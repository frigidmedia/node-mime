# mime

Comprehensive MIME type mapping API. Includes all 600+ types and 800+ extensions defined by the Apache project, plus additional types submitted by the node.js community.

## Fork

This fork is customized to be packaged within one file to be included in node core.

## Install

Install with [npm](http://github.com/isaacs/npm):

    npm install mime

## API - Queries

### mime.lookup(path)
Get the mime type associated with a file. Performs a case-insensitive lookup using the extension in `path` (the substring after the last '/' or '.').  E.g.

    var mime = require('mime');

    mime.lookup('/path/to/file.txt');         // => 'text/plain'
    mime.lookup('file.txt');                  // => 'text/plain'
    mime.lookup('.TXT');                      // => 'text/plain'
    mime.lookup('htm');                       // => 'text/html'

### mime.extension(type)
Get the default extension for `type`

    mime.extension('text/html');                 // => 'html'
    mime.extension('application/octet-stream');  // => 'bin'

### mime.charsets.lookup()

Map mime-type to charset

    mime.charsets.lookup('text/plain');        // => 'UTF-8'

(The logic for charset lookups is pretty rudimentary.  Feel free to suggest improvements.)
