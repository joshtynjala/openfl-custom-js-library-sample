# OpenFL custom JS library

The [OpenFL](https://openfl.org) library for Haxe contains a number of template files that are used when building a project. You can find them in the [_assets/templates_](https://github.com/openfl/openfl/tree/develop/assets/templates) directory. Using the `<template>` element in _project.xml_, it's possible to provide additional template files to copy to the output directory, on a per-project basis, and without forking OpenFL.

This sample project contains a directory named [_custom-templates_](https://github.com/joshtynjala/openfl-custom-js-library-sample/tree/main/custom-templates). It is configured in [_project.xml_](https://github.com/joshtynjala/openfl-custom-js-library-sample/tree/main/project.xml) like this:

```xml
<template path="custom-templates"/>
```

Inside [_custom-templates_](https://github.com/joshtynjala/openfl-custom-js-library-sample/tree/main/custom-templates), there's a file at [_html5/template/custom-library.js_](https://github.com/joshtynjala/openfl-custom-js-library-sample/tree/main/custom-templates/html5/template/custom-library.js). This is a custom JavaScript library that needs to be called from Haxe code.

To include an HTML `<script>` tag in the _index.html_ for _custom-library.js_, configure it in [_project.xml_](https://github.com/joshtynjala/openfl-custom-js-library-sample/tree/main/project.xml) like this:

```xml
<dependency name="./custom-library.js" if="html5"/>
```

There is also a file named _src/CustomLibrary.hx_ that defines [Haxe externs](https://haxe.org/manual/lf-externs.html) for the custom library. Visit [Haxe Manual: Using external JavaScript libraries](https://haxe.org/manual/target-javascript-external-libraries.html) for more details about custom JavaScript library externs.

To build and launch the project, run the following command:

```sh
openfl test html5
```
