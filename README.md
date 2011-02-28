# BBYIDX - Share you ideas

BBYIDX is a free and open source idea-gathering application written in Ruby and distributed
under the GNU Affero General Public License.

## Local Installation

1. `bundle install`
2. `rake db:migrate`
3. `rake db:seed`

### Database

To set up the database, if you are using MySQL, you'll need to make sure the user configured in database.yml
has permission to use the "load data" command:

    grant file on *.* to bbyidx;

### Running the test suite

To verify your installation:

    rake test

## Configuration

The following files will need to be modified in order to configure your
installation:

* config/environment_custom.rb
* config/database.yml
* config/newrelic.yml       (if you want performance metrics from NewRelic)
* config/twitter.yml        (if you want Twitter integration)
* config/facebooker.yml     (if you want Facebook integration)

## Customization

To customize the UI, edit / create files in the following directories:

* app/views/custom/
* public/stylesheets/sass/
* public/images/

**NOTE:** UI elements that pertain to your brand need not be contributed back to the open source project.

## Heroku Installation

The following steps* will walk you through getting BBYIDX running on Heroku, our favorite cloud platform.
These steps must be executed from the project root directory.

1. `heroku create YOUR-APP-NAME`
2. `heroku addons:add [sendgrid](http://addons.heroku.com/sendgrid):free`
3. `git push heroku master`
4. `heroku rake db:migrate`
5. `heroku restart`
6. `heroku rake db:seed`
7. `heroku open`

_* NOTE: The [heroku client library](http://rubygems.org/gems/heroku) is required for these steps._
