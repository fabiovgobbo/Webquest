
HTML=Introdução.html Tarefa.html Processo.html  Avaliação.html Conclusão.html
MRKD=$(HTML:.html=.md)

all: $(HTML)

%.html: %.md template.html
	markdown $< > tmp
	sed "/<\!--++-->/r tmp" "template.html" | sed "s/<t>/$*/" > $@

clean:
	rm -rf tmp

git: clean
	git add *
	git commit
	git push

purge: clean
	rm -rf $(HTML)
