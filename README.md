# APA 7 Student LaTeX Template for Pandoc

This repository contains a LaTeX template for generating APA 7 formatted documents using Pandoc. Follow the instructions below to set up your environment and use this template.

## Installation

### MacOS/Linux

This template has only been tested using the MacOS, but should work on all OS distributions that Pandoc supports.

1. Install [Pandoc](https://pandoc.org/installing.html)
2. Download the latest version of [apa7_student](https://github.com/liquidswrds/apa7_student.git) template
3. Move the template to your Pandoc template folder. The typical location for MacOS:
    - `/Users/USERNAME/.pandoc/templates`
    - `/Users/USERNAME/.local/share/pandoc/templates/`
    - _**Note: if you do not see the template forlder you will need to create it using the following command:**_ `mkdir .pandoc/templates`

## Usage

These instruction assume you have some basic knowledge of markdown and Pandoc. This is only suggested usage using basic command line tools. Feel free to use VSCode, Obsidian, etc..

1. Create a folder to organize your research paper. Ex. `mkdir research`
2. Create your markdown file. `touch document.md`
3. Add your content to the markdown file. `vim document.md`

    ```markdown
    ---
    title: "Your Document Title"
    author: "Your Name"
    date: "2024-01-01"
    institution: "Your Institution"
    course: "Course Name"
    instructor: "Instructor Name"
    duedate: "2024-01-10"
    bibliography: ["references.bib"]
    ---  
    # Introduction  
    This is an example document using the APA 7 Student LaTeX template.  
    # Methods  
    Describe your methods here.  
    # Results  
    Describe your results here.  
    # Discussion  
    Discuss your findings here.  
    # References
    ```

4. Add your bibliography

    Create a `references.bib` file with your bibliography entries in BibTeX format. `vim references.bib`

    ```bibtex
    @article{sample2024,
    author = {Author, A.},
    title = {Sample Article},
    journal = {Journal Name},
    year = {2024},
    volume = {1},
    pages = {1-10},
    }
    ```

5. Download the current Citation Style Language (CSL) template [apa7](https://www.zotero.org/styles/apa)
6. Compile the document with Pandoc
    Use the following command to generate the PDF document:

    ```sh
    pandoc document.md --template=apa7_student.latex --pdf-engine=xelatex -o document.pdf
    ```

    This command tells Pandoc to use the `apa7_student.latex` template, the `xelatex` engine, and to output a PDF file named `document.pdf`.

### Custom YAML Header Variables

#### Required

`title:` Enter the title of your paper
`author:` Enter your name  
`institution:` Enter your University/College name  
`course:` This is your course number  
`instuctor:` Enter your professor/instructor name  
`duedate:` Enter the date the assignment is due  
`abstract:` Enter the abstract for your paper

#### Additional

Other Pandoc variable are supported [Pandoc Manual](https://pandoc.org/MANUAL.html#variables-for-latex)

#### Example of YAML Header

```markdown
---
title: "The Quantization of Rabbits in a Vacuum"
author: "Stephen Hawking"
institution: "UA Little Rock"
course: "CSEC 3201"
instructor: "Dr William Pepper"
duedate: "July 4, 1776"
bibliography: "references.bib"
csl: "apa.csl"
abstract: |
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Tempor orci eu lobortis elementum nibh tellus. Sit amet nulla facilisi morbi tempus iaculis urna id. Diam maecenas ultricies mi eget mauris pharetra et. Amet aliquam id diam maecenas ultricies mi eget mauris pharetra. Ipsum consequat nisl vel pretium. Tortor condimentum lacinia quis vel. Placerat duis ultricies lacus sed turpis tincidunt.

---
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes or improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
