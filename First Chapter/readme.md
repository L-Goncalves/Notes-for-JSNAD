## This chapter is to:

<ul>
    <li>Explore all possible Node and V8 command line flags.</li>
    <li>Use key utility mode command line flags.</li>
    <li>Understand an essential selection of operational command line flags.</li>
<ul>


### Printing Command Options

To see Node CLI for any version we can just use `node --help` and we'll have a list of commands we can use in node.

beyond the node cli flags there's also additional flags for modifying the Javascript runtime engine: V8.


To view these flags run `node --v8-options`


it's also possible to parse a Javascript Application without running it in order to just check the syntax.

This can be useful on occasions as running code has a teardown cost, for instance needing to clear the database, but there's still a need to check if the code parses it can also be used in more advanced cases like where the code has been generated and a syntax check is required.

To check the syntax of a code we can use `--check` or `-c` flag.

`node --check app.js` : basically it'll check the syntax of app.js


`node -c app.js` : basically it'll check the syntax of app.js <b>-c is a short for --check<b>.
