# ish
- default file system is 3.14.x, can download updated file system from alpine website, import it and boot it
- node and npm not working well so far
- git not work unless set
`git config --global pack.threads "1"`
- alpine default shell ash, you can change e.g to bash 

`echo $SHELL` 

`apk add bash` 
 
`cat /etc/shells`  make sure it was there

`lchsh USER` and input the shell path

- `apk add openssh`, refer to GitHub for auth to creat pub key and add to you keys settings
- mount -t ios <*src floder*> <*dest folder*>
- export your filesystem, you can import it by your any iOS device, anything will like replay except mount iOS disk, you have to mount again
- install gcc, I make a c file, it works