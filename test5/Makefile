# $Id: Makefile,v 1.1 2019-03-04 19:44:15-08 - - $

MKFILE     = Makefile
JAVASRC    = queue.java qtest.java
CLASSES    = queue.class qtest.class
JARCLASSES = ${CLASSES} queue\$$emptyexn.class queue\$$node.class
JARFILE    = qtest
MAINCLASS  = qtest
SOURCES    = ${JAVASRC} ${MKFILE}

all : ${JARFILE}

${JARFILE} : ${CLASSES}
	echo Main-class: ${MAINCLASS} >Manifest
	jar cvfm ${JARFILE} Manifest ${JARCLASSES}
	chmod +x ${JARFILE}
	- rm Manifest

%.class : %.java
	cid + $<
	javac $<

clean :
	- rm ${JARCLASSES}

spotless : clean
	- rm ${JARFILE}

ci : ${SOURCES}
	cid + ${SOURCES}

test : ${JARFILE}
	./${JARFILE} * | cat -n

