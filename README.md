##Clone repo:
	git clone git@github.com:smeghead/atnd.git attendance

##Edit your .bashrc
	export ATND_TOOL=/home/fukata/usr/local/attendance
	export PATH=$PATH:$ATND_TOOL

##Reload .bashrc:
	source ~/.bashrc

##Usage:
	atnd [-h] [-l num] [-d ids] msg 
###OPTIONS:
- -l display latest messages.
- -d delete messages. separated comma ID.
- -h show help.

##Tips:

###when svn or git command execute, register atnd.
    #for atnd
    function precmd() {
      lastcmd=$(history -n -1 | head -1)
      case $(echo $lastcmd | cut -d ' ' -f 1) in
        git|svn)
          atnd "$lastcmd [$(pwd)]"
          ;;
      esac
    }

