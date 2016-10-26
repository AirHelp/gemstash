# gemstash
Docker image for gemstash

### Build container

```
docker build --pull -t airhelp/gemstash .
```

### Start container

```
docker run -i --rm --name gemstash \
  -v /root/.gemstash:/root/.gemstash \
  -p 9292:9292 \
  airhelp/gemstash
```

### Configure Bundler

Now, you can tell Bundler to use Gemstash container:

```
$ bundle config mirror.https://rubygems.org http://localhost:9292
```

optionally you can enable fallback to rubygems.org

```
$ bundle config mirror.https://rubygems.org.fallback_timeout true
```

and set timeout

```
$ bundle config mirror.https://rubygems.org.fallback_timeout 3
```

For more details go to: https://github.com/bundler/gemstash
