include project.mk

$(project).pdf: $(input-files)
	# DejaVu Sans supports some Unicode characters.
	gawk '1; ENDFILE{ print "\n\\newpage\n" }' $^ | \
	pandoc -o $@ \
		--pdf-engine=xelatex \
		-V mainfont="DejaVu Sans" \
		-V colorlinks=true \
		-V linkcolor=gray \
		-V urlcolor=blue \
		-V toccolor=gray

all: $(project).pdf

clean:
	rm -rf $(project).pdf

.PHONY: clean all
