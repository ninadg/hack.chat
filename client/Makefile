
SCHEMES_BASE16 = $(wildcard base16/*.less)
SCHEMES = $(SCHEMES_BASE16:base16/%.less=schemes/%.css)

build: $(SCHEMES) index.html style.css

schemes/%.css: scheme.less
	mkdir -p schemes
	../node_modules/less/bin/lessc --global-var='name=$*' $^ > $@

%.css: %.less
	../node_modules/less/bin/lessc $^ > $@

%.html: %.jade
	../node_modules/jade/bin/jade.js $^

clean:
	rm -fv schemes/*.css index.html style.css
