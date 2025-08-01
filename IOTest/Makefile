what:;	@echo "make what?  (...)"
.PHONY:	remote push purge fetch plot view watch

REM_BASE=/local/DDRead
REM_INST=$(notdir ${PWD:=})
#REM_HOST=$(notdir ${PWD:/${REM_INST}=})
REMOTE=root@shire:${REM_BASE}/${REM_INST}
remote:	; @echo ${REMOTE}

PUSH=DDLayout DDRead Makefile
push:	; rsync -ptvSH ${PUSH} ${REMOTE}/

purge:	; rm -rf *.out Plot.png
fetch:	; rsync -avSH ${REMOTE}/{cfg.\*,\*.out} ./
plot:	fetch ; ./Plot *.out
view:	; eog Plot.png
watch:	; watch -n60 make plot

## storcli /call/vall show bgi|cc
## storcli /call/vall pause bgi|cc
## storcli /call/vall resume bgi|cc
