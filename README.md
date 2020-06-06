# HackBeanpot Backend

The API for the HackBeanpot webapp (experimental).

Generated with this guide:
https://edgeguides.rubyonrails.org/api_app.html


Worked through this tutorial to build a JWT authenticator:
https://www.pluralsight.com/guides/token-based-authentication-with-ruby-on-rails-5-api

Things you may want to cover:

* Ruby version
* System dependencies
* Configuration
* Database creation
* Database initialization
* How to run the test suite
* Services (job queues, cache servers, search engines, etc.)
* Deployment instructions

## Installation

Use the package manager [bundle](https://bundler.io/bundle_install.html) to install the dependencies in the `Gemfile`.

```bash
bundle install
```

## Usage

Enter `rails c` in the terminal to open the Interactive Ruby Shell for rails.
To add a new user:

```bash
$ User.create!(email: 'example@mail.com' , password: '123123123' , password_confirmation: '123123123')
```

Enter `rails s` in the terminal to start the rails server. 

To retrieve a JWT for authentication (with the user you created):
```bash
$ curl -H "Content-Type: application/json" -X POST -d '{"email":"example@mail.com","password":"123123123"}' http://localhost:3000/authenticate
```

Use that information to access infromation from a protected route:
```bash
$ curl -H "Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE0NjA2NTgxODZ9.xsSwcPC22IR71OBv6bU_OGCSyfE89DvEzWfDU0iybMA" http://localhost:3000/items
[]
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

