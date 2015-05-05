PdfToXomUtility
===============

PdfToXom utility is used to create java files from given pdf files.
The utility reads the pdf file and extracts all editable fields available in it.
Then it uses these fields to create java file. The generated java file will have
the fields as member variables and its getters and setters methods.


##### Create Jar from the source code

To generate stand alone executable jar for the PdfToXomUtility project, follow below steps: 

* From terminal, go inside CMS-DocumentGenerationService directory.
* Execute command:

```
    gradle build
```

* Look for the generated jar file in  CMS-DocumentGenerationService/PdfToXomUtility/build/libs directory
* The jar is generated with name "PdfToXom-1.0.0.jar"


##### Running the application 

To create java file from given set of pdf files, follow below steps:

* Copy the Executor.sh file and put it in a directory on the file system. Put the "PdfToXom-1.0.0.jar" jar in 
   the same directory.
* Through Unix terminal, go inside the directory where Executor.sh is kept.
* To view help, run command:

```
    ./Executor.sh -h
```

* To generate java file from pdfs kept in current working directory i.e. the directory where the 
    Executor.sh and PdfToXom-1.0.0.jar are kept, execute below sample command
	
```
    ./Executor.sh -f pdf1.pdf,pdf2.pdf,pdf3.pdf 
```

  Note: There should be no space between pdf file names and it should be comma separated. In above command, pdf1,pdf2
  etc are given for example. While executing this command you will have to give actual PDF names instead.
   
  Example: suppose your pdf file names are VSD3333.pdf and REG227.pdf then the command to generate java file will
  as below:
	
```
    ./Executor.sh -f VSD3333.pdf,REG227.pdf
``` 

* To generate java file from pdfs which are kept in another directory on the file system use below command

```
    ./Executor.sh -d PATH_OF_PDF_DIRECTORY
```

   Note: This command will take only one directory path at a time and read all pdfs inside it to generate java file.
    
   Example: Suppose you have kept all your pdf files in /home/dev/pdfs directory then fire below command from the terminal
	
```
    ./Executor.sh -d /home/dev/pdfs
```

*  To generate java file from pdf having absolute path known on the file system use below command

```
    ./Executor.sh -p /home/dev/pdfs/pdf1.pdf,/home/usr/pdfs/pdf2.pdf,/usr/pdfs/pdf3.pdf   
```

   Note: There should not be any blank space between absolute paths of pdfs.
    
   Example: Suppose you have two pdf file in different directories(home/dev/pdfs and /home/usr/pdfs) and you want to generate
   generate java file then from the terminal execute below command
	
```   
    ./Executor.sh -p /home/dev/pdfs/VSD3333.pdf,/home/usr/pdfs/REG227.pdf
```

*  The java file is generated in your current working directory.  

*  The format of the java file generated will be 
   Your first pdf file name + Xom + timestamp + .java
  

*  If something goes wrong while java file generation, look for the error trace in your terminal or log4j-application.log 
   file in your current working directory.

