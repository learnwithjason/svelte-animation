<p align="center">
  <a href="https://www.learnwithjason.dev">
    <img src="https://res.cloudinary.com/jlengstorf/image/upload/q_auto,f_auto,w_240/v1579281727/lwj/learnwithjason.png" alt="Learn With Jason" width="120" />
  </a>
</p>
<h1 align="center">
  Animation With Svelte (with Scott Tolinski)
</h1>
<h3 align="center">
  This app was built live on <em>Learn With Jason</em> and it was super fun and I’m sad you weren’t there.
</h3>
<p align="center">
  But don’t worry! You can still: 
  <a href="https://www.learnwithjason.dev/animation-with-svelte"><strong>watch the video</strong></a> · 
  <a href="https://svelte-animation.netlify.app"><strong>see the demo</strong></a> · 
  <a href="https://app.netlify.com/start/deploy?repository=https://github.com/learnwithjason/svelte-animation&utm_source=learnwithjason&utm_medium=github&utm_campaign=devex"><strong>deploy this project</strong></a> · 
  <a href="https://jason.af/lwj/schedule"><strong>see upcoming episodes</strong></a>
</p>

&nbsp;

Svelte is gaining a lot of popularity in the JavaScript community, and its robust animation capabilities probably have a lot to do with that. in this episode, Scott Tolinski will teach us how to animate in Svelte 🔥

&nbsp;

## More Information

- [Watch this app get built live + see links and additional resources][episode]
- [Follow _Learn With Jason_ on Twitch][twitch] to watch future episodes live
- [Add the _Learn With Jason_ schedule to your Google Calendar][cal]

&nbsp;
<p align="center">
  <a href="https://app.netlify.com/start/deploy?repository=https://github.com/learnwithjason/svelte-animation&utm_source=learnwithjason&utm_medium=github&utm_campaign=devex">
    <img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy this project to Netlify" />
  </a>
</p>

[episode]: https://www.learnwithjason.dev/animation-with-svelte
[twitch]: https://jason.af/twitch
[cal]: https://jason.af/lwj/cal
## This was created using the Svelte template

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

```bash
node scripts/setupTypeScript.js
```

Or remove the script via:

```bash
rm scripts/setupTypeScript.js
```

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public my-project.surge.sh
```
