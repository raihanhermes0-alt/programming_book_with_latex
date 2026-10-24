# Programming Book with LaTeX

## Environment

Open this repository in VS Code and choose **Reopen in Container** when
prompted. The dev container installs `latexmk` and the TeX Live packages used
to build the book, plus Pandoc for DOCX export. The first container build
downloads these packages and may take a few minutes.

The recommended **LaTeX Workshop** extension builds `main.tex` when you save
it and opens the result in a VS Code PDF tab. The PDF is written to `build/`.
Use the extension's SyncTeX navigation to jump between source and PDF.

To build both outputs, run **Terminal > Run Build Task > Build PDF and DOCX**
in VS Code. The PDF preview updates automatically when you save the source;
run the task again to refresh the DOCX.

The outputs are `build/main.pdf` and `build/main.docx`. DOCX is converted
from the LaTeX source by Pandoc, so complex LaTeX layouts may not be preserved
exactly; use the PDF as the typeset version and edit the DOCX in a word
processor if needed.

To build from the integrated terminal instead:

```sh
latexmk -pdf -outdir=build main.tex
pandoc --from=latex --to=docx main.tex --output=build/main.docx
```

To remove generated files:

```sh
latexmk -C -outdir=build main.tex
```
