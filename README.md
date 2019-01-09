# Traefik-ify

[![Roots](https://img.shields.io/badge/dynamic/json.svg?url=https://raw.githubusercontent.com/roots/roots-example-project.com/master/site/composer.json?token=R2l0SHViIFRva2VuIEdvZXMgSGVyZQ==&label=wordpress&logo=roots&logoColor=white&query=$.require["roots/wordpress"]&colorB=2b3072&colorA=525ddc)](//roots.io) ![Docker](https://img.shields.io/badge/docker-rules-blue.svg) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/3e0216bab8504573b62ce72b4441c2e2)](https://www.codacy.com/app/pixelcollective/traefik-ify?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=pixelcollective/traefik-ify&amp;utm_campaign=Badge_Grade) [![Reviewed by Hound](https://img.shields.io/badge/Reviewed_by-Hound-8E64B0.svg)](https://houndci.com) [![Gitter](https://img.shields.io/badge/chat-on%20gitter-purple.svg)](https://gitter.im/Tiny-Pixel/Traefik-ify?utm_source=share-link&utm_medium=link&utm_campaign=share-link)

> Easily Traefik-ify your roots/bedrock WordPress installation. It's great! It's super easy to do! Nothing to lose (except some port conflicts!)

And it's basically non-destructive for an existing Trellis setup. Dank.

## Requirements

1. Docker
2. Docker-compose

## Try it out

The following assumes you are running [Bedrock](https://github.com/roots/bedrock) in a local environment.

Run the following commands from the `traefik` directory:

1. `docker network create traefikify`
2. `docker-compose up -d`

Run the following commands from the `example.com` directory:

1. `composer install`
2. `mv env.example .env`
3. `docker-compose up -d`

You will then need to add `example.test` to `/etc/hosts`, or however you manage your virtual hosts.

The WordPress installation screen should be available at `example.test`. Additionally, you can monitor traefik at `localhost`.

## Add to existing install

The `mixins` directory contains everything you need.

1. Copy `./config/docker/` to your `config` directory.
2. Copy `./Dockerfile` to bedrock root.
3. Copy `./docker-compose.yml` to bedrock root.
4. Add `database` to your `.gitignore` 🙀
5. Make sure the variables in the traefik-ify `env.example` are included in your existing `.env`. It should look something like this:

``` env
WP_ENV=development
DOMAIN_CURRENT_SITE=example.test
WP_HOME=http://example.test
WP_SITEURL=http://example.test/wp
DB_NAME=example_test_development
DB_USER=example_test
DB_PASSWORD=example_test
```

## Party

You should be good to execute `docker-compose up` from `traefik`, then your Bedrock root. You'll notice the database mounts to a directory in Bedrock. You can change this behavior (and lots of other things) in `docker-compose.yml`.

## Credits

* [roots/bedrock](https://github.com/roots/bedrock)
* [austinpray/bedrock-testbed](https://github.com/austinpray/bedrock-testbed)
* [saturate/traefik-wordpress](https://github.com/Saturate/traefik-wordpress)
