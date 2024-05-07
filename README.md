# ANDES Latex Template

Template to write ANDES documents using LaTeX.

# Breaking changes

### From v1.0 to v2.0:
- The `\req` and `\question` now accepts the label as an optional (i.e., non -mandatory) argument.  This is a breaking chage since the label is supposed to be provided with square brackets rather than curly ones. E.g.
```
% Old version (v1.0), using curly brackets for label
\req{req:MyLabel}{My requirement}

% Current version (v2.0), using square brackets for label or no label at all (an automatic one is internally generated):
\req[req:MyLabel]{My requirement}
\req{My requirement}
```

- Two new commands are available, `\reqlong` and `\questionlong` allowing to specify a custom text for the list of requirements and questions respectively;

- Minor changes:
  - `_preamble.tex` and `_title.tex` are now included with `\input` rather than `\include`;
  - The *Scope* section in `introduction.tex` is now a `\subsection`;
  - The new *Paragraphs* section in `example_section.tex` provides a guideline to use `\medskip` and `\noindent`;

As usual, have a look to the `example_section.tex` file for examples on how to use the above commands.




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
