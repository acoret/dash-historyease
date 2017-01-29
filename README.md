# dash-historyease
To earse something in dash file history record.

As we know ubuntu unity desktop environment will record the file u use,sometime it will record something u don't want it to.</br>
So I just write a `lua-shell`  to fix it.<br/>
##Usage
*First it need lua and splite3*<br/>
dash_history [OPTIONS] [aim_name]<br/>
      install,it will try to copy itself into the $install_path，if u want to change it u can edit the luafile in 3 line(It's default is /usr/local/bin/)<br/>
      -h,--help it wil print help and usage to u,but in fact it is in chinese,so ....<br/>
      -p,--path,it will change the where aim sqlite placed，default ~/.local/share/zeitgeist/activity.sqlite<br/>
      -w,--where,it is control the SQL command's WHERE,default uri<br/>
      -f,--from,it is control the SQL command FROM,default value<br/>
      -l,--list,if you use the -l,it won't delete just print the aim.<br/>
      -m,--match,it will try to match ...uh...i will explain ..<br/>
<br/>
dash_history -p ~/.local/share/zeitgeist/activity.sqlite -l -m testfile   --- it will print like these<br/>
24129|file:///home/uncrepter/`testfile`1.ok<br/>
24130|file:///home/uncrepter/nopro`testfile`_ok  
thats how -m work  
if you use the -l it won't delete just print  
and in fact the lua-shell work according to send command to splite3 like these  
*dash_history -l -m aim*  
`sqlite3 /home/uncrepter   /.local/share/zeitgeist/activity.sqlite "SELECT * FROM uri WHERE value LIKE '%aim%'"`

<br/>
##Installation
i prefer just place it in somewhere u like,and edit it in .bashrc
like these
alias dash_history /$shell_path/dash_history

and it will work.i think so.
If u want to use the install
uh...i dont test it at all...hope it won't crash or ...may u can add sudo before cp.
don't forget to edit shell,u need to edit the path and install_path
##After all
I'm noob...
