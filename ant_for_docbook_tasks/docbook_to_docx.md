## DocBook to docx {#docbook-to-docx}

FUTURE RELEASE (experimental)

### Description {#description}

Existing docx stylesheets _DocBook XSL stylesheets_ seems to be limited.The idea is to process docbook to docx within ant script, using a custom processor based on _docx4java_.

The beginning of the development is commited on the sourceforge repository. See dev/src/java/net/sourceforge/ant4docbook/processors/DocxProcessor.java. Some efforts are needed to continue the development and contributions are welcome.

### Docx task parameters {#docx-task-parameters}

### Examples {#examples}

_&lt;project name="docbook-ant-task-to-docx" default="docbook-to-docx"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-docx"&gt;__&lt;dbk file="docbook.xml" tofile="generated-docx-file.docx" /&gt;__&lt;/target&gt;__&lt;/project&gt;_