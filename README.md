# web-games

Published web games portfolio — finished games promoted from the
[`web-games-forge`](https://github.com/p2well/web-games-forge) lab.

**Live site:** https://p2well.github.io/web-games/

## Structure

Each game lives in its own top-level folder as a self-contained
[Phaser 4](https://phaser.io/) + [Vite](https://vitejs.dev/) app:

```
web-games/
├── index.html                 # Landing gallery (linking to each game)
├── snake/                     # A published game (self-contained Vite app)
│   ├── index.html
│   ├── package.json
│   ├── vite/
│   ├── public/
│   └── src/
└── .github/workflows/deploy.yml
```

## How games are published

1. Build a game in the [forge](https://github.com/p2well/web-games-forge).
2. When it's finished, copy its self-contained directory here as `<game>/`.
3. Open a PR to `main`. On merge, the GitHub Actions workflow builds **every**
   game folder and deploys them under one GitHub Pages site:
   `https://p2well.github.io/web-games/<game>/`.

Games use relative asset paths (`base: './'`), so each one works correctly
under its `/web-games/<game>/` subpath — and also deploys unchanged to
root-domain hosts such as Vercel or Netlify.

## Local development

Each game is an independent npm project:

```bash
cd snake
npm install
npm run dev
```

## Deployment

Deployment is fully automated via `.github/workflows/deploy.yml` using the
official GitHub Pages actions. Enable it once under
**Settings → Pages → Build and deployment → Source: GitHub Actions**.

## License

MIT
