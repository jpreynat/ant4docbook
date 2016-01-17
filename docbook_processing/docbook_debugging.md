## DocBook debugging {#docbook-debugging}

Ant4docbook let you process docbook step by step to debug errors :

1.  docbook to xml, to process xinclude
2.  docbook to fo
3.  fo to pdf

Example :

_&lt;project name="docbook-debugging" default="debug-pdf"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="validate-dtd-or-not"&gt;__&lt;property name="ant4docbook.dtd.validating" value="true*|false"/&gt;__&lt;dbk file="docbook.xml" tofile="docbook.xinclude.xml" /&gt;__&lt;/target&gt;__&lt;target name="debug-pdf"&gt;__&lt;dbk file="docbook.xml" tofile="docbook.xinclude.xml" /&gt;__&lt;dbk file="docbook.xinclude.xml" tofile="docbook.fo" /&gt;__&lt;dbk file="docbook.fo" tofile="docbook.pdf" /&gt;__&lt;/target&gt;__&lt;target name="debug-html"&gt;__&lt;dbk file="docbook.xml" tofile="docbook.xinclude.xml" /&gt;__&lt;dbk file="docbook.xinclude.xml" tofile="docbook.html" /&gt;__&lt;/target&gt;__&lt;target name="debug-with-your-xsl-stylesheet"&gt;__<dbk file="docbook.xml" tofile="custom-docbook.xml"__stylesheet="/path/to/your/xsl/stylesheet" />__&lt;/target&gt;__&lt;/project&gt;_