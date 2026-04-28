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
