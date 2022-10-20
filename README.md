## Github Linguist For Imba
- [Github Linguist Contributing Page](https://github.com/github/linguist/blob/master/CONTRIBUTING.md)
- [Original Issue](https://github.com/github/linguist/issues/5910)
- [Original PR](https://github.com/github/linguist/pull/3869/commits/e4a8f807bcae364133ba715b2d56fa804db9dcdd)
- [New PR](https://github.com/github/linguist/pull/6080)
- [Number of Imba Files On Github](https://github.com/search?p=9&q=extension%3Aimba&ref=opensearch&type=Code)
- [Number of Dependents On Github](https://github.com/imba/imba/network/dependents?package_id=UGFja2FnZS0xNDkyNDIxOQ%3D%3D)
- [Source of Game Of Life Sample, MIT license](https://github.com/imba/game-of-life)

### Imba Language
```
Imba:
  type: programming
  color: "#16cec6"
  extensions:
  - ".imba"
  ace_mode: text
  tm_scope: source.imba
  language_id: 1057618448
```

### Installation

Warning: This may be a massive pain.

1. Install Docker Desktop from docker website, not from homebrew.
1. Open Docker.
1. Then:
	```
	brew install cmake pkg-config icu4c
	sudo gem install bundler
	git clone https://github.com/imba/linguist.git
	cd linguist
	```
1. On an M1 Macbook Air, before running `script/bootstrap`, I had to run:
	```
	bundle config build.charlock_holmes --with-icu-dir=/usr/local/opt/icu4c --with-cxxflags='-Wno-reserved-user-defined-literal -std=c++11'
	bundle config set force_ruby_platform true
	```
1. Then:
	```
	script/bootstrap
	bundle exec rake samples
	bundle exec bin/github-linguist --breakdown
	```
1. Then add imba to end of `languages.yml`, omitting `language_id`, and:
	```
	script/add-grammar https://github.com/imba/imba-linguist-grammar
	script/update-ids
	```
