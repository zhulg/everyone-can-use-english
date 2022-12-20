.PHONY: deploy
deploy: book
	@echo "====> 1 deploying to github"
	rm -rf /tmp/book
	git worktree add -f /tmp/book gh-pages
	@echo "====> 2 begining mdbook build"
	mdbook build
	@echo "====> 3 del old res"
	rm -rf /tmp/book/*
	@echo "====> 4 push new and deploying "
	cp -rp book/* /tmp/book/
	cd /tmp/book && \
		git add -A && \
		git commit -m "deployed on $(shell date) by ${USER}" && \
		git push origin gh-pages
