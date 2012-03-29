Deploying to Cloud Foundry
===

### Add the following to config/boot.rb to use node v6 as the javascript runtime

	# required for CloudFoundry only
	# /var/vcap/data/packages/dea_node06/1/bin
	deanode_contents = Dir.entries("/var/vcap/data/packages/dea_node06")
	deanode_contents.delete(".")
	deanode_contents.delete("..")
	deanode_contents.each { |d| ENV['PATH'] = "#{ENV['PATH']}:/var/vcap/data/packages/dea_node06/#{d}/bin" }
	puts "PATH set to #{ENV['PATH']}"
	
### Turn on static assets and compilation in config/environments/production.rb
	config.serve_static_assets = true
	config.assets.compile = true


### Use CloundFoundry specific jquery-rails gem

	# For Ruby 1.9 Cloud Foundry requires a tweak to the jquery-rails gem.
	# gem 'jquery-rails'
	gem 'cloudfoundry-jquery-rails'

NB: comment out the existing gem 'jquery-rails' entry in your Gemfile

### Remove any heroku or newrelic gems
	# gem 'heroku'
	# gem 'newrelic_rpm'

### Update bundle and package ready for deployment
	bundle install
	bundle package
	
### Rebuild production assets prior to deployment
	rm -Rf public/assets
	RAILS_ENV=production bundle exec rake assets:precompile
	
### Configure vmc
	vmc target http://api.[your micro foundry name].cloudfoundry.me
	vmc register
	vmc login youremail@yourdomain.com
	
NB: You can skip these steps if you have already registered a username to your local CloudFoundry installation
	
### Deploy to CloudFoundry with ruby v1.9 runtime
	vmc push --runtime ruby19
	
### References

http://start.cloudfoundry.com/frameworks/ruby/rails-3-1.html

http://support.cloudfoundry.com/entries/20757913-getting-a-rails-3-1-1-production-environment-working
