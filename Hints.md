# Hints

## JSON Editor

![Eclipse-Configure-JSON-Association.PNG](Pictures/Eclipse-Configure-JSON-Association.PNG)

JSON means JavaScript Object Notation, so you just have to have any JavaScript editor 
and associate the *.json files with it:

    Window > Preferences
    General > Editors > File Associations
    Add... > File type: *.json
    Select *.json file type > Add... (Associated editors) > JavaScript Editor
    Make it default

Now you can now open JSON files with the JavaScript editor (with syntax highlight),
 use the formatter and set your favorite color theme with Eclipse Color Theme.

![Eclipse-Preferences-FileAssociations.png](Pictures/Eclipse-Preferences-FileAssociations.png)


## Launch npm

1. (Switch to Node perspective)

2. run as ->  npm....

![run-npm-at-project.jpg](Pictures/run-npm-at-project.jpg)

See also [npm documentation](https://npmjs.org/doc/)


Thank to George Pang for question.

## Connect Eclipse to GitHub issues

Eclipse Juno 4.2.2 come with EGit and GitHub support, that includes Mylyn GitHub Connector

![Mylyn-Add-Task-Repository.png](Pictures/Mylyn-Add-Task-Repository.png)

![Mylyn-Add-Task-Repository-Credentials.png](Pictures/Mylyn-Add-Task-Repository-Credentials.png)

You need to add at least 1 query

![Mylyn-Query-Add.png](Pictures/Mylyn-Query-Add.png)

![Mylyn-Result.png](Pictures/Mylyn-Result.png)

## Shell script support

Install Eclipse-addons.p2f

![Shell-script-support.PNG](Pictures/Shell-script-support.PNG)
