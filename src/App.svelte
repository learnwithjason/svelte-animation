<script>
  import { fly } from "svelte/transition";
  import { elasticOut } from "svelte/easing";
  import { spring } from "svelte/motion";

  let isActive = true;

  function anythingIWant() {
    return {
      css: t => {
        return `
					transform: scale(${t});
				`;
      },
      easing: elasticOut,
      duration: 3000
    };
  }

  function drag(node) {
    let x;
    let y;

    const coords = spring({
      x: 0,
      y: 0
    });

    coords.subscribe(current => {
      node.style.transform = `translate3d(${current.x}px, ${current.y}px, 0)`;
    });

    node.addEventListener("mousedown", mousedown);

    function mousedown(event) {
      x = event.clientX;
      y = event.clientY;

      window.addEventListener("mouseup", mouseup);
      window.addEventListener("mousemove", mousemove);
    }

    function mouseup() {
      window.removeEventListener("mouseup", mouseup);
      window.removeEventListener("mousemove", mousemove);

      coords.update(() => {
        return { x: 0, y: 0 };
      });

      node.dispatchEvent(
        new CustomEvent("dragstop", {
          detail: { x, y }
        })
      );

      x = 0;
      y = 0;
    }

    function mousemove(event) {
      const dx = event.clientX - x;
      const dy = event.clientY - y;

      x = event.clientX;
      y = event.clientY;

      coords.update(current => {
        return {
          x: current.x + dx,
          y: current.y + dy
        };
      });
    }
  }
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  .box {
    background: red;
    display: block;
    height: 100px;
    margin: 0 auto;
    width: 100px;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1 use:drag>Animation in Svelte</h1>
  <button on:click={() => (isActive = !isActive)}>
    {#if isActive}Hide Box{:else}Show Box{/if}
  </button>
  {#if isActive}
    <div
      class="box"
      transition:anythingIWant
      use:drag
      on:dragstop={event => {
        if (event.detail.x > 300) {
          isActive = false;
        }
      }} />
  {/if}
</main>
