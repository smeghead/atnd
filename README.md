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
- -L       display latest 10 messages. 
- -l num   display latest given count messages. 
- -d ids   delete messages. separated comma ID.
- -h       show help.

##Tips:

###when svn or git command execute, register atnd.(zsh only)

add below in ~/.zshrc

	#for atnd
	function precmd() {
	  lastcmd=$(history -n -1 | head -1)
	  case $(echo $lastcmd | cut -d ' ' -f 1) in
	    git|svn)
	      atnd "$lastcmd [$(pwd)]"
	      ;;
	  esac
	}

###when svn or git command execute, register atnd.(bash only, simple version)

	function precmd() {
	  lastcmd=$(history 1 | awk '{printf("%s %s %s %s %s\n", $2, $3, $4, $5, $6);}')
	  case $(echo $lastcmd | cut -d ' ' -f 1) in
	    git|svn)
	      atnd "$lastcmd [$(pwd)]"
	      ;;
	  esac
	}
	PROMPT_COMMAND='precmd'

