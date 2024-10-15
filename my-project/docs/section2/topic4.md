# Enable GitHub Pages for Hosting MkDocs
After pushing your MkDocs project to GitHub, install the MkDocs GitHub Pages plugin:

```
pip install mkdocs-material mkdocs-git-revision-date-localized-plugin
```

Add this to your *mkdocs.yml* file:
```
plugins:
  - search
  - git-revision-date-localized
```

Deploy your site:
```
mkdocs gh-deploy
```
