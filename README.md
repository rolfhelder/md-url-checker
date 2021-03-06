<h1>NodeJS Library - URL extractor and status checker</h1> 

<p align="center">
  <img src="https://img.shields.io/static/v1?label=NodeJS&message=16.15.1&color=green&style=for-the-badge&logo=typescript"/>
  <img src="https://img.shields.io/static/v1?label=License&message=MIT&color=blue"/>
  <img src="https://img.shields.io/static/v1?label=Repo_status&message=1.0.0&color=red"/>
</p>

<p align="center">
  <a href="#project">Project</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#technologies">Technologies</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#install">How to Install</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#use">How to Use</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#option">--options</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="#license">License</a>
</p>

<p align="center">
  Download at&nbsp;&nbsp; 
  <a href="https://github.com/rolfhelder/md-url-checker">Github</a>&nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://www.npmjs.com/package/md-url-checker">NPM</a>
</p>

<h2 id="project">๐ป Project</h2>

This is a NodeJS module to extract url links โ with an option to see if the links are broken or not โ from a markdown file or a file following markdown syntax of the type:

`[link](http(s)://domain.com/yadayada)`

The module returns an array of objects with the list of links found in the files within a folder especified when calling the module with the option to add the status code returned when acessing the url.

<h2 id="technologies">๐งช Technologies</h2>

Project developed using the following technologies:

- NodeJS

<h2 id="install">๐จ๐ปโ๐ง How to install</h2>

`npm install md-url-checker`

<h2 id="use">๐ค How to use</h2>

There are two ways to use this module

### Directly on terminal:

`md-url-checker folderPath --option` 

where,
   
- `folderPath`: is the relative or absolute path to the folder with the files you wish to analize.
- `--option`: is an available option as listed <a href="#option">here</a>.
option --check|-c

### Importing function getUrl()

getUrl(folderPath: 'string', option: 'string');

Use examples:

```JS

import checker from "md-url-checker";

checker.getUrl("./files"); // returns array of objects with links found in files
checker.getUrl("./files" , "--check"); // returns array of objects with links and status code
checker.getUrl("./files" , "-c"); // returns array of objects with links and status code
```

The first example returns an array of arrays โ if there are multiple files in `./files`โ with the format:

```JS
[
  [
    {
      LinkFoo: 'https://bar.barz',
    }
  ]
  [
    {
      LinkDarth: 'https://darkside.join/how-to-increase-your-power-10x',
    }
  ]
]
```

The second and third examples are equivalent and return an array of arrays โ if there are multiple files in `./files`โ with the format:

```JS
[
  [
    {
      LinkFoo: 'https://bar.barz',
      status: '200 - OK'
    }
  ]
  [
    {
      LinkDarth: 'https://darkside.join/how-to-increase-your-power-10x',
      status: '404 - Not Found'
    }
  ]
]
```

<h2 id="option">๐ Available --options</h2>

--check | -c

- checks the urls status codes and return an object with url and status code with the following format:

```JS
[
    {
      LinkFoo: 'https://bar.barz',
      status: '200 - OK'
    },
    {
      LinkDarth: 'https://darkside.join/how-to-increase-your-power-10x',
      status: '404 - Not Found'
    }
]
```

<h2 id="license">๐ License</h2>

<p>This project uses MIT license. See <a href="https://en.wikipedia.org/wiki/MIT_License">LICENSE</a> for more details.</p> 

<hr>

<footer align="center">Made without โ by Rolf Helder</footer>
