what:;	@echo "make what?  (...)"
.PHONY:	remote push fetch
## plot view watch

REM_HOST=shire
REM_BASE=/local/IOTest
REM_INST=$(notdir ${PWD:=})
REMOTE=root@${REM_HOST}:${REM_BASE}/${REM_INST}
remote:	; @echo ${REMOTE}

PUSH=IOTest
push:	; rsync -ptvSH ${PUSH} ${REMOTE}/
fetch:	; rsync -avSH ${REMOTE}/{cfg.\*,\*.out} ./

## To control RAID background tasks:
##   storcli /call/vall show bgi|cc
##   storcli /call/vall pause bgi|cc
##   storcli /call/vall resume bgi|cc
