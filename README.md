# caravan.landondahle.com

Static site for the **caravan** subdomain on [landondahle.com](https://landondahle.com).

## Develop

```bash
cd caravan.landondahle.com
npx --yes serve -l 4400
```

Open http://127.0.0.1:4400/

## Remote

```text
https://github.com/lardahle/caravan.landondahle.com.git
```

```bash
git remote add origin https://github.com/lardahle/caravan.landondahle.com.git
git push -u origin main
```

Point DNS **caravan.landondahle.com** at your host; web root = this folder (where `index.html` lives).

## Deploy (GitHub Actions → FTP)

On every push to **`main`**, [.github/workflows/deploy-ftp.yml](.github/workflows/deploy-ftp.yml) runs [SamKirkland/FTP-Deploy-Action](https://github.com/SamKirkland/FTP-Deploy-Action) and uploads the repo (minus `.git`, `.github`, `README`, `.gitignore`) to your host.

**Repository secrets** (Settings → Secrets and variables → Actions):

| Name | Example |
|------|--------|
| `FTP_SERVER` | Host from Site Tools → FTP (e.g. `ftp.landondahle.com` or the value shown) |
| `FTP_USERNAME` | FTP user for that site or subdomain |
| `FTP_PASSWORD` | That user’s password |

If the FTP account opens in the **wrong folder**, edit the workflow and set `server-dir` to your subdomain’s document root (see comment in the YAML).

You can re-run the job manually: **Actions** → **Deploy via FTP** → **Run workflow**.
