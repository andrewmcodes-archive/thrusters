![thrusters](https://i.imgur.com/4ckTCWf.png)

# Thrusters

Thrusters is an opinionated Rails app bootstrapper.

**Rails Version**: 5.2

**Ruby Version**: 2.6.1

## Getting Started

### Requirements

You'll need the following installed to run the template successfully:

* Ruby 2.6.1
  * Editable via `.ruby-version` file
* Bundler
  * `gem install bundler`
* Rails
  * `gem install rails`
* Yarn
  * `brew install yarn`
* Foreman (optional)
  * `gem install foreman`

### Creating a new app

```bash
rails new myapp -d postgresql -m https://raw.githubusercontent.com/andrewmcodes/thrusters/master/template.rb
```

Or if you have downloaded this repo, you can reference template.rb locally:

```bash
rails new myapp -d postgresql -m template.rb
```

To run your app, use `foreman start`.

This will run `Procfile.dev` via `foreman start -f Procfile.dev` as configured by the `.foreman` file and will launch the development processes `rails server`, `sidekiq`, and `webpack-dev-server` processes. You can also run them in separate terminals manually if you prefer.

A separate `Procfile` is generated for deploying to production.

### Authenticate with social networks

We use the encrypted Rails Credentials for app_id and app_secrets when it comes to omniauth authentication. Edit them as so:

```
EDITOR=code rails credentials:edit
```

Make sure your file follow this structure:

```yml
secret_key_base: [your-key]
development:
  github:
    app_id: something
    app_secret: something
    options:
      scope: 'user:email'
      whatever: true
production:
  github:
    app_id: something
    app_secret: something
    options:
      scope: 'user:email'
      whatever: true
```

With the environment, the service and the app_id/app_secret. If this is done correctly, you should see login links
for the services you have added to the encrypted credentials using `EDITOR=code rails credentials:edit`

### Cleaning up

```bash
rails db:drop
spring stop
cd ..
rm -rf myapp
```

## Contributing

[Contributing Guide](/CONTRIBUTING.md)

## Code of Conduct

[Code of Conduct](/CODE_OF_CONDUCT.md)

## Recognition

This project was originally forked from [excid3/jumpstart](https://github.com/excid3/jumpstart). Many thanks to [Chris Oliver](https://github.com/excid3) for creating this awesome project.
