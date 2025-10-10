## Secret Of The Polyglot
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
The file: https://artifacts.picoctf.net/c_titan/9/flag2of2-final.pdf

### Solve
**Flag:** `picoCTF{f1u3n7_1n_pn9_&_pdf_7f9bccd1}`

The file was opened via a web browser (google chrome) as adobe acrobat displayed an error(mostly due to naming the flag with wrong extension). In the web browser, the file displayed the second part of the flag "1n_pn9_&_pdf_7f9bccd1}". Then,the file was opened using the hex editor,HxD, for further examination. The first few bites say, PNG, meaning that the file is actually a PNG file and not a pdf file. We can rename the file, by using mv command in bash as so, "mv flag2of2-final.pdf flag2of2-final.png". After the conversion, upon opening the png file, gave us the first part of the flag "picoCTF{f1u3n7_". Upon combining the two parts we get the flag.

### New Learnings


### References 
-> File signatures: https://filesig.search.org/