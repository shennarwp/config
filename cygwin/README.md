dump installed package list (as multi line strings):
`cygcheck -c -d | sed -e "1d" -e 's/ .*\$//' | cut -f1 -d ' ' > packagelist`

install in new machine (run in cygwin/conemu as admin):
``./setup-x86_64.exe -q -P `awk 'NR==1{printf \$1}{printf ",%s", \$1}' packagelist```

see also: https://stackoverflow.com/questions/46829532/cygwin-save-package-selections-for-later-reinstall