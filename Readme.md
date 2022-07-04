# AGCF Media Team Document

## Website Creation Step by Step
### Create site folder
```
PS C:\Andrew\prj> hugo new site media
Congratulations! Your new Hugo site is created in C:\Andrew\prj\media.
Just a few more steps and you're ready to go:
1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".
Visit https://gohugo.io/ for quickstart guide and full documentation.

PS C:\Andrew\prj> cd media
PS C:\Andrew\prj\media> git init
Initialized empty Git repository in C:/Andrew/prj/media/.git/
```
### Add `relearn` theme
```
PS C:\Andrew\prj\media> git submodule add https://github.com/McShelby/hugo-theme-relearn.git themes/relearn
Cloning into 'C:/Andrew/prj/media/themes/relearn'...
remote: Enumerating objects: 122240, done.
remote: Counting objects: 100% (32171/32171), done.
remote: Compressing objects: 100% (8891/8891), done.
remote: Total 122240 (delta 15927), reused 32150 (delta 15912), pack-reused 90069
Receiving objects: 100% (122240/122240), 63.94 MiB | 7.31 MiB/s, done.
Resolving deltas: 100% (62370/62370), done.
warning: LF will be replaced by CRLF in .gitmodules.
The file will have its original line endings in your working directory
```
### Modify `config.toml` to use the theme
See the config file in the `exampleSite` under `relearn` theme for more details. 

Note: Theme name is the name under "theme" folder
```
# Use theme name "relearn" instead of "hugo-theme-relearn" because we add the theme using the following command
# git submodule add https://github.com/McShelby/hugo-theme-relearn.git themes/relearn
theme = "relearn"
```

### Create chapter page
Chapters are pages that contain other child pages(content pages). You can think chapter as a container(folder).
It has a special layout style and usually just contains a chapter name, the title and a brief abstract of the section.
```
hugo new --kind chapter applications/_index.md
```

### Create content pages
Create content pages inside the chapter. Here are two ways to create content in the chapter:

```
// 1. As single file; it's simple
hugo new basics/first-content.md

// 2. As a folder with _index.md; You can create sub-folder to hold all the assets used by this page
hugo new basics/second-content/_index.md
```

### Test & Run
```
hugo serve
```

```
CUSTOMIZE YOUR OWN HOME PAGE
The site is working. Don't forget to customize this page with your own. You typically have 3 choices :

1. Create an _index.md document in content folder and fill it with Markdown content
2. Create an index.html file in the static folder and fill the file with HTML content
3. Configure your server to automatically redirect home page to one your documentation page
```
