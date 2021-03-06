# Docker Exec Image: s

A Dockerfile describing an container capable of executing s source files.

# Build

```sh
git clone https://github.com/docker-exec/scala.git
docker build -t dexec/lang-scala .
```

# Usage

In a directory containing a script e.g. foo.scala, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.scala:/tmp/dexec/build/foo.scala \
    dexec/lang-scala foo.scala
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.scala:/tmp/dexec/build/foo.scala \
    dexec/lang-scala foo.scala \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
