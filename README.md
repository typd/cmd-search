# cmd-search

A shell tool to search local files and file texts

## usage

search [-d directory] [-p path_regex] [-L max depth] [text]

-d, directory to search, current directory by default

-L, max depth depth, no limit by default

-p, file path regex, e.g. '*.py'

-text, plain text to search within each text file, if leave it empty, just show matched file names

    ➜  ./search -p search for
    [dir  ]: /Users/yizhe/Working/typd/cmd-search
    [path ]: "search"
    [text ]: "for"
    ----------------
    Search Results:
      ./search
        [ 12]     for file in os.listdir(dir):
        [ 27]                     print('  {}'.format(invert('./' + relative_path)))
        [ 28]                     for match in matches:
        [ 29]                         print('    {}'.format(match))
        [ 31]                         print('    {} matches'.format(len(matches)))
        [ 34]                 #print('  ERROR on openning {}'.format(path))
        [ 35]                 #print('  {}'.format(ex))
        [ 40]     return '\033[7m{}\033[0m'.format(str)
        [ 43]     return '\033[4m{}\033[0m'.format(str)
        [ 46]     return '\033[1m{}\033[0m'.format(str)
        [ 61]         matches = ['{0} {1}'.format(\
        [ 62]                 bold('[{0: >3}]'.format(no)),\
        [ 64]                 for no, line in enumerate(file)\
        [ 70]     return template.format(regex.replace('.', '\\.').replace('*', '.*')) if regex else None
        [ 83]     print('[dir  ]: {}'.format(dir))
        [ 85]         print('[depth]: {}'.format(max_depth))
        [ 87]         print('[path ]: "{}"'.format(args.path_regex))
        [ 89]         print('[text ]: "{}"'.format(args.text))
        [ 94]     print('Matched {} lines in {} files'.format(lines, files))
        19 matches
    ----------------
    Matched 19 lines in 1 files
    ----------------

## note

- highlight searched files

- underline matched text in each line

- ignore non-text files while matching file content

- similar commnd in shell, which is pretty long: find . -name \*.py | xargs grep 'text'

## install

pre-requirements           

- python3; it's a better python than python2 

- pip3 install -r requirements.txt; 'pip3' is your python3 pip

install

    git clone https://github.com/typd/cmd-search.git
    cp cmd-search/search /usr/local/bin/search
