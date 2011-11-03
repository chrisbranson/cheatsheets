RVM cheat sheet
===

### get latest version of rvm:
	rvm get head
	rvm reload 

### show active ruby version:
	ruby -v

### check which versions of ruby you now have installed:
	rvm list

### install & use new version of ruby:
#### 1. install specific version & release of ruby:
	rvm install ruby-1.9.3-p0
#### 2. permanently set default version of ruby:
	rvm ruby-1.9.3-p0 --default
#### 3. install bundler:
	gem install bundler
#### 4. set path for pg gem
	export PATH=/Library/PostgreSQL/9.0/bin:$PATH
#### 5. install application gems
	bundle install

### reset rvm gemset:
#### 1. clear out installed gems
	rvm gemset empty
#### 2. get latest *live* version of rubygems
	rvm rubygems current
#### 3. get bundler
	gem install bundler
#### 4. set path for pg gem
	export PATH=/Library/PostgreSQL/9.0/bin:$PATH
#### 5. install application gems
	bundle install

### temporarily change version of ruby:
	rvm ruby-1.9.2-p180

### uninstall specific version of ruby:
	rvm remove ruby-1.9.2-p136