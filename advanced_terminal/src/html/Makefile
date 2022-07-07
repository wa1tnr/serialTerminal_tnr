# Thu  7 Jul 21:02:24 UTC 2022

TMPFI=tempfile_8888

captured.$$$$:
	@echo captured.$$$$ > ./thisfile_7777
	@git show | sed 1q > `cat ./thisfile_7777`

clean:
	@echo -n "THIS is a target for removal: "
	@echo `cat ./thisfile_7777`
	@echo -n "removing: "
	@echo `cat ./thisfile_7777`
	@rm -rf `cat ./thisfile_7777`
	@rm -rf ./thisfile_7777
	@rm -rf ./${TMPFI}

stamped:	captured.$$$$ index.html
	@cat ./index.html >> ${TMPFI}
	@echo "" >> ${TMPFI}
	@echo "</html>" >> ${TMPFI}
	@echo "<br>" >> ${TMPFI}
	@cat "`cat thisfile_7777`" >> ${TMPFI}
	@echo "<br>" >> ${TMPFI}
	@git checkout -- index.html # dangerous with no saved changes
	@diff ./index.html ./${TMPFI} ; exit 0

stemp:	stamped
	@cat ./${TMPFI} > new_index.html
	@echo
	@echo now just the diff for final product here:
	@echo
	@diff ./index.html ./new_index.html ; exit 0

stamp:	stemp clean
	@echo target was stamp

all:
	@echo make all

# 06 July 2022 17:44z
# END.
