# Convert markdown to PDF on Linux

Two examples are given:
- A4 portrait document
- landscape slides for presentation

## Quick start

1. Create one Markdown file per chapter.
2. Edit `title.md`: set the title, the author's name, etc.
3. Edit `project.mk` to list the chapters in the desired order, starting with `title.md`.
4. Type `make` to produce a PDF file.

💡 Tip: to force make to run: `make -B`.

👉 Type `\newpage` to create a **new slide**.


## Pandoc

[Pandoc](https://pandoc.org/), the _universal document converter_, is used to convert Markdown to PDF.

### Install pandoc

```shell
$ apt-get -y install pandoc texlive-xetex librsvg2-bin
```

### Run pandoc

1. Edit `project.mk`.
1. Run pandoc: `make`.

💡 Tip: to force make to run: `make -B`.

## Styling

### Emojis

- Unicode emojis can be rendered in the PDF, although not all emojis are actually rendered by the font used.
  _DejaVu Sans_ has more emojis than e.g. _Liberation Sans_.
- Markdown emoji codes such as `:warning:` are not rendered in the PDF.
  Use Unicode instead, such as `U+26A0` for ⚠.


### Mermaid diagrams

1. Convert the Mermaid diagrams to SVG or PNG, e.g. on [Mermaid.live](https://mermaid.live/), [Mermaid Editor](https://mermaideditor.com/tools/mermaid-to-svg) or [Mermaid Online](https://mermaidonline.org/mermaid-to-svg).
1. Include the image in the markdown document in place of the Mermaid diagrams.
1. Run pandoc.

Some people report that they can convert Mermaid to SVG with mmdc-cli, the Mermaid CLI tool, but I didn't manage to install it.

### Slides

- To increase the font size, change the page size in `title.md`: A4, A5 or A6.
- Images whose width is larger than their height are rendered better.
  Otherwise, some undesired page breaks may be added.
- Type `\newpage` to create a new slide.
- `\newpage` is added automatically at the beginning of a new chapter.