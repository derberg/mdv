# mdv

A tiny markdown (link) validator. It returns an exitCode of 1 if any internal links are broken,
making it suitable for use in CI environment.

## Usage

````
Options:
  -d, --debug  enable debug mode                                       [boolean]
  -h, --help   Show help                                               [boolean]
````

### API

````javascript
var mdv = require('mdv');
var options = {};
var result = mdv.validate(markdownString);
````

### Example output

````javascript
{ source: '../OpenAPI-specification/versions/3.0.md',
  missingAnchors:
   [ { name: 'definitions', defined: 0, seen: 1 },
     { name: 'specification', defined: 0, seen: 1 },
     { name: 'format', defined: 0, seen: 1 },
     { name: 'schema', defined: 0, seen: 1 },
     { name: 'linkObject', defined: 0, seen: 4 },
     { name: 'dataTypeType', defined: 0, seen: 2 },
     { name: 'oasParameters', defined: 0, seen: 2 },
     { name: 'requestBody', defined: 0, seen: 1 },
     { name: 'oasResponses', defined: 0, seen: 2 },
     { name: 'ReferenceObject', defined: 0, seen: 1 } ],
  duplicatedAnchors: [] }
````

