---
title: React with Webpack File Structure
localeTitle: 与Webpack文件结构反应
---
现在是时候在编写任何代码之前设置我们的文件结构了。

首先，让我们创建一个名为`.gitignore`的新文件：
```
touch .gitignore 
```

此文件将包含我们将项目推送到GitHub时**不**包含的所有文件和文件夹的列表。有一个网站为`.gitignore`文件提供样板代码，这非常有用，因为`.gitignore`文件通常可能相当冗长和冗长，我们可能会忘记一些我们希望Git忽略的文件或文件夹。

转到[https://www.gitignore.io/](https://www.gitignore.io/)并在搜索栏中键入`Node` ，然后单击`Generate` 。这将生成一个如下所示的文件：
```
# Created by https://www.gitignore.io/api/node 
 
 ### Node ### 
 # Logs 
 logs 
 *.log 
 npm-debug.log* 
 
 # Runtime data 
 pids 
 *.pid 
 *.seed 
 
 # Directory for instrumented libs generated by jscoverage/JSCover 
 lib-cov 
 
 # Coverage directory used by tools like istanbul 
 coverage 
 
 # Grunt intermediate storage (http://gruntjs.com/creating-plugins#storing-task-files) 
 .grunt 
 
 # node-waf configuration 
 .lock-wscript 
 
 # Compiled binary addons (http://nodejs.org/api/addons.html) 
 build/Release 
 
 # Dependency directories 
 node_modules 
 jspm_packages 
 
 # Optional npm cache directory 
 .npm 
 
 # Optional REPL history 
 .node_repl_history 
```

现在我们可以将其复制并粘贴到我们的`.gitignore`文件中。

请注意， `.gitignore`文件应始终包含`node_modules` 。这非常重要，因为我们不想将我们的`node_modules`文件夹包含在我们的Git提交中，因为它们占用了大量的磁盘空间，并且可以使用`npm install` ，它指向我们的`package.json` 。

我们的`.gitignore`文件中列出的大多数文件和文件夹在我们的项目中都不存在，但是如果他们将来这样做，它们将不会被包含在我们的Git提交中，这是重要且有用的，因为我们必须是选择我们的承诺。

现在，我们需要创建一个包含**开发**代码内容的新文件夹。我们称之为`src` ：
```
mkdir src 
```

然后，我们需要创建一个文件夹，其中包含我们用于**生产**目的的文件。我们将此文件夹称为`dist` ：
```
mkdir dist 
```

*   [帮助：有关`src`和`dist`文件夹的更多信息](http://stackoverflow.com/questions/23730882/what-is-the-role-of-src-and-dist-folders/23731040#23731040)

现在我们已经安装了我们的软件包并创建了空的`src`和`dist`文件夹，我们的树将看起来像这样（不包括`.gitignore` ，这是一个隐藏文件）：
```
. 
 ├── dist 
 ├── node_modules 
 ├── package.json 
 ├── src 
 └── webpack.config.js 
```

现在，我们可以创建一个进入`src`文件夹的新`js`文件夹。这将包含我们所有的React代码：
```
mkdir src/js 
```

我们可以继续在`src/js`创建一个空的`client.js` 。这将是我们的主要React文件：
```
touch src/js/client.js 
```

我们还需要一个**不应该**进入我们的`src`文件夹的`index.html` ，而不是我们的`dist`文件夹，因为它是**生成**我们的应用程序所必需的：
```
touch dist/index.html 
```

所以现在，我们的树看起来像这样：
```
. 
 ├── dist 
 │   └── index.html 
 ├── node_modules 
 ├── package.json 
 ├── src 
 │   └── js 
 │       └── client.js 
 └── webpack.config.js 

```