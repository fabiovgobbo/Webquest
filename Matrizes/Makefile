
HTML=Introdução.html Tarefa.html Processo.html  Avaliação.html Conclusão.html
MRKD=$(HTML:.html=.md)

all: $(HTML)

%.html: %.md template.html
	pandoc $< > tmp
	sed "/<\!--++-->/r tmp" "template.html" | sed "s/<t>/$*/" > $@

clean:
	rm -rf tmp

commit: clean
	git add *
	git commit

push:
	git push

purge: clean
	rm -rf $(HTML)
