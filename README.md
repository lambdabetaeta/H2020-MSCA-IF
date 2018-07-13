This is a LaTeX template for the Marie Sklodowska-Curie Individual
Fellowships application (H2020-MSCA-IF). I have updated it to the
2018 call.

Disclaimer: I do not offer any guaratees about this template. Use
at your own risk.

## Usage Instructions

### Command Line

Just

> make

This will produce [IF-Part_B.pdf](IF-Part_B.pdf), which is the
combination of both documents in Part B of the proposal.  When
submitting the grant, one must submit documents 1 and 2
separately. To compile them, type: 

> make doc1 

> make doc2

The first command will produce [document1.pdf](document1.pdf); 
the second will produce [document2.pdf](document2.pdf).

### From TeXShop

If you need to compile from within your LaTeX IDE instead of with the command line, 
you need the flag: 

> --jobname=document1 "\includeonly{doc1}\input{IF-Part_B}"

> --jobname=document1 "\includeonly{doc2}\input{IF-Part_B}"

to produce [document1.pdf](document1.pdf) and [document2.pdf](document2.pdf), respectively. 
In TexShop 3.65, you can add this flag in the _Engine_ submenu of the TexShop preferences. 
Add the desired flag (just one at a time) to the _pdflatex_ command after: 
_--file-line-error --synctex=1_

Note, however, that cross-references and page numbers will only be correct if you had just 
previously compiled the full document without the flag. 
If the references are incorrect, try recompiling the entire [IF-Part_B.pdf](IF-Part_B.pdf). 
That is to say, remove the _--jobname..._ flags, recompile, and then add them back. 
(This is, in fact, exactly what the Makefile does.) 

### Grant Preparation Instructions

To prepare your proposal you will want to:

  1. Edit the relevant metadata in [IF-Part_B.tex](IF-Part_B.tex), 
  such as your proposal acronym.
  
  2. Complete [doc1.tex](doc1.tex), which corresponds to the first
  document of Part B.
  
  3. Complete [doc2.tex](doc2.tex), which corresponds to the second document.


If you encounter difficulties compiling the pdf, try the following:

 * Delete all `*.aux` files before compiling
 
 * Consult [this StackOverflow answer](http://tex.stackexchange.com/a/31366/84485), 
 which is what the script is based on
 
 * Just build [IF-Part_B.tex](IF-Part_B.tex) normally and then manually split the files 
 
 * Open a new issue describing the difficulties.
