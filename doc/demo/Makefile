# order of input, use `\` to separate lines
txt = ??_*.txt

out = _demo
# target: usually any of docx, pdf, html, txt
target = html

$(out).$(target): $(txt)
	$(MAKE) prepare
	pandoc -s -o $(out).$(target) .*.txt.md

prepare:
	for t in $(txt); do pandoc -s --id-prefix $$t -o .$$t.md $$t; done

fmt:
	for t in $(txt); do pandoc -s $$t -o $$t; done

clean:
	-rm .*.txt.md

fresh: clean
	-rm $(out).$(target)
