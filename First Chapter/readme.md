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


If the code parses successfully, there will be no output. If the code does not parse and there is a syntax error, the error will be printed to the terminal.


### Dynamic Evaluation
Node can directly evaluate from the shell. This is very useful for quickly checking a code snipeet or for creating very small cross-platform commands that use Javascript and Node core API's


There are two flags we can use to evaluate code the `-p` or `--print` that basically will evaluate an expression and print the result. the `-e` or `--eval` flag evaluates without printing the result of the expression.

Examples:

`node --eval "1+1"`
output: will not print anything because the expression is evaluated and okay.

`node --print "1+1"`
output: it will print 2

`node -e "console.log(1+1)"` 
This will print 2 because console.log is used to explicitly write the result of 1+1 to the terminal.

When used with print flag the same will print 2 and then print undefined because console.log returns undefined; so the result of the expression is undefined:

`node -p "console.log(1+1)`


### Preloaded CommonJS Modules

The command line flag `-r` or `--require` can be used to preload CommonJS module before anything else loads.

Example:

`node -r /preload.js app.js`

preload.js will be loaded first because it's used with the flag `require` which makes it required.

When it is useful to use this?

Preloading Modules is useful when using consuming modules that instrument or configure the process in some way. One example would be the `dotenv` module.


### Stack Trace Limit
