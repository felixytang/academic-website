# Managing Publications

## Automatic BibTeX Import (Recommended)

1. Edit `publications.bib` in the repository root
2. Add your publications in BibTeX format
3. Commit and push to GitHub
4. GitHub Actions will automatically generate publication pages
5. Review and merge the automated pull request

## Manual Publication Creation

To manually create a publication:

```bash
hugo new content/publication/paper-name/index.md
```

Then edit the file with your publication details:
- title, authors, date
- publication type, journal/conference
- DOI, abstract, links
- Add PDF to `static/uploads/`
- Add BibTeX in `cite.bib`

## Tips

- Keep `publications.bib` as your master source
- Export from reference managers (Zotero, Mendeley, etc.)
- GitHub Actions handles the conversion automatically
- You can customize generated pages after auto-import
