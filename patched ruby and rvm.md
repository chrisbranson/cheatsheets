Ruby & RVM with Rails Express patchset applied
===

Install RVM

	\curl -L https://get.rvm.io | bash -s stable --ruby

or

	\curl -L https://get.rvm.io | bash -s

Ensure RVM is up to date

	rvm get stable

Check rvm patchsets support ruby version and patch number you want to install

	ls ~/.rvm/patchsets/ruby/
	ls ~/.rvm/patchsets/ruby/1.9.3

If the ruby version and/or patch number isn't listed, clone the following repository

	git clone git://github.com/skaes/rvm-patchsets.git
	cd rvm-patchsets
	./install.sh 1.9.3

See https://github.com/skaes/rvm-patchsets for further details

If the ruby version and patch number is listed, you can ask rvm to install Ruby with the patchset

	rvm reinstall 1.9.3 --patch railsexpress

Or for a specific patch number

	rvm reinstall 1.9.3-p327 --patch railsexpress

Use the new ruby as the default ruby

	rvm use ruby-1.9.3-p327 --default

Don't forget to update .rvmrc
