# Ant for docbook tasks {#ant-for-docbook-tasks}

## DocBook ant task &lt;dbk&gt; {#docbook-ant-task-dbk-}

### Description {#description}

Ant4docbook is an ant task for processing docbook xml documents.see : _http://ant.apache.org/_see : _http://www.docbook.org/_

Ant4docbook transforms docbook files into other formats using :

*   _DocBook XSL stylesheets_ and XSL Formatting Objects,

see : _docbook to html_see : _docbook to pdf_see : _docbook to epub_

*   Custom docx processor using _docx4java_see :

Ant4docbook preprocess docbook files using _freemarker engine_ to add variables and conditions on docbook files.see : _Templating with freemarker_

### Encoding {#encoding}

By default, all files are processed as UTF-8.

### DocBook task properties {#docbook-task-properties}

DocBook task have parameters and inner elements to define behavior. Nevertheless, some global properties are useful to set some specific points.

## DocBook to html {#docbook-to-html}

### Description {#description-0}

Process docbook to html within ant script, using _DocBook XSL stylesheets_.

### Html task parameters {#html-task-parameters}

### Examples {#examples}

_&lt;project name="docbook-ant-task-to-html" default="docbook-to-html"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-html"&gt;__&lt;dbk file="docbook.xml" tofile="generated-html-file.html" /&gt;__&lt;/target&gt;__&lt;target name="docbook-to-html-with-many-parameters"&gt;__<dbk file="docbook.xml" tofile="generated-html-file.html"__parameters="html.properties" />__&lt;/target&gt;__&lt;target name="docbook-to-html-with-some-parameters"&gt;__&lt;dbk file="docbook.xml" tofile="generated-html-file.html"&gt;__&lt;parameter name="section.autolabel" value="1" /&gt;__&lt;parameter name="toc.section.depth" value="3" /&gt;__&lt;/dbk&gt;__&lt;/target&gt;__&lt;/project&gt;_

## DocBook to pdf {#docbook-to-pdf}

### Description {#description-1}

Process docbook to pdf within ant script, using _DocBook XSL stylesheets_ and _XSL Formatting Objects_.

By default, ant4docbook embed apache fop to process pdf files.You may use your favorite fo processor as an external tool by setting property. For example :

_&lt;project name="docbook-ant-task-to-pdf"&gt;__&lt;property name="ant4docbook.fop" value="/path/to/apache-fop/fop" /&gt;__[...]__&lt;/project&gt;_

### Pdf task parameters {#pdf-task-parameters}

### Examples {#examples-0}

_&lt;project name="docbook-ant-task-to-pdf" default="docbook-to-pdf"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-pdf"&gt;__&lt;dbk file="docbook.xml" tofile="generated-pdf-file.pdf" /&gt;__&lt;/target&gt;__&lt;target name="docbook-to-pdf-with-many-parameters"&gt;__<dbk file="docbook.xml" tofile="generated-pdf-file.pdf"__parameters="pdf.properties" />__&lt;/target&gt;__&lt;target name="docbook-to-pdf-with-some-parameters"&gt;__&lt;dbk file="docbook.xml" tofile="generated-pdf-file.pdf"&gt;__&lt;parameter name="paper.type" value="A4" /&gt;__&lt;/dbk&gt;__&lt;/target&gt;__&lt;/project&gt;_

## DocBook to epub {#docbook-to-epub}

### Description {#description-2}

Process docbook to epub within ant script, using _DocBook XSL stylesheets_.

### Epub task parameters {#epub-task-parameters}

### Examples {#examples-1}

_&lt;project name="docbook-ant-task-to-epub" default="docbook-to-epub"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-epub"&gt;__&lt;dbk file="docbook.xml" tofile="generated-epub-file.epub" /&gt;__&lt;/target&gt;__&lt;/project&gt;_

## DocBook to docx {#docbook-to-docx}

FUTURE RELEASE (experimental)

### Description {#description-3}

Existing docx stylesheets _DocBook XSL stylesheets_ seems to be limited.The idea is to process docbook to docx within ant script, using a custom processor based on _docx4java_.

The beginning of the development is commited on the sourceforge repository. See dev/src/java/net/sourceforge/ant4docbook/processors/DocxProcessor.java. Some efforts are needed to continue the development and contributions are welcome.

### Docx task parameters {#docx-task-parameters}

### Examples {#examples-2}

_&lt;project name="docbook-ant-task-to-docx" default="docbook-to-docx"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-docx"&gt;__&lt;dbk file="docbook.xml" tofile="generated-docx-file.docx" /&gt;__&lt;/target&gt;__&lt;/project&gt;_