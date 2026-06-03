# browsertricky

This is a tiny script and directory structure I've used to make it a bit easier
to run and manage [browsertrix-crawler] for archiving websites without needing
to remember the Docker incantation. It works with either Docker or Podman (and
prefers Podman if it is available).

If you'd like to use it:

```
$ git clone https://github.com/edsu/browsertricky.git
$ cd browsertricky
./browsertricky example
```

Now go to https://replayweb.page and load the [WACZ] file that was created at `collections/example/example.wacz`. 

That's not a terribly interesting example, so use the example config to create a new one:

```
cp config/example.yaml config/mysite.yaml
```

Edit the `config/mysite.yaml` adding information about a site you would like to archive:

1. Change the name of the collection from `example` to `mysite`
2. Change the `seeds` list to include a new URL like `https://mysite.com`

And run it!

```
$ ./browsertricky mysite
```

If you open http://localhost:9037 while the crawl is underway you should see a screencast of the browser.

You can also see what the progress is:

```
$ ./progress mysite
mysite: 595/2517 [254M]
```

Or run it with [watch] to update every few seconds:

```
$ watch -n 10 ./progress mysite
```

Once it is finished you should see a WACZ file at `collections/mysite/mysite.wacz`

See the [documentation] for the available options for the [YAML configuration],
and how to write your own [custom behaviors] to control the behavior of the
browser as it is crawling.

[browsertrix-crawler]: https://github.com/webrecorder/browsertrix-crawler
[WACZ]: https://specs.webrecorder.net/wacz/latest/
[YAML configuration]: https://crawler.docs.browsertrix.com/user-guide/yaml-config/
[custom behaviors]: https://crawler.docs.browsertrix.com/user-guide/behaviors/
[documentation]: https://crawler.docs.browsertrix.com/
[watch]: https://en.wikipedia.org/wiki/Watch_(command)
