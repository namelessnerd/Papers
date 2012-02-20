RM = rm -rf

BASE = ${wildcard *.tex}
FILES = ${BASE:%.tex=%.pdf}
MAIN=adefaaai2012
SVN-DEL= svn delete
LOPT =	-interaction=batchmode
LOPT2 = -shell-escape ${LOPT}
VERSION = `svnversion .`
DATE = `date +%m%d`
NAME = ${MAIN}.${DATE}

all: cleanlog compile clean rename open

compile: ${MAIN}.tex
	latex ${LOPT} ${MAIN}.tex
	#bibtex ${MAIN}
	#latex ${LOPT} ${MAIN}.tex
	#latex ${LOPT} ${MAIN}.tex
	dvips -q -Ppdf -o ${MAIN}.ps ${MAIN}.dvi
	ps2pdf ${MAIN}.ps
	
cleanlog: clean
	${RM} ${BASE:%.tex=%.log}

	
clean:
	${RM} ${BASE:%.tex=%.dvi}	
	${RM} *.aux
	${RM} ${BASE:%.tex=%.blg}
	${RM} ${BASE:%.tex=%.toc}

rename:
	cp ${MAIN}.pdf pdfversions/${NAME}.pdf

open:
	open ${MAIN}.pdf

