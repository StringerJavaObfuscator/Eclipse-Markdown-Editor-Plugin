## Eclipse Plugin Protection

This fork of the simple Eclipse plugin (https://github.com/winterstein/Eclipse-Markdown-Editor-Plugin) is to demonstrate how to Stringer protection for this kind of applications.

## Description
- https://jfxstore.com/stringer/docs#maven-plugin

## Requirements
- Maven
- Stringer Standard or Enterpise with a valid license

## Configuring 
Install Stinger and Stringer Maven plugin to local Maven repository:

```
mvn install:install-file -Dfile=`pwd`/stringer.jar -DpomFile=`pwd`/stringer.pom
mvn install:install-file -Dfile=`pwd`/stringer-annotations.jar -DpomFile=`pwd`/stringer-annotations.pom
mvn install:install-file -Dfile=`pwd`/stringer-maven-plugin.jar -DpomFile=`pwd`/stringer-maven-plugin.pom
```

## Building

```
mvn clean install
```

## Installation of the protected plugin:
1. Run Eclipse
1. Open the installation dialog from the main menu Help -> Install
1. Click to the "Add..." button to add custom update site
1. Click to the "Archive..." button and choose the archive Eclipse-Markdown-Editor-Plugin/site/target/markdown.editor.site-1.2.0-SNAPSHOT.zip
![Plugin Installation](img/install.png)
1. Install the plugin and restart Eclipse

## Stringer Protection Examples
Examples below show Stringer protection for classes.

### A class without protection 
![Not Protected Class](img/class.png)

### The class protected by Stringer
![Protected Class](img/class_protected.png)

# Eclipse Markdown Editor Plugin

[![Build Status](https://secure.travis-ci.org/winterstein/Eclipse-Markdown-Editor-Plugin.png)](http://travis-ci.org/winterstein/Eclipse-Markdown-Editor-Plugin)
<a href="http://marketplace.eclipse.org/marketplace-client-intro?mpc_install=369" 
title="Drag and drop into a running Eclipse toolbar area to install Markdown Text Editor">
  <img src="https://marketplace.eclipse.org/sites/all/modules/custom/marketplace/images/installbutton.png"/>
</a>

Edit .md and .txt files with syntax highlighting.   
Provides Outline and Preview HTML views.

Please see the website for information:
<http://www.winterwell.com/software/markdown-editor.php>

Eclipse Marketplace entry:
<http://marketplace.eclipse.org/content/markdown-text-editor>  
or install with [Nodeclipse CLI Installer](https://github.com/Nodeclipse/nodeclipse-1/tree/master/org.nodeclipse.ui/templates) `nodeclipse install markdown`

There is also a complementary GitHub Flavoured Markdown Viewer
<https://github.com/satyagraha/gfm_viewer>


## Usage

![](http://marketplace.eclipse.org/sites/default/files/Markdown-Editor-1.1.0.PNG)

Note that for HTML preview OS the internal browser is used, e.g. Internet Explorer on Windows; if you use Ubuntu or other Linux distros, we recommend the WebKit browser; see:

- <http://www.eclipse.org/swt/faq.php#browserlinuxrcp>
- <http://www.eclipse.org/swt/faq.php#browserlinux>
- <http://tronprog.blogspot.de/2012/05/eclipse-internal-web-browser-in-kubuntu.html>

## Eclipse Dev Details

You need Eclipse with PDE, e.g. Eclipse Standard



![](overview.png)

Main Editor class `winterwell.markdown.editors.MarkdownEditor` defined as

      <editor
            name="Markdown Editor"
            extensions="txt,md"
            icon="icons/notepad.gif"
            contributorClass="winterwell.markdown.editors.ActionBarContributor"
            class="winterwell.markdown.editors.MarkdownEditor"
            id="winterwell.markdown.editors.MarkdownEditor">
      </editor>

### Build

	mvn package
      
then check `site\target` directory for update site archive `markdown.editor.site-x.x.x.zip` and p2 repository.
Use Help -> Install New Software... -> Add... -> Archive to istall from .zip file.

Increase version

	mvn -Dtycho.mode=maven org.eclipse.tycho:tycho-versions-plugin:set-version -DnewVersion=1.2.0-SNAPSHOT

### History

- 1.0
- 1.1 (24 Feb 2014) by Telmo Brugnara @tbrugz #40
  - Rich color preferences #35 #37
- 1.2 (Jan 2015) by Olivier Martin @oliviermartin #52
  - Update preview when the file is saved #48
  - MultiMarkdown metadata #49
  - GitHub code blocks #50
  - detecting links #51
  - open GFM View from Markdown View #53

<a href="http://with-eclipse.github.io/" target="_blank"><img alt="with-Eclipse logo" src="http://with-eclipse.github.io/with-eclipse-1.jpg" /></a>
