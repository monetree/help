# fix skype error for multiple file configured

soubhagya@developer:/etc/apt$ cat /etc/apt/sources.list.d/skype-stable.list
deb [arch=amd64] https://repo.skype.com/deb stable main
soubhagya@developer:/etc/apt$ cat /etc/apt/sources.list.d/skypeforlinux.list
deb [arch=amd64] https://repo.skype.com/deb stable main
soubhagya@developer:/etc/apt$ 
soubhagya@developer:/etc/apt$ rm -rf /etc/apt/sources.list.d/skypeforlinux.list
rm: cannot remove '/etc/apt/sources.list.d/skypeforlinux.list': Permission denied
soubhagya@developer:/etc/apt$ sudo rm -rf /etc/apt/sources.list.d/skypeforlinux.list
