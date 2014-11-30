#Use d for docker. e.g. d ps -a
d() { docker "$@" ; }

#Stop and remove last running container
drml() { DA_LID=`docker ps -lq`; echo "Stopped container `docker stop $DA_LID`"; "Removed container `docker rm $DA_LID`"; }

#Get a bash prompt in a running container
dbash() { docker exec -i -t "$1" /bin/bash; }

#Remove all stopped containers
alias drmall='docker rm `docker ps -a -q`'