# Docbook + Plain Text {#docbook-plain-text}

## Markdown and DocBook {#markdown-and-docbook}

### Description {#description-4}

_Markdown_ is a _lightweight markup languages_

*   easy to read,
*   easy to write,
*   easy to convert, (see _ant + pandoc_ )
*   _easy to xinclude_ in docbook documents. **This is (one of) the aim of ant4docbook.**

### Examples {#examples-3}

docbook-markdown.xml

_<?xml version="1.0" encoding="utf-8"?>__&lt;article xmlns:xi="http://www.w3.org/2001/XInclude"&gt;__&lt;title&gt;Test xinclude markdown&lt;/title&gt;__&lt;xi:include href="docbook-markdown.md"/&gt;__&lt;/article&gt;_

docbook-markdown.md

_A First Level Header__====================__A Second Level Header__---------------------__Now is the time for all good men to come to__the aid of their country. This is just a__regular paragraph.__The quick brown fox jumped over the lazy__dog's back.__### Header 3__> This is a blockquote.__>__> This is the second paragraph in the blockquote.__>__> ## This is an H2 in a blockquote_

build.xml

_&lt;project name="docbook-markdown" default="docbook-and-markdown"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__<!-- xinclude markdown -->__&lt;target name="xinclude-markdown"&gt;__&lt;dbk file="docbook-markdown.xml" tofile="docbook-markdown.pdf" /&gt;__&lt;/target&gt;__<!-- or process markdown -->__&lt;target name="process-markdown"&gt;__&lt;dbk file="markdown.md" tofile="markdown.html" /&gt;__&lt;/target&gt;__&lt;/project&gt;_

see: _docbook-markdown.pdf_