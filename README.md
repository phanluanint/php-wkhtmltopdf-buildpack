# PHP wkhtmltopdf Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [wkhtmltopdf][1]
binary with environment stack. 

**It only work with `heroku/php` buildpack** and working on `heroku-16` and `heroku-18` stack.

## Versions

* Buildpack:   `0.2`
* wkhtmltopdf: `0.12.3` by default

## Usage

[Add this buildpack][2] to your Heroku application to install the `wkhtmltopdf`
and `wkhtmltoimage` binaries, and the corresponding library `libwkhtmltox`,
into the dynos:

```bash
$ heroku buildpacks:add https://github.com/phanluanint/php-wkhtmltopdf-buildpack.git
```

If you want to use a `wkhtmltopdf` version other than 0.12.3, set
`WKHTMLTOPDF_VERSION`:

```bash
heroku config:set WKHTMLTOPDF_VERSION="0.12.4"
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on `cedar-14`, `heroku-16` and `heroku-18`. You can check this with:

```bash
$ heroku stack
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: http://wkhtmltopdf.org/
[2]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
