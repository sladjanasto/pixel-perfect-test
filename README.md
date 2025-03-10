# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

## Project Details
For this project, I used the latest version of Tailwind CSS, which no longer relies on a tailwind.config.js file. Instead, I utilized CSS variables to handle styling configurations. While it's not my usual approach, I decided to keep Tailwind classes inline for this test project. Normally, I prefer structuring styles using @apply and @layers for better maintainability.

I have not worked with SvelteKit before, as my background is in a different framework, but I made an effort to follow best practices. I assume these are similar to Angular's best practices, but I may be mistaken.

Regarding accessibility, I have included some foundational improvements, though I haven't added SEO-specific tags. As a result, the Lighthouse score for SEO is lower. However, since this is just a test project, I focused on other aspects.

I tested the responsiveness based on the available design, which was only for mobile. Consequently, the layout on larger screens has a somewhat restricted width.

Let me know if you need any modifications or additional details!
