# Rails dev base container

This container is based on official rails container (was ruby:2.2 but got SSL error on some node, so change to rails container), but with those changes:

* Change debian and gem repo to Taobao mirror
* Link binary `/usr/bin/nodejs` to `node` to enable `node` command.
* Install npm package.
* Install bower package (used in rails-bower gem) and allow root to run `bower` command.

