# OpenRouter Models Static Browser

Static GitHub Pages-friendly browser for `https://openrouter.ai/api/v1/models`.

## Files

- `generate-openrouter-models-page.js` — Node.js generator
- `index.template.html` — UI template
- `models.json` — downloaded OpenRouter models data
- `index.html` — generated page
- `model.js` — generated gzip+base64 JSON payload

## Regenerate

```bash
wget https://openrouter.ai/api/v1/models -O models.json
node generate-openrouter-models-page.js models.json .
```

## Local test

```bash
python3 -m http.server 8080
```

Open:

```text
http://127.0.0.1:8080/
```

## Codex config flow

1. Check model rows in the table.
2. Click `Generate config.toml`.
3. Copy the generated TOML into `./codex/config.toml` or `~/.codex/config.toml`.
4. Use selected profile:

```bash
codex --profile profile-name
```
