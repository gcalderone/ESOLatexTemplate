# ANDES Latex Template

Template to write ANDES documents using LaTeX.

# Workflow

- Rename the main file (`Main.tex`) into the final document name, e.g.: `mv Main.tex ANDES_InstrumentSoftwareRequirements.tex`.
- Modify the document properties at the beginning of the main file;
- Insert images into the `media` folder, and insert text in `introduction.tex`, `related_documents.tex`, `section.tex`, etc.  You may also add new files to be included using the `\include{filename.tex}` command;
- Use the provided environments and commands for specific tasks:
  - Applicable documents (`ADlist` environment and `\ARDitem` command);
  - Reference documents (`RDlist` environment and `\ARDitem` command);
  - Cite applicable or reference documents (`\citedoc` command);
  - Reference a requirement (`\citereq`) or a question (`\citequestion`);
  - Generate the table of rquirements (`\listofreq`) and questions (`\listofquestion`).
  See examples in the provided `.tex` files;
- Note: the `_preamble.tex` and `_title.tex` files are not supposed to be modified by users;
- Finally, compile into a PDF file with the command:
  ```
  pdflatex ANDES_InstrumentSoftwareRequirements.tex
  ```
  You may need to run the command multiple times to get the correct references.
