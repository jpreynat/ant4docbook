## DocBook to pdf {#docbook-to-pdf}

### Description {#description}

Process docbook to pdf within ant script, using _DocBook XSL stylesheets_ and _XSL Formatting Objects_.

By default, ant4docbook embed apache fop to process pdf files.You may use your favorite fo processor as an external tool by setting property. For example :

_&lt;project name="docbook-ant-task-to-pdf"&gt;__&lt;property name="ant4docbook.fop" value="/path/to/apache-fop/fop" /&gt;__[...]__&lt;/project&gt;_

### Pdf task parameters {#pdf-task-parameters}

### Examples {#examples}

_&lt;project name="docbook-ant-task-to-pdf" default="docbook-to-pdf"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-pdf"&gt;__&lt;dbk file="docbook.xml" tofile="generated-pdf-file.pdf" /&gt;__&lt;/target&gt;__&lt;target name="docbook-to-pdf-with-many-parameters"&gt;__<dbk file="docbook.xml" tofile="generated-pdf-file.pdf"__parameters="pdf.properties" />__&lt;/target&gt;__&lt;target name="docbook-to-pdf-with-some-parameters"&gt;__&lt;dbk file="docbook.xml" tofile="generated-pdf-file.pdf"&gt;__&lt;parameter name="paper.type" value="A4" /&gt;__&lt;/dbk&gt;__&lt;/target&gt;__&lt;/project&gt;_