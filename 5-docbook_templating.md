# DocBook templating {#docbook-templating}

## Preprocessing with freemarker {#preprocessing-with-freemarker}

### Description {#description-6}

Ant4docbook preprocess docbook files as _freemarker templates_ , to add variables and conditions if needed.

### Preprocessing parameters {#preprocessing-parameters}

### Examples {#examples-5}

DocBook file with freemarker instructions :

_<?xml version="1.0" encoding="utf-8"?>__&lt;article xml:lang="en"&gt;__&lt;title&gt;$ {custom_title}&lt;/title&gt;__&lt;section id="section1"&gt;__&lt;title&gt;Section level 1&lt;/title&gt;__&lt;para&gt;__write your documentation with some conditions__[# if (output_format_is_pdf)??]__&lt;xref linkend="appendix-xxx" /&gt;__[# else]__&lt;ulink url="appendix-xxx.html"&gt;appendix-xxx&lt;/ulink&gt;__[/ #if]__&lt;/para&gt;__&lt;/section&gt;__&lt;/article&gt;_

Ant script with freemarker parameters :

_&lt;project name="ant-project" default="docbbook-preprocessing"&gt;__&lt;target name="docbbook-preprocessing"&gt;__<!-- define &lt;dbk&gt; ant task here, with preprocessor parameter set to true -->__&lt;dbk file="docbook.xml" tofile="file.html" preprocessor="true"&gt;__&lt;parameter name="custom_title" value="My Custom Title" /&gt;__&lt;/dbk&gt;__&lt;dbk file="docbook.xml" tofile="file.pdf" preprocessor="true"&gt;__&lt;parameter name="custom_title" value="My Custom Title" /&gt;__&lt;parameter name="output_format_is_pdf" value="true" /&gt;__&lt;/dbk&gt;__&lt;/target&gt;__&lt;/project&gt;_