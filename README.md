# To replicate issue

Render using a profile:
```
quarto render --profile narrow-body
```

This creates `_narrow-body` as expected, and `_narrow-body` doesn't contain `_site` as expected.

```
_narrow-body/
├── about.html
├── default-layout.html
├── default-layout_files
├── index.html
├── search.json
├── site_libs
└── styles.css
```

Now render without a profile:
```
quarto render
```

`_site` now includes `_narrow-body`:

```
_site/
├── _narrow-body
├── about.html
├── default-layout.html
├── default-layout_files
├── index.html
├── search.json
├── site_libs
└── styles.css
```

Problem seems to be adding the file `default-layout.qmd` - delete this file and there is no unexpected behavior.


