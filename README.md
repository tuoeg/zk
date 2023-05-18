Native Go Zookeeper Client Library
===================================

[![GoDoc](https://godoc.org/git.hrlyit.com/packages/zk?status.svg)](https://godoc.org/git.hrlyit.com/packages/zk)
[![Build Status](https://img.shields.io/github/workflow/status/go-zookeeper/zk/unittest/master)](https://git.hrlyit.com/packages/zk/actions?query=branch%3Amaster)
[![Coverage Status](https://img.shields.io/codecov/c/github/go-zookeeper/zk/master)](https://codecov.io/gh/go-zookeeper/zk/branch/master)

# why fork repo
1. When using the original repo to connect zookeeper server,goroutine leakage will occur
2. when connect timeout, loop can't quit

# how to use context

```
ctx, cancelfunc := context.WithTimeout(context.Background(), 1*time.Second)
defer cancelfunc()
c, _, err := zk.Connect(ctx, []string{"host:port"}, 0)
```

License
-------

3-clause BSD. See LICENSE file.
