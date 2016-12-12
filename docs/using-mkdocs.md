# Using MkDocs

## Documentation

[http://www.mkdocs.org/](http://www.mkdocs.org/) 

For full documentation.

## Adding a page

[http://www.mkdocs.org/#adding-pages](http://www.mkdocs.org/#adding-pages) 

    curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md

## Code

```
Fenced code blocks are like Standard
Markdown’s regular code blocks, except that
they’re not indented and instead rely on
start and end fence lines to delimit the
code block.
```

```javascript
console.log("Hello");
```


## Styling

[Writing and styling tips](http://www.mkdocs.org/user-guide/writing-your-docs/) 
## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

!!! note
    This is an example of a note

!!! warning
    This is an example of a warning block


## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## Tables

First Header | Second Header | Third Header
------------ | ------------- | ------------
Content Cell | Content Cell  | Content Cell
Content Cell | Content Cell  | Content Cell
