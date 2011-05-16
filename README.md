##Clone repo:
	git clone git@github.com:smeghead/atnd.git attendance

##Edit your .bashrc
	export ATND_TOOL=/home/fukata/usr/local/attendance
	export PATH=$PATH:$ATND_TOOL

##Reload .bashrc:
	source ~/.bashrc

##Usage:
	atnd [-l] msg
###OPTIONS:
- -l display latest messages.
