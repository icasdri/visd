# visd
*Making VIM a stream editor*.
<br>
**visd** makes it possible to use your `vim` and `ex` commands to manipulate streams, like you would with `sed`. 

## Examples
Some inter-tag changing.
```
$ echo "<h1>Hello World</h1>" | visd 'f>lcitWelcome'
<h1>Welcome<h1>
```

Ex-mode replacement and a basic word change. 
```
$ echo "This is a tsee" | visd ':s/tsee/test/' 'cwThat'
That is a test
```

In-word movement, simple character appending, and a visual-mode command! Additionally, `visd` behaves like `sed` and operates on a per-line basis. Note that, each sequence of commands always starts execution at the start of the line.
```
$ cat records.txt
John 18
Alex 26
Richard 40

$ cat records.txt | visd 'Ea,' 'A.' 'vwgU'
JOHN, 18.
ALEX, 26.
RICHARD, 40.
```

## Installation
`visd` is a simple `bash` script. Simply download it, mark it as executable, and add it to your `PATH`. Make sure `vim` is installed and available in your `PATH` as well (why wouldn't it be?).

For instance:
```
$ wget 'https://raw.githubusercontent.com/icasdri/visd/master/visd'
$ chmod u+x visd
$ export PATH=$PATH:.
```

For Arch Linux users, the package [visd-git](https://aur.archlinux.org/packages/visd-git/) is available in the AUR.

## Acknowledgements
**visd** is essentially an easy-to-use utility around the concepts presented in this great blog post http://blog.robertelder.org/use-vim-inside-a-unix-pipe-like-sed-or-awk/. Have a read to understand how it works!

## License
Licensed under the MIT License, see LICENSE for details.
