###############################################################################
###############################################################################

DATE

This document was written on 12 September 2021

###############################################################################
###############################################################################

ABOUT

These files are a part of the Mahāvīrī LaTeX Source Code. This is the first book I have typeset in LuaLaTex with Harfbuzz rendering. Harfbuzz rendering allows Unicode Devanagari text to be correctly copy-pasted and searched using many PDF viwers (including Chrome and PDF viewers on Android devices, there are some issues with Acrobat Reader though). I thank Shreevatsa R for introducing me to Harfbuzz renderer. The full book is freely downloadable and so the source code is also released for free to help other Indic book designers typeset Indic books using LaTeX/LuaLaTeX.

###############################################################################
###############################################################################

BOOK DETAILS

The book details (in Hindi) are in the file BOOKINFORMATION.

###############################################################################
###############################################################################

INSTRUCTIONS TO COMPILE

1) Unzip the zipped file for Mahāvīrī LaTeX Source Code. There are three subfolders: Cover, Plate, and Book. The Cover and Plate code needs to be compiled first and the Book code last. The cover and plate design of the book was done using pstricks which does not work with LuaLaTex. For this reason, they were compiled using XeLaTeX. The Cover was compiled using TeX Live version 2019 while the plate using TeX Live version 2020.

2) Get the fonts (TTF files). The book was designed using these four fonts: Arial Unicode MS (for unicode symbols), Charis SIL (for IAST with diacritics), Chanakya Sanskrit (for Devanagari), and Rupee Foradian (for rupee symbol). Put the files in the same directory as the LaTeX source. Charis SIL and Rupee Foradian are free fonts, Arial Unicode MS and Chanakya Sanskrit are not. The fonts are not provided with this source code. If you do not have these fonts, then you may use any other Unicode fonts (the final output will be different from the book PDF) and accordingly change the font name in the lines with the \setmainfont and \newfontfamily commands 

3) Compile the file main.tex in the Cover subfolder using XeLaTeX. This was done using XeLaTeX, TeX Live version 2019. This will generate the cover PDF.

4) Compile the file main.tex in the Plate subfolder using XeLaTeX. This was also done using XeLaTeX, TeX Live version 2020. This will generate the plate PDF.

5) Put the cover and plate PDFs in the Book subfolder. 

6) Compile the file main.tex in the Book subfolder using LuaLaTeX. This was done using LuaLaTeX, TeX Live version 2020. This will generate the book PDF.

###############################################################################
###############################################################################

NOTE: The TeX files in the Book subfodler are not coded manually but generated from a set of shell scripts from an XML source which uses a non-standard custom XML. The XML files and the shell scripts are currently not available for public use.

###############################################################################
###############################################################################

ISSUES

1) One pain with LuaLaTeX was that I could not make pstricks work in it. This is disappointing since pstricks is so good for designing book plates and book covers. After spending a lot of time to make pstricks work without any result, I finally decided to design the book cover and plate in XeLaTeX. As the cover and plate was in XeLaTeX, I had to switch to importing images (and not PDFs) for the PDF I created to be uploaded on Acadmeia here: https://www.academia.edu/50965409/. Had I not done this and imported PDFs created in XeLaTeX the Devanagari glyphs on the cover would have been messed up. 

2) An unexpected outcome I noticed is that seamless copy-pasting and searching is not possible in all PDF viewers. For example, when I open the PDF in Chrome and copy-paste the contents of the title page, I get the below in Unicode with no error and can search for विशिष्टशब्दार्थ

(मूलपाठ, विशिष्टशब्दार्थ, सामान्यार्थ, व्याख्या,
पद्यार्धानुक्रमणी, और शब्दानुक्रमणी सहित
भक्तशिरोमणि गोस्वामी तुलसीदासकी सिद्ध रचना)

But when I open the PDF in Adobe Acrobat Reader DC (my version is 2021.005.20060) on Windows and copy-paste the contents of the title page, this is what I get with random space characters inserted. 

(मूलपाठ, वि शि ष्टशब्दार्थ , सामान्यार्थ , व्याख्या,
पद्यार्धा नुक्रमणी, और शब्दानुक्रमणी सहि त
भक्तशि रोमणि गोस्वामी तुलसीदासकी सि द्ध रचना)

Even searching with विशिष्टशब्दार्थ is not successful, one has to search for वि शिष्ट शब्दार्थ to find the string in the PDF in Acrobat Reader. Shreevatsa R informed me that even on Adobe Acrobat Reader DC 2021.005.20058 on macOS, the copy-pasting is not perfect and the output is with spaces like "मूलपाठ, वि शि ष्टशब्दार्थ , सामान्यार्थ , व्याख्या," etc on 

Chrome seems to handle the rendering perfectly, but not Adobe Acrobat. I have not tried other PDF viewers on my laptop. On my Android phone (Redmi K20 Pro), the copy-pasting is perfect as in Chrome and I can search for विशिष्टशब्दार्थ. Even on my old Android phone from 2016 (Samsung Galaxy J7 Prime), the copy-pasting is perfect and I can search for विशिष्टशब्दार्थ. 


