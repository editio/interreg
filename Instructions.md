José Luis Losada Palenzuela: TEI Workshop's materials (Międzygórze)
 
# INSTRUCTIONS 

## TOOL (VScode)

If not already done, install [Visual Studio Code](https://code.visualstudio.com). Follow the instructions on the page.

You need to install also the extensions *Scholarly XML* and *XML Tools*. `View > Extensions > Search extensions in the Marketplace`.

- Open the file `TEI-File.xml` in VScode (ie., drag and drop it to VSCode)
- Change the name (directly or in `File > Save As`.  Keep the extension `.xml`)
- Tip: save it in the same place of the exercise.

## TRANSCRIPTION.

- Remove the dummy text "Some text here." between the opening `<p>` and the closing `</p>` within the `<body>` element. 
- Transcribe from the scan “Lope-sonnet-scan-PL-1965.pdf” the sonnet in Polish  (... or use the transcription provided “Lope-sonnet-PL-Transcript-1965.txt”).
- Insert (or transcribe directly) the text into the opening `<p>` and the closing `</p>`.

The document should be now well-formed (`✓ XML Valid` on the bottom left-hand corner). 

## ENCODING.

You are encoding a sonnet, so you need to add these elements:

`<l>`: verse line. `<lg>`: line group (verse lines functioning as a formal unit, e.g.: sonnet: 14 verses lines; quatrain: 4 verses lines; tercet: 3 verses lines). 

- Start removing the opening `<p>` and the closing `</p>`, we don't need them for a sonnet.
- Don't worry about the error `ⓧ XML is not valid` (it means the document is not, yet, well-formed).  
- Surround the first verse line with a the opening `<l>` and the closing `</l>`. 
- Proceed the same way with all lines.
- Tip! You can try a shortcut: Highlight the verse line, press Ctrl/CMD-e, and in the contextual menu type 'l', for the element name).

The document should be now well-formed (`✓ XML Valid` on the bottom left-hand corner).

- Now encode all line groups, i.e., the sonnet, the 2 quatrains and 2 tercets. Surround with `<lg> </lg>` all verses lines (that is the whole sonnet) and go on successively for each quatrain and tercet. The structure should look like:

```xml
<lg> 
    <lg>
        <l>...</l>
        <l>...</l>
        <l>...</l>
        <l>...</l>
    </lg>
    [...]
</lg>
```

Have a look at the file provided “Lope-sonnet-empty.xml” if you have trouble getting it done.  

- Add now the attributes to mark up the strophes and the number lines (remember to add the quotation marks):

`<lg type="sonnet">`: line group for the whole poem.
`<lg type="quatrains">`: line group for a quatrain.
`<lg type="tercets">`: line group for a tercet.
`<l n="1">`: verse line number. 


## ENCODING METADATA (`<teiHeader>`).

Add some descriptive information to your file, e.g., a title to your edition.  

- Add a tittle and an author: `titleStmt -> title`, `titleStmt -> author`.

- Add some bibliographic information to your file. Use the bibliographic information provided in the transcription "Lope-sonnet-PL-Transcript-1965.txt"

```xml
<sourceDesc>
    <bibl>[...]</bibl>
</sourceDesc>
``` 

You can be more precise in the bibliographic reference. Inside you need to add following elements and one attribute: 

```xml
<title>
<editor role="tłumacz">
<pubPlace>
<publisher>
<date>
```

## VISUALIZATION on the Web browser

It is possible to display XML directly in the browser by adding a CSS stylesheet to the XML document.

- Copy the "visualize-tei-xml.css" file that comes with the materials and add it to the same location where you saved your encoded sonnet (if you saved it in the same folder as the exercise, the CSS file is already there).
- Add at the beginning of the XML document, before the root element `<TEI>`, the following instruction (which tells the XML where to find the CSS). You must have the XML file and the CSS file in the same folder.

`<?xml-stylesheet type="text/css" href="visualize-tei-xml.css"?>`

- Browser: open the XML file in your browser (dragging/dropping it into the browser may help).

- Familiar with CSS stylesheet? Open it in VSCode and play around with it.

## DID YOU FINISH ALREADY?

Violante or Violente? 'Violente' in the Polish version is a typo, so go for it and encode the correction.

- Search in the [TEI Guidelines](https://www.tei-c.org/release/doc/tei-p5-doc/de/html/ref-choice.html) for a solution looking for 'choice' (`<choice>`, `<sic>`, `<corr>`).

The first letter in the original is highlighted. Do we encode it?

- Search in the [TEI Guidelines](https://www.tei-c.org/release/doc/tei-p5-doc/de/html/ref-hi.html) for a solution looking for 'hi' (`<hi>`) and the attribute @rend.

* I provided you with a TEI-XML file already encoded “Lope-sonnet-1965-done.xml”. Feel free to have a look inside or ask me for help.