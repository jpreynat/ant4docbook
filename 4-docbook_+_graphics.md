# Docbook + Graphics {#docbook-graphics}

## DocBook and plantuml {#docbook-and-plantuml}

### Description {#description-5}

_Plantuml_ is a modeling language to create _UML_ diagrams (use case, class, sequence, activity, component, state, ...).

Ant4docbook aims to:

*   easy convert plantuml to svg or png, using _ant + plantuml_.
*   easy xinclude plantuml in docbook documents.

### Installation {#installation-0}

Please install (linux debian):$ apt-get install graphviz

### Examples {#examples-4}

docbook-plantuml.xml

_<?xml version="1.0" encoding="utf-8"?>__&lt;article xmlns:xi="http://www.w3.org/2001/XInclude"&gt;__&lt;title&gt;Test xinclude plantuml&lt;/title&gt;__&lt;xi:include href="diagram.plantuml"/&gt;__&lt;/article&gt;_

diagram.plantuml

_\@startuml__Alice -> Bob: Authentication Request__Bob --> Alice: Authentication Response__Alice -> Bob: Another authentication Request__Alice <-- Bob: another authentication Response__\@enduml_

build.xml

_&lt;project name="docbook-plantuml" default="docbook-and-plantuml"&gt;__<taskdef name="dbk"__classname="net.sourceforge.ant4docbook.taskdefs.DocbookTask"__classpath="PATH/TO/ant4docbook.jar"/>__&lt;target name="docbook-plantuml"&gt;__&lt;dbk file="docbook-plantuml.xml" tofile="docbook-plantuml.pdf" /&gt;__&lt;/target&gt;__&lt;/project&gt;_

see: _docbook-plantuml.pdf_