## About

This is a memcache client library for the Go programming language
(http://golang.org/).

### Differences from the upstream (bradfitz) repo

- Added a `SetMaxIdleConnsPerAddr` method

## Installing

### Using *go get*

    $ go get github.com/sendgrid/gomemcache/memcache

After this command *gomemcache* is ready to use. Its source will be in:

    $GOPATH/src/github.com/sendgrid/gomemcache/memcache

## Example

    import (
            "github.com/sendgrid/gomemcache/memcache"
    )

    func main() {
         mc := memcache.New("10.0.0.1:11211", "10.0.0.2:11211", "10.0.0.3:11212")
         mc.Set(&memcache.Item{Key: "foo", Value: []byte("my value")})
         mc.SetMaxIdleConnsPerAddr(10) // default is 2

         it, err := mc.Get("foo")
         ...
    }

## Full docs, see:

See https://godoc.sendgrid.net:8888/pkg/github.com/sendgrid/gomemcache/memcache

Or run:

    $ godoc github.com/sendgrid/gomemcache/memcache

