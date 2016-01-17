## DocBook to html {#docbook-to-html}

### Description {#description}

Process docbook to html within ant script, using _DocBook XSL stylesheets_.

### Html task parameters {#html-task-parameters}

### Examples {#examples}

_&lt;project name="docbook-ant-task-to-html" default="docbook-to-html"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-to-html"&gt;__&lt;dbk file="docbook.xml" tofile="generated-html-file.html" /&gt;__&lt;/target&gt;__&lt;target name="docbook-to-html-with-many-parameters"&gt;__<dbk file="docbook.xml" tofile="generated-html-file.html"__parameters="html.properties" />__&lt;/target&gt;__&lt;target name="docbook-to-html-with-some-parameters"&gt;__&lt;dbk file="docbook.xml" tofile="generated-html-file.html"&gt;__&lt;parameter name="section.autolabel" value="1" /&gt;__&lt;parameter name="toc.section.depth" value="3" /&gt;__&lt;/dbk&gt;__&lt;/target&gt;__&lt;/project&gt;_