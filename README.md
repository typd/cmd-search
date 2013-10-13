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
        line   12:     for file in os.listdir(dir):
        line   27:                     print('  {}'.format(bold('./' + relative_path)))
        line   28:                     for match in matches:
        line   29:                         print('    {}'.format(match))
        line   31:                         print('    {} matches'.format(len(matches)))
        line   33:                 print('  ERROR on openning {}'.format(path))
        line   37:     return '\033[4m{}\033[0m'.format(str)
        line   40:     return '\033[1m{}\033[0m'.format(str)
        line   55:         matches = ['line {0: >4}: {1}'.format(no, line.replace('\n', '').replace(text, underline(text)))\
        line   56:                 for no, line in enumerate(file)\
        line   62:     return template.format(regex.replace('.', '\\.').replace('*', '.*')) if regex else None
        line   75:     print('[dir  ]: {}'.format(dir))
        line   77:         print('[depth]: {}'.format(max_depth))
        line   79:         print('[path ]: "{}"'.format(args.path_regex))
        line   81:         print('[text ]: "{}"'.format(args.text))
        line   86:     print('Matched {} lines in {} files'.format(lines, files))
        16 matches
    ----------------
    Matched 16 lines in 1 files
    ----------------

## note

- highlight searched files

- underline matched text in each line

- ignore non-text files while matching file content

## install

pre-requirements           

- python3; it'a better python than python2 

- pip3 install -r requirements.txt; 'pip3' is your python3 pip

install

    git clone https://github.com/typd/cmd-search.git
    cp cmd-search/search /usr/local/bin/search
