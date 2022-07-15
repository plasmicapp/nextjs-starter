# A statically generated landing page using Next.js and Plasmic

This example showcases Next.js's [Static Generation](https://nextjs.org/docs/basic-features/pages) feature using [Plasmic](https://www.plasmic.app/) as the visual page builder.

You'll get:

- Statically generated pages from your visual designs
- Development server on [preview mode](https://nextjs.org/docs/advanced-features/preview-mode) watches for changes from Plasmic Studio

## Deploy your own

Once you have access to the [environment variables you need](#step-3-set-up-environment-variables), deploy the example using [Netlify](https://www.netlify.com/):

[![Deploy with Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/plasmicapp/nextjs-starter#NEXT_PUBLIC_PLASMIC_PROJECT_ID=2UaUgsF5EfZMMRJgygm1T1&NEXT_PUBLIC_PLASMIC_PROJECT_API_TOKEN=Ku1gFeO2mlPAlqPBKpv5BGIJNd5NUboG6eDc7qVcP3ZRbHsKUTma9LJuMlE2fUXL2jvhnnyA7I5hRVpu0qA&PLASMIC_PREVIEW_SECRET=plasmic_preview_s)

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init), [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/), or [pnpm](https://pnpm.io) to bootstrap the example:

```bash
npx create-next-app --example cms-plasmic cms-plasmic-app
# or
yarn create next-app --example cms-plasmic cms-plasmic-app
# or
pnpm create next-app --example cms-plasmic cms-plasmic-app
```

## Configuration

### Step 1. Create an account and a project on Plasmic

First, [create an account on Plasmic](https://studio.plasmic.app/).

After creating an account, create a new project.

### Step 2. Gather your project ID and API token

Once you've opened your Plasmic project, you can find the project ID in the URL: `https://studio.plasmic.app/projects/PROJECTID`.

The API token can be found by clicking the Code button in the top bar.
![api token](https://www.plasmic.app/blog/static/images/plasmicflix/08-api-token.png)

### Step 3. Set up environment variables

Copy the `.env.local.example` file in this directory to `.env.local` (which will be ignored by Git):

```bash
cp .env.local.example .env.local
```

Then replace the default env values in `.env.local` with your project credentials:

- `NEXT_PUBLIC_PLASMIC_PROJECT_ID` should be the `projectId` value in step 2.
- `NEXT_PUBLIC_PLASMIC_PROJECT_API_TOKEN` should be the API token gathered in previous step.
- `PLASMIC_PREVIEW_SECRET` can be any random string (but avoid spaces), like `MY_SECRET` - this is used for [Preview Mode](https://nextjs.org/docs/advanced-features/preview-mode).

### Step 4. Run Next.js in development mode

```bash
npm install
npm run dev
# or
yarn install
yarn dev
```

Your blog should be up and running on [http://localhost:3000](http://localhost:3000)! If it doesn't work, post on the [Plasmic Slack Community](https://www.plasmic.app/slack).

### Step 5. Try preview mode

By default, the code is set up to only build published Plasmic projects.
If you want to see changes as you make them in the Plasmic Studio, enter preview mode by opening the following URL:

```
http://localhost:3000/api/preview?secret=PLASMIC_PREVIEW_SECRET&slug=PATH
```

Be sure to replace the secret with the chosen secret in Step 3 and pick a path to preview (e.g. `http://localhost:3000/api/preview?secret=123456&slug=/`)

Now you can make edits in the Studio and see them reflected in the development server live.

You can exit preview mode at any time by going to the following URL:

```
http://localhost:3000/api/exit-preview
```

### Step 6. Deploy on Netlify

You can deploy this app to the cloud with [Netlify](https://www.netlify.com/) ([Documentation](https://docs.netlify.com/)).

To deploy your local project, push it to GitHub/GitLab/Bitbucket and import to [Netlify](https://app.netlify.com/start).

**Important**: When you import your project, make sure to click on **Environment Variables** and set them to match your `.env.local` file.

## Next steps:

With Plasmic, you can enable non-developers on your team to publish pages and content into your website or app.

To learn more about Plasmic, take a look at the following resources:

- [Plasmic Website](https://www.plasmic.app/)
- [Plasmic Documentation](https://docs.plasmic.app/learn/)
- [Plasmic Slack Community](https://www.plasmic.app/slack)

You can check out [the Plasmic GitHub repository](https://github.com/plasmicapp/plasmic) - your feedback and contributions are welcome!
