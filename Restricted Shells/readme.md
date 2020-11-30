
# Getting an Improved Shell

**Basic tty shell:**

```
python -c 'import pty; pty.spawn("/bin/bash")'

python3 -c 'import pty; pty.spawn("/bin/bash")'

echo os.system(‘/bin/sh’)

/bin/sh -i

perl -e 'exec "/bin/sh";'
```

**Improving PATH variable:**

```
export PATH=$PATH:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

export PATH="/usr/bin:$PATH"
export PATH="/bin:$PATH"
```

*SearchSploit also has tips for breaking out a restricted shell with - "searchsploit restricted shell"
Searchsploit -u can update the searchsploit database*

**Crazy duplicate characters?**

*background process with CRTL+Z*
```
bg

stty raw -echo

fg
```

*This stops the terminal from echoing characters.*

```
Ctl+Z
stty raw -echo
fg
reset
```
