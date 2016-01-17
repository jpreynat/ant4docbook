## DocBook to epub {#docbook-to-epub}

### Description {#description}

Process docbook to epub within ant script, using _DocBook XSL stylesheets_.

### Epub task parameters {#epub-task-parameters}

### Examples {#examples}

_&lt;project name="docbook-ant-task-to-epub" default="docbook-to-epub"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-epub"&gt;__&lt;dbk file="docbook.xml" tofile="generated-epub-file.epub" /&gt;__&lt;/target&gt;__&lt;/project&gt;_