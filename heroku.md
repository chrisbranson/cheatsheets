Heroku cheat sheet
===

### get info about your app on heroku
	heroku info

### push code changes (after a commit) to heroku server
	git push heroku

### change logging level to debug (more detailed)
	heroku config:add LOG_LEVEL=DEBUG

### change logging level to info (less detailed)
	heroku config:add LOG_LEVEL=INFO

### see log content
	heroku logs

### see more log content (200 lines in this example)
	heroku logs -n 200

### tail heroku logs
	heroku logs --tail

### manually scale web and worker dynos
	heroku scale web=1 worker=0

### see what dynos/process are running
	heroku ps
