# Hints

## Aptana Studio

![Aptana-with-Nodeclipse.png](Pictures/Aptana-with-Nodeclipse.png)

Before 0.4 was issue [#15 Support black background color schemes](https://github.com/Nodeclipse/nodeclipse-1/issues/15).
Could be walked around by installing [Eclipse Color Theme](http://marketplace.eclipse.org/content/eclipse-color-theme) 
 and changing theme to [Roboticket](http://eclipsecolorthemes.org/?view=theme&id=93) or other white background.
Window->Preferences->General->Appearance->Color Theme

When debugging, the issue [#15](https://github.com/Nodeclipse/nodeclipse-1/issues/15) is still present, when Chromium Editor (JS Editor) is opened.
For your own sources be sure to use Nodeclipse Editor.

Aptana uses also cannot simply install Nodeclipse plugin, as Aptana will not resolute to get required (since 0.4) JSDT dependency.
The solution is provided in [Enide](http://marketplace.eclipse.org/content/enide-eclipse-nodejs-ide) is NJSDT (alternative to JSDT),
 or manually from `https://bitbucket.org/nexj/updatesite/raw/default` for NJSDT+NJSDoc (thanks to @johnpeb)  
The solution is also to install JSDT from Eclipse update site
`http://download.eclipse.org/releases/juno` or `http://download.eclipse.org/releases/kepler`

![Getting-JSDT.PNG](Pictures/Getting-JSDT.PNG)

Or you can take Nodeclipse NTS and add Aptana plugins.

## Select JVM for Eclipse instance

Add -vm option in [eclipse.ini](http://wiki.eclipse.org/Eclipse.ini), that is in Eclipse folder. Quote:

	Note the format of the -vm option - it is important to be exact:
    	The -vm option and its value (the path) must be on separate lines.
    	The value must be the full absolute or relative path to the Java executable, not just to the Java home directory.
    	The -vm option must occur before the -vmargs option, since everything after -vmargs is passed directly to the JVM. 

Example:

	...
	-vm
	C:\Program Files\Java\jdk1.7.0_11\bin\javaw.exe
	-vmargs
	-Xms40m
	-Xmx512m

## Editors

### JavaScript Editors

In Eclipse ecosystem there are a lot of JavaScript Editors. Some examples:

- JSDT project
- VJET project
- Nodeclipse ships with it's own Node Editor and ...
- JS Editor (from Chromium project)

### JavaScript Code Assist

Eclipse standard [JavaScript Development Tools (JSDT)](http://www.eclipse.org/webtools/jsdt/)
 ([wiki](http://wiki.eclipse.org/JSDT))
 already includes JavaScript Editor with Code/Content Assist function.  
 
Go to Preferences->JavaScript->Editor->Content Assist 

![Eclipse-Preferences-JavaScript-Editor-ContentAssist.png](Pictures/Eclipse-Preferences-JavaScript-Editor-ContentAssist.png)

> **Inferred Types**
> 
> In order for some JDT-based functionality (such as code completion) to work correctly,
> class type information needs to be available. This information is not available in JavaScript,
> but it can be inferred in many cases.

Code assist for some libraries and framework is provided as extensions, for example
[Code assist for jQuery](http://marketplace.eclipse.org/content/jsdt-jquery).

### CoffeeScript Editor

Use [CoffeeScriptSet.p2f](https://raw.github.com/Nodeclipse/eclipse-node-ide/master/CoffeeScriptSet.p2f)
to [quickly install](http://marketplace.eclipse.org/content/coffeescript-editor-quick-installer).  
Warning: this plugin created by Adam Schmideg was not updated for a year.
see [About CoffeeScript support in Nodeclipse](http://www.nodeclipse.org/2013/06/02/Coffee.html)

![CoffeeScriptEditor.png](Pictures/CoffeeScriptEditor.png)


### JSON Editor

![Eclipse-Configure-JSON-Association.PNG](Pictures/Eclipse-Configure-JSON-Association.PNG)

JSON means JavaScript Object Notation, so you just have to have any JavaScript editor 
and associate the *.json files with it (this is default since Nodeclipse 0.4):

    Window > Preferences
    General > Editors > File Associations
    Add... > File type: *.json
    Select *.json file type > Add... (Associated editors) > JavaScript Editor
    Make it default

Now you can now open JSON files with the JavaScript editor (with syntax highlight),
 use the formatter and set your favorite color theme with Eclipse Color Theme.

![Eclipse-Preferences-FileAssociations.png](Pictures/Eclipse-Preferences-FileAssociations.png)

Alternatively, if you need/like good Outline, you can install JSON Editor plugin.

![JSON-Editor.png](Pictures/JSON-Editor.png)

### Editor Minimap

There is experimental support for minimap.

![Nodeclipse-with-Minimap.png](Pictures/Nodeclipse-with-Minimap.png)

(Only in Nodeclipse [NTS](http://www.nodeclipse.org/nts/), close when don't like)

## Launch npm

1. (Switch to Node perspective)

2. run as ->  npm....

![run-npm-at-project.jpg](Pictures/run-npm-at-project.jpg)

See also [npm documentation](https://npmjs.org/doc/)


Thank to George Pang for question.

## Start Explorer or Shell

Right-click folder in Project Explorer or selected path in an Editor, then

![StartExplorer.png](Pictures/Plugins/StartExplorer.png)

## Git

Press Ctrl+Shift+3 to commit current file or file set.

### Update several Git repositories at once

Just select them with mouse (holding Ctrl)  
Right-click any of them Team -> Pull  
See result.

![EGit-update-several-repositories-at-oce.png](Pictures/EGit-update-several-repositories-at-oce.png)

### Conflict resolution

When pulling, EGit (as any Git) does fetch then merge.  
EGit will show error message if change conflict has happened. And Merging will stop.

You can use Team -> Synchronize, to compare local git workspace and with git repository.

![EGit-status-icons.png](Pictures/EGit-status-icons.png)

Then you may select Replace With -> Branch, Tag, or Reference...

![EGit-replace-with-remote](Pictures/EGit-replace-with-remote.png) 

### GitHub Flavored Markdown (GFM) Viewer

See markdown .md files as they are on GitHub. Very useful when browsing `node_modules` folder. Minimum recommended version is 1.1.1 .

![Eclipse-Node-IDE-Overview-0.4.3.png](Pictures/Eclipse-Node-IDE-Overview-0.4.3.png)

To open GFM View right click any .md file and select <kbd>Show in GFM view</kbd>. (Since 1.1.1 in Enide 0.4.10)

### Connect Eclipse to GitHub issues

STS comes with EGit and GitHub support, that includes
 [Mylyn GitHub Connector](http://marketplace.eclipse.org/content/github-mylyn-connector).
<a href="http://marketplace.eclipse.org/marketplace-client-intro?mpc_install=1147" class="drag">
<img src="http://marketplace.eclipse.org/sites/all/modules/custom/marketplace/images/installbutton.png"></a>

![Mylyn-Add-Task-Repository.png](Pictures/Mylyn-Add-Task-Repository.png)

![Mylyn-Add-Task-Repository-Credentials.png](Pictures/Mylyn-Add-Task-Repository-Credentials.png)

You need to add at least 1 query

![Mylyn-Query-Add.png](Pictures/Mylyn-Query-Add.png)

![Mylyn-Result.png](Pictures/Mylyn-Result.png)

See more at [GitHub:teach](http://teach.github.com/articles/github-issues-cheatsheet/):

- [Tips and Tricks: Using Eclipse with GitHub(http://eclipsesource.com/blogs/2012/08/28/tips-and-tricks-using-eclipse-with-github/)  by Ian Bull
- [GitHub Eclipse page](http://eclipse.github.com/)

## REST Client

![Rest-Client-View.png](Pictures/Rest-Client-View.png)

This one has not been updated for a long while. [Sources are still on SVN](http://svn.codespot.com/a/eclipselabs.org/restclient-tool/).

## Shell script support

Install Eclipse-addons.p2f

![Shell-script-support.PNG](Pictures/Shell-script-support.PNG)
