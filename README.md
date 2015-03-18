# dcd
like cd command
but it can save the cd history and fuzzy find dirs

How To Install
Linux Only
Download the execute file dcd (i compile the 64bit for linux only)
Download the dcd.sh 
mkdir .dacecd in your homepath then move dcd.sh and dcd in it

vim YOURHOMEPATH/.dacecd/.dcd.sh
#!/bin/bash
unalias cd
alias dcd='YOURHOMEPATH/.dacecd/dcd'
if [ $# == 0 ];then
    cd
else
    cd $1
fi
dcd `pwd`
unalias dcd
alias cd='source YOURHOMEPATH/.dacecd/dcd.sh'

Replace YOURHOMEPATH to your real homepath.



How To Config

First:
Can't use ~ to instead of YOURHOMEPATH

Second:
vim YOURHOMEPATH/.dacecd/.dacecdrc


{
  "ContainDirs": [
    "/home/qspace_system/QQMail/micromsg",
    "/home/qspace_system/QQMail/mmcomm"
  ],
  "HisCount":100
}

Modify the ContainDirs that you need to fuzzy. The .dacecdrc must be a json.


Third:
vim .profile or .bashrc

Add two lines below:
alias cd='source YOURHOMEPATH/.dacecd/dcd.sh'
alias cdl='YOURHOMEPATH/.dacecd/dcd;source YOURHOMEPATH/.dacecd/command.sh'

Reconnnect your terminal.

