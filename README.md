# browsertricky

This is a tiny script and directory structure I've used to make it a bit easier
to run and manage [browsertrix-crawler] for archiving websites without needing
to remember the Docker incantation.

If you'd like to use it:

```
$ git clone https://github.com/edsu/browsertricky.git
$ cd browsertricky
./browsertricky example
```

Now go to https://replayweb.page and load the WACZ file that was created at `collections/example/example.wacz`. 

That's not a terribly interesting example, so use the example config to create a new one:

```
cp config/example.yaml config/mysite.yaml
```

Now edit the `config/mysite.yaml`:

1. Change the name of the collection from `example` to `mysite`
2. Change the `seeds` list to include a new URL like `https://mysite.com`

And run it!

```
$ ./browsertricky mysite
```

If you open http://localhost:9037 while the crawl is underway you should see a screencast of the browser.

Read the browsertrix-crawler [documentation] for all the options you can put in your YAML configuration files. There are quite a few!

[browsertrix-crawler]: https://github.com/webrecorder/browsertrix-crawler
[documentation]: https://github.com/webrecorder/browsertrix-crawler/blob/main/README.md
