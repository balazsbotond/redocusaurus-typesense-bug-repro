# Redocusaurus - TypeSense Search Bar bug repro

This is a minimal example to reproduce [this bug](https://github.com/rohit-gohri/redocusaurus/issues/236)
which causes build failure if a project uses both the TypeSense search bar plugin and Redocusaurus.

Individual commits show the steps the project was built.

Steps to reproduce the bug:

```
npm install
npm run build
```

The build fails with the following error:

```
main:38056
                {}.DEBUG = namespaces;
                  ^

SyntaxError: Unexpected token '.'
```

If you comment out the following line (line 74) in `docusaurus.config.js`,
the project can be built successfully.

```
themes: ['docusaurus-theme-search-typesense'],
```