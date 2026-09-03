# Astro

A brief example of an [Astro](https://astro.build/) site that runs as a standalone Node server and deploys to any host with [DollarDeploy](https://dollardeploy.com). This demo showcases:

- `/` - A static page (pre-rendered)
- `/ssr` - A page that uses server-side rendering
- `/ssr-with-swr-caching` - Similar to the previous page, but also sets `stale-while-revalidate` `cache-control` headers so a CDN/proxy in front can cache the response
- `/image` - Astro [Asset](https://docs.astro.build/en/guides/images/) using the built-in sharp image optimization

It uses the [`@astrojs/node`](https://docs.astro.build/en/guides/integrations-guide/node/) adapter in `standalone` mode, so `pnpm build` produces a server you start with `pnpm start`.

## Deploy Your Own

Deploy with the DollarDeploy CLI ([`ddc`](https://www.npmjs.com/package/@dollardeploy/cli)):

```bash
npm install -g @dollardeploy/cli
ddc auth
ddc deploy --url https://github.com/huksley/astro-boilerplate --create-host
```

The server listens on `0.0.0.0` and respects the `PORT` environment variable (defaulting to `3000`).

## Project Structure

Astro looks for `.astro`, `.md`, or `.js` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we like to put any Astro/React/Vue/Svelte/Preact components or layouts.

Any static assets, like images, can be placed in the `public/` directory.

## Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                             |
| :--------------------- | :------------------------------------------------- |
| `pnpm install`         | Installs dependencies                              |
| `pnpm run dev`         | Starts local dev server at `localhost:4321`        |
| `pnpm run build`       | Build your production site to `./dist/`            |
| `pnpm run preview`     | Preview your build locally, before deploying       |
| `pnpm run start`       | Runs the built production server (`PORT`, default `3000`) |
| `pnpm run astro ...`   | Run CLI commands like `astro add`, `astro preview` |
| `pnpm run astro --help`| Get help using the Astro CLI                       |
