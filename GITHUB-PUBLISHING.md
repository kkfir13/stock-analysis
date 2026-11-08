# Publish this Claude plugin to a public GitHub repository

Anthropic's public plugin directory expects a GitHub repository or a folder
inside a repository, **not** the uploaded ZIP itself. Do not change the
visibility of the private `kkfir13/edge-value-vision` product repository.

1. Sign in to https://github.com/new and create a **Public** repository named
   `stock-analysis` under `kkfir13`. Leave README/license generation
   unchecked (they are included in this package).
2. Unzip this archive and commit **all files and directories**, including the
   hidden `.claude-plugin` directory, to the `main` branch. The required file
   must exist at `/.claude-plugin/plugin.json`.
3. With Git CLI, from the unpacked directory, run:

   ```bash
   git init -b main
   git add -A
   git commit -m "Publish Stock Analysis by ValuEdge Claude plugin v1.2.0"
   git remote add origin https://github.com/kkfir13/stock-analysis.git
   git push -u origin main
   ```

4. Check that the repo browser shows `README.md`, `LICENSE`, `.mcp.json` and
   `.claude-plugin/plugin.json`.
5. In Claude's **Submit a plugin → Source** screen enter:

   - **Repository:** `https://github.com/kkfir13/stock-analysis`
   - **Plugin path:** leave empty (repository root)
   - **Branch or tag:** leave empty (default `main`)

6. Click **Validate** and fix any reported errors before proceeding.

Security: never add `.env`, tokens, OAuth secrets, Supabase service keys,
Cloudflare credentials, or backend code to this public repository.
