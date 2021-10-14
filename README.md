# docker-compose-flarum

Manage Flarum with docker-compose

### Start Flarum Server

```
docker-compose up -d
```

### Restart Server (Containers)

```
docker-compose restart
# or
docker-compose restart flarum
# or
docker-compose stop
docker-compose start
# or
docker-compose stop flarum
docker-compose start flarum
```

### Install an extension

```
docker-compose exec flarum extension require some/extension
```

### Remove an extension

```
docker-compose exec flarum extension remove some/extension
```

### List all extensions

```
docker-compose exec flarum extension list
```

### Updating your database and removing old assets & extensions

```
docker-compose exec flarum php /flarum/app/flarum migrate
docker-compose exec flarum php /flarum/app/flarum cache:clear
```

### More commands

```
docker-compose exec flarum php /flarum/app/flarum --help
docker-compose exec flarum php /flarum/app/flarum info
```

### Upgrade

```
docker-compose exec flarum composer update --prefer-dist --no-plugins --no-dev -a --with-all-dependencies -d /flarum/app/ \
&& docker-compose exec flarum php /flarum/app/flarum migrate \
&& docker-compose exec flarum php /flarum/app/flarum cache:clear
```

### Crontab

```
* * * * * cd /path-to-your-project && /usr/local/bin/docker-compose exec -T flarum php /flarum/app/flarum schedule:run >> /dev/null 2>&1
```

https://discuss.flarum.org/d/24118-setup-the-flarum-scheduler-using-cron

### Generate sitemap

```
docker-compose exec flarum php /flarum/app/flarum fof:sitemap:build
```

## Extensions

```
flarum-lang/chinese-simplified
fof/filter
v17development/flarum-seo
fof/analytics
fof/pages
fof/links
# fof/best-answer
fof/sitemap
fof/follow-tags
ianm/syndication
fof/disposable-emails
fof/recaptcha
fof/doorman
fof/reactions
fof/gamification
fof/forum-statistics-widget
# flagrow/ads
fof/github-autolink
fof/stopforumspam
fof/terms
itnt/flarum-backtop
itnt/flarum-uitab
michaelbelgium/flarum-discussion-views
fof/drafts
fof/ignore-users
fof/socialprofile
fof/impersonate
fof/oauth
fof/user-directory
clarkwinkelmann/flarum-ext-author-change
clarkwinkelmann/flarum-ext-create-user-modal
clarkwinkelmann/flarum-ext-manual-discussion-slug
pipecraft/flarum-ext-id-slug
fof/formatting
davwheat/custom-sidenav-links
```

Find Extensions

- https://bbs.csur.fun/d/84-flarum
- https://discuss.flarum.org.cn/d/1246
- https://discuss.flarum.org.cn/d/325

Flarum Docs:

- https://docs.flarum.org/

Flarum Community:

- https://discuss.flarum.org/
- https://discuss.flarum.org.cn/

Flarum Release:

- https://github.com/flarum/core/releases

Flarum Docker:

- https://github.com/mondediefr/docker-flarum

## Related

- [flarum/flarum](https://github.com/flarum/flarum) - Simple forum software for building great communities.
- [flarum/core](https://github.com/flarum/core) - Simple forum software for building great communities.
- [docker-flarum](https://github.com/mondediefr/docker-flarum) - 💬 🐳 Docker image of Flarum

## License

Copyright (c) 2021 [Pipecraft][my-url]. Licensed under the [MIT license][license-url].

## >\_

[![Pipecraft](https://img.shields.io/badge/https://-pipecraft.net-brightgreen)](https://www.pipecraft.net)
[![PZWD](https://img.shields.io/badge/https://-pzwd.net-brightgreen)](https://pzwd.net)

[my-url]: https://www.pipecraft.net
[license-url]: LICENSE
