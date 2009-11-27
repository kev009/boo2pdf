Transmogrifier -- created Tue Apr 16 15:07:42 2002

Problems fixed in this release.
Large Black/White images are no longer truncated during
processing.


The Transmogrifier will take an existing BookManager Book, and if any
Pictures are present, will create a copy of the Book in which the
pictures have been converted into a form compatible with todays Web
Browsers.

Such conversion is necessary for Books being served by BookServer
for AIX vs 2.2, and BookServer for Linux vs 2.2.  It is recommended
that Books that will be read by the SoftCopy Reader for Java also
be converted.


Installation.
It is recommended that this initial version be run from the
directory containing the Books to be converted.

1. Place the self-extracting file TranBook.EXE in the directory
   containing the Books to be converted.

2. Execute the self-extracting file 'TransBook'.
   This will create the following files:
       EBGIF2.FLT
       EBGIF2.INI
       EMCGM2.FLT
       EMCGM2.INI
       EMMET2.FLT
       EMMET2.INI
       IMGDF2.FLT
       IMMET2.FLT
       IMWMF2.FLT
       ISGDI32.DLL
       ISGDI32.INI
       TransMog.exe
       ReadMe.txt

3. Execute the command 'TransMog'
   This will result in a display of the correct parameters
   for converting the Books, namely:

      "The correct parameters for the Transmogrifier are:
       Transmog <bookname.boo> [New Book directory name]
       where '[]' is optional  "




Execution

File and Directory names, and Directory paths, should conform
to the old DOS 8.3 convention (i.e. the 'shortname' convention).

From the command line, execute:
  Transmog <bookname.boo> [New Book directory]

       <bookname.boo>  the name of the Book to be converted
                 (a fully qualified file name may be used).


       [New Book Directory Name]  This is an optional parameter.
                 A fully qualified directory name may be used, or a
                 simple directory name, in which case the directory
                 will be created as a sub-directory of the current
                 directory. In the absence of such a name the
                 Transmogrifier will create one for you, named
                 'NewBooks', as a subdirectory of the current directory.

                 All converted books will be placed in this directory


  The Transmogrifer will respond with:
      <New Book Directory> directory has been created to hold the new book
      Book <bookname.boo>, Version <the book version number>
      <a series of characters>  (see below)
      Version 1.4 Book created and placed in <New Book Directory>


      If the New Book directory already exists then the first line
      ("<> directory has been...") will not be displayed.

      A crude progress monitor is included. This takes the form of a
      stream of characters directed to the screen. These characters
      indicate which particular process is being carried out.

             g   a  GDF picture is being converted to GIF
             m   an MMR picture is being converted to GIF
             C   a  CGM picture is being converted to GIF
             G   a  Metafile Bitmap is   converted to GIF
             J   a  Metafile Bitmap is   converted to JPEG
             V   a  Metafile Vector is   converted to GIF
             h   the Book header is created
             x   a dummy index is being created
             L   the Low Resolution Pictures are added
             O   the Object Data (High res.Pictures) added
             D   the Object Descriptions are added
             T   the Text component of the Book is added
             N   the new Book is copied to the NewBook directory


      During the conversion process, the Transmogrifier will create
      a temporary directory named <bookname>.PIC in the <bookname>
      directory.  This directory will contain some of the
      intermediary files created during the Book conversion process.
      If the Book conversions fails at some stage, the temporary
      directory will not be erased and a suitable error message
      will be produced.

      Examination of, the error message, the contents of the book
      subdirectory (bookname.pic), and the progress monitor, will
      give some indication of the cause of the error.


  If the Book does not contain any Pictures that require converting
  the Transmogrifier will respond with :
      "Book <bookname> contains no pictures."


  If the Book has already been converted, or was built by a version
  of BookManager Build that supports the Web-compliant picture
  formats, the Transmogrifier will respond with:
      "Book <bookname> is not a version 1.2 or 1.3 Book"







Limitations and known problems

    a. The code has not yet been optimized for speed, efficiency and
       size.



Please report all errors to yeadon@us.ibm.com, cc rrinda@us.ibm.com

Please send all requests for enhancements or clarifications to
yeadon@us.ibm.com, cc rrinda@us.ibm.com




For updates of this product, please visit the IBM BookManager Web site
at
    http://BookSrv2.raleigh.ibm.com


