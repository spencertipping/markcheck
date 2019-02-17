# Markcheck: checks local markdown links
I have a problem: I'll write up a bunch of Markdown files that link to each
other, then I'll move some of them, and in the process I'll forget to update
links. This is a bummer, so I wrote this thing to fix it.


## Usage
```sh
$ find -name '*.md' | xargs markcheck
```


## Testing
- [This link should be missing](should-be-missing)
- [This link should be ok](http://should-be-ok)


## License
MIT as usual.
