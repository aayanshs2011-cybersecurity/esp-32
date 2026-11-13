# Deploy your ESP32 Labs site to Vercel

This is a deployment-ready copy of [ESP32 Labs](https://github.com/agharsallah/esp-labs-web) by Abderrehmen Gharsallah, with its accompanying [esp-labs firmware](https://github.com/agharsallah/esp-labs). The original MIT license and firmware license are retained. Espressif's reference and third-party materials retain their own terms.

## GitHub + Vercel (recommended)

1. Unzip this folder and upload its contents to a new GitHub repository. Include the `firmware-source` folder and `docs-llm/esp32-s3` (including its images); they power the code and reference readers. Upload the files themselves, not a folder containing the project.
2. In Vercel, choose **Add New → Project**, import your repository, and select **Node.js 24.x** in the project settings. The Vite preset, install command, build command and output directory come from `vercel.json`.
3. Select **Deploy**. No API keys or environment variables are needed. Later pushes deploy automatically.

## Vercel CLI

From the unzipped project root, with Node.js 24.14+ installed:

```sh
npm install -g vercel
vercel login
vercel
vercel --prod
```

The included `.vercelignore` intentionally keeps the reference files. Do not remove `firmware-source` or `docs-llm/esp32-s3` if you want the full code and datasheet readers.

## Run locally

```sh
corepack enable
pnpm install --frozen-lockfile
pnpm dev
```

For a production build, use `pnpm build` and `pnpm preview`. Progress is stored in each visitor's browser; it is not shared between devices. The bench status data represents the original project's example and can be edited in `public/data/`. Links to firmware on GitHub point to the original firmware repository unless `VITE_LABS_SOURCE_URL` is customized.

## What changed

The interface has been visually refreshed while retaining the original functionality and credit. The firmware lives inside this project at `firmware-source`; the default firmware path was updated; automatic Git deployments were enabled; the reference is no longer excluded from CLI deployments; the original repository-specific GitHub workflows were removed. No Vercel account has been connected or deployment made on your behalf.
