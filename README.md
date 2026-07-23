# Upload-FTP

Automated FTP deployment powered by GitHub Actions. Push to `main` and your files are deployed to your hosting server — no manual uploads needed.

## How It Works

A GitHub Actions workflow triggers on every push to the `main` branch (or manually via `workflow_dispatch`). It uses [SamKirkland/FTP-Deploy-Action](https://github.com/SamKirkland/FTP-Deploy-Action) to sync your repository files to a remote server over FTP.

- **Automatic deploys** on push to `main`
- **Manual trigger** available via GitHub Actions UI
- **Concurrency control** — concurrent deploys are cancelled to avoid conflicts
- **Smart exclusions** — `.git` and `.github` directories are never uploaded

## Setup

Add the following secrets to your repository (**Settings → Secrets and variables → Actions**):

| Secret            | Description                          |
| ----------------- | ------------------------------------ |
| `HOST_HOST`       | FTP server hostname (e.g. `ftp.example.com`) |
| `HOST_USER`       | FTP username                         |
| `HOST_PASSWORD`   | FTP password                         |

Once configured, every push to `main` will automatically deploy your files.

## License

[MIT](LICENSE) © Toward_77
