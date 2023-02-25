# To replicate issue

The commit prior to adding these instructions adds the file `default-layout.qmd` - prior to adding this file there doesn't seem to be any unexpected behavior.


Now, render using a profile:
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
