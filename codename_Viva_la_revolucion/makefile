MOD_NAME := Theme Randomizer
MOD_CREATOR := DefKorns
MOD_CATEGORY := UI
GIT_COMMIT := $(shell echo "`git rev-parse --short HEAD``git diff-index --quiet HEAD -- || echo '-dirty'`")
GIT_TAG := $(shell git describe --tags)
MOD_FILENAME := $(shell basename "`git config --get remote.origin.url`" .hmod.git)

all: out/$(MOD_FILENAME)-$(GIT_COMMIT).hmod

out/$(MOD_FILENAME)-$(GIT_COMMIT).hmod:
	mkdir -p out/ temp/
	rsync -a mod/ temp/ --links --delete

	cd temp/; tar -czvf "../$@" *
	rm -r temp/
	touch "$@"

clean:
	-rm -rf out/

.PHONY: clean
