# Running the webhook server

`ansible-rulebook --rulebook rules.yml -i inventory.yml --verbose`


### Setting JAVA_HOME for use with jpy

`ansible-rulebook` requires Java to operate. As part of the installation or development,
you need to set `$JAVA_HOME` correctly.

For MacOS, you can use `homebrew` to install `openjdk` - however you must set JAVA_HOME
to be a path that is a bit more explicit than usual, in order for [jpy][jpy] to correctly function.

```
export JAVA_HOME=/opt/homebrew/opt/openjdk@17/libexec/openjdk.jdk/Contents/Home
```

### Curl invocation

There's a sample JSON request in the repo, you can use it to send to the endpoint, to kick
off the playbook

```
curl -d @rule.json 127.0.0.1:5000/endpoint
```


[jpy]: https://github.com/jpy-consortium/jpy
