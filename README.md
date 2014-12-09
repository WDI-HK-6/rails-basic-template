# Rails Basic Template

### Reference: https://github.com/HK-WDI-November-2014/student-course-everything/blob/master/simple-rails-app.md

# Ruby on Rails
- Gemfile: A file that defines libraries the app is using
- bundle install: Based on the Gemfile, install all the libraries
- You should run `bundle install` every time you modify your Gemfile
- A gem is a library for Ruby
- RubyGems.org is a place to find and download Ruby gems

### New Rails App
1. rails new <name> -GBT
2. bundle install

3. Change the following in the Gemfile
``` ruby
	# use '4.1.6' for heroku
gem 'rails', '4.1.6'
	# Use postgresql as the database for Production
gem 'pg', group: :production
	# Use sqlite3 as the database for Development
gem 'sqlite3', group: :development
	# Bootstrap
gem 'bootstrap-sass', '~> 3.3.0'
```

4. Run `bundle install`

5. Uncomment and change in `routes.rb`
```
  root 'static_pages#index'
```

6. Generate a controller called `static_pages`
```
rails generate controller static_pages
```

7. Add a view called `index.html` under `static_pages` view folder

8. Change `application.css` to `application.css.scss`

9. Add the following line to the end of `application.css.scss`
```
@import "bootstrap-sprockets";
@import "bootstrap";
```

10. Add .gitignore File

### Deploy to Heroku
1. In `config/production.rb`, change the following 
```
config.serve_static_assets = false
```
to 
```
config.serve_static_assets = true
```
2. heroku create
3. Commit your changes
4. git push heroic master
