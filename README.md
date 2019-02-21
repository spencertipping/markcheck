# Markcheck: checks local markdown links
I have a problem: I'll write up a bunch of Markdown files that link to each
other, then I'll move some of them, and in the process I'll forget to update
links. This is a bummer, so I wrote this thing to fix it.


## Usage
```sh
$ markcheck                       # same as markcheck .
$ markcheck /path/to/git/repo ... # scan one or more repos
```


## Output
`markcheck` will report two types of errors:

1. A document contains a link to a file that doesn't exist
2. A non-`readme` document exists, but nobody links to it


## Testing
Markcheck is [barely] tested with
[Lazytest](https://github.com/spencertipping/lazytest).

```bash
$ ./markcheck; echo $?
./README.md:32: invalid link to should-be-missing
/home/spencertipping/r/public/markcheck/orphaned.md is orphaned
1
```

- [This link should be missing](should-be-missing)
- [This link should be ok](http://should-be-ok)

```
[This link should be ignored](should-be-ignored)
```


## License
MIT as usual.
