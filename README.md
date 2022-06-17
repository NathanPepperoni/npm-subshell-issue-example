# npm-subshell-issue-example

to reproduce:

Execute the following command at the root level of the project: `(cd subdir && ls) && ls`

You'll see the following output:
```
samplefile.txt
package.json  subdir/
```

butif you use the npm script to run the exact same bash command sequence by entering `npm run example`, you get the following unexpected output:
```
samplefile.txt
samplefile.txt
```

this indicates that when run as a package script, the subshell (the parenthesis around the first 2 commands) is not working correctly
