# セットアップ手順ログ

```
brew update
brew install elixir
mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v1.0.1/phoenix_new-1.0.1.ez
```

```
mix phoenix.new phoenix_test
cd phoenix_test/
mix deps.get
heroku create --buildpack "https://github.com/HashNuke/heroku-buildpack-elixir.git"
vi elixir_buildpack.config
echo 'web: mix phoenix.server' > Procfile
heroku buildpacks:add https://github.com/gjaldon/heroku-buildpack-phoenix-static.git
```

# PhoenixTest

```
We are all set! Run your Phoenix application:

    $ cd phoenix_test/
    $ mix deps.get
    $ mix ecto.create
    $ mix phoenix.server

You can also run your app inside IEx (Interactive Elixir) as:

    $ iex -S mix phoenix.server
```

To start your Phoenix app:

  1. Install dependencies with `mix deps.get`
  2. Create and migrate your database with `mix ecto.create && mix ecto.migrate`
  3. Start Phoenix endpoint with `mix phoenix.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](http://www.phoenixframework.org/docs/deployment).

## Learn more

  * Official website: http://www.phoenixframework.org/
  * Guides: http://phoenixframework.org/docs/overview
  * Docs: http://hexdocs.pm/phoenix
  * Mailing list: http://groups.google.com/group/phoenix-talk
  * Source: https://github.com/phoenixframework/phoenix
