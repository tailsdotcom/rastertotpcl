## File contents here courtesy of https://github.com/Drachenkaetzchen/rastertotpcl
## This Makefile will successfully install the drivers onto Ubuntu 18.04 LTS

EXEC=rastertotpcl
CFLAGS=-Wall -Wextra --std=c99 -O2 -lm
PPDPATH=/usr/share/ppd
EXECPATH=/usr/lib/cups/filter

all: rastertotpcl ppd

.PHONY: ppd clean install uninstall

$(EXEC): rastertotpcl.c
	gcc $(CFLAGS) rastertotpcl.c -o rastertotpcl -lcupsimage -lcups

ppd:
	ppdc tectpcl2.drv

install:
	if test ! -d $(PPDPATH)/$(EXEC); then mkdir $(PPDPATH)/$(EXEC); fi
	cp ppd/* $(PPDPATH)/$(EXEC)
	cp $(EXEC) $(EXECPATH)/
	

uninstall:
	rm -rf $(PPDPATH)/$(EXEC)
	rm -f $(EXECPATH)/$(EXEC)


clean:
	rm -f rastertotpcl
	rm -rf ppd
