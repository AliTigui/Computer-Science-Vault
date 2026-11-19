# OnlineVault template

This folder is a complete, static viewer. Host it as-is on GitHub Pages,
Netlify, or any plain web server — there is no build step and no backend.

## Add a vault

1. Put your Obsidian vault files inside `vault-assets/` (Markdown plus any
   images, PDFs, audio, etc.). Keep the folder structure.
2. Open `pack.html` from this site and choose the `vault-assets` folder,
   or run `node tools/pack-vault.mjs --index` from this folder.
3. Reload the page.

The browser option needs no install (Chrome/Edge; other browsers can use
its file-picker fallback). The Node option needs Node.js 18+. Both write
`vault-assets/vault.json`, which lists the notes and attachments. The viewer
reads that file at runtime, so the same build works for any vault. To pack
a vault directly from its original location instead, run:

```bash
node tools/pack-vault.mjs "/path/to/My Vault" --out vault-assets
```

To update the vault later, copy in the changes and re-run the packer.

Notes with `publish: false` in their frontmatter are skipped. Everything in
`vault-assets/` is public once hosted — review it before publishing.
