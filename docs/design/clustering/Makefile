FONT := DroidSansMono.ttf

PNGS := $(patsubst %.seqdiag,%.png,$(wildcard *.seqdiag))

.PHONY: all
all: $(PNGS)

.PHONY: watch
watch:
	fswatch *.seqdiag | xargs -n 1 sh -c "make || true"

$(FONT):
	curl -sLo $@ https://googlefontdirectory.googlecode.com/hg/apache/droidsansmono/$(FONT).ttf

%.png: %.seqdiag $(FONT)
	seqdiag -a -f '$(FONT)' $<
