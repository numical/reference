# Find
[from here](https://www.linux.com/blog/25-examples-linux-find-command-search-files-command-line)

General syntax: `find where-to-look criteria wnat-to-look-for`

### case insensitive file name search
`find . [not] -iname *.md`

### search only files
`find . -type [f/d] -name *.md`

### find files containing text
`grep --exclude-dir={dir1,dir2} -rnw '/path' -e "pattern"`
