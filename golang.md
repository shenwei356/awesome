# Golang

## doc

-  [Ten Useful Techniques in Go](http://arslan.io/ten-useful-techniques-in-go)
-  [Effective Go in chinese](http://www.hellogcc.org/effective_go.html)
-  [(Draft) Traps, Gotchas, and Common Mistakes in Go (golang)](http://devs.cloudimmunity.com/gotchas-and-common-mistakes-in-go-golang/)
-  Rob Pike的Go语言PPT教程翻译[1](http://tonybai.com/2012/08/23/the-go-programming-language-tutorial-part1/),[2](http://tonybai.com/2012/08/27/the-go-programming-language-tutorial-part2/),[3](http://tonybai.com/2012/08/28/the-go-programming-language-tutorial-part3/)
-  [Translating Effective Python into Go: Know When to Use Channels for Generator-Like Functions](http://www.informit.com/articles/article.aspx?p=2359758)

## Install packages

Use proxy, or use [Gopm](https://github.com/gpmgo/gopm).
```
http_proxy=127.0.0.1:8087 go get **
```

for socks5 proxy

```
sudo dnf install privoxy
sudo echo forward-socks5 / 127.0.0.1:1080 . >> /etc/privoxy/config
sudo service privoxy restart
http_proxy=127.0.0.1:8118 go get **
```

Godoc and vet moved to the go.tools subrepository since go1.2, so

```
# go get code.google.com/p/go.tools/cmd/...
```

More official [sub-repositories](http://golang.org/pkg/#subrepo)

- crypto — additional cryptography packages.
- net — additional networking packages.
- sys — packages for making system calls.
- text — packages for working with text.
- tools — godoc, vet, cover, and other tools.
- exp — experimental code (handle with care; may change without warning).

install them

```
https_proxy=https://127.0.0.1:8118 go get -v golang.org/x/tools/cmd/{godoc,goimports,gorename,vet,gomvpkg,cover}
```

other great tools

```
go get -v github.com/golang/lint/golint
go get -v github.com/sqs/goreturns
```


## Update packages

```
go get -u github.com/astaxie/beego
```

Or use [gofresh](https://github.com/divan/gofresh) (Keep your Go package dependencies fresh.)

## Necessary dev tools

- [gometalinter](https://github.com/alecthomas/gometalinter) - Concurrently run Go lint tools and normalise their output
- goimports, [see more](https://michaelwhatcott.com/gosublime-goimports/)


## Programming Patterns

- [composable-go-services-using-libchan/](http://blog.codeship.com/composable-go-services-using-libchan/)
- [go-promise](https://github.com/fanliao/go-promise) - A library implement futrue and promise
- [libchan](https://github.com/docker/libchan) - Like Go channels over the network,
- [go-broadcast](https://github.com/dustin/go-broadcast) - A trivial channel pubsub I use in lots of projects. http://godoc.org/github.com/dustin/go-broadcast
- [tunny](https://github.com/Jeffail/tunny) - A goroutine pool for golang

## Data Structure

- **[go-datastructures](https://github.com/Workiva/go-datastructures)** - Go-datastructures is a collection of useful, performant, and threadsafe Go datastructures.
- [golang-set](https://github.com/deckarep/golang-set) - A simple set type for the Go language.
- [set](https://github.com/fatih/set) - Set is a basic and simple, hash-based, Set data structure implementation in Go (Golang)
- [pmap (ParallelMap)](https://github.com/shenwei356/pmap) - A lock-free parallel map in go
- [lane](https://github.com/oleiade/lane) - A golang queues, stacks and deques implementation library
- [btree](https://github.com/google/btree) - by google
- [bloom](https://github.com/willf/bloom) - Go package implementing Bloom filters
- [bitset](https://github.com/willf/bitset) - Go package implementing bitsets
- **[BoomFilters](://github.com/tylertreat/BoomFilters)** - Probabilistic data structures for processing continuous, unbounded streams. This includes Stable Bloom Filters, Scalable Bloom Filters, Counting Bloom Filters, Inverse Bloom Filters, Cuckoo Filters, several variants of traditional Bloom filters, HyperLogLog, Count-Min Sketch, and MinHash
- [goraph](https://github.com/gyuho/goraph) - Package goraph implements graph, tree data structures and algorithms.
- [go-radix](https://github.com/armon/go-radix) - Golang implementation of Radix trees, [go-immutable-radix](https://github.com/hashicorp/go-immutable-radix)

## IO

- [xopen](https://github.com/brentp/xopen) - open files for buffered reading and writing in #golang
- [readahead](https://github.com/klauspost/readahead) - Asynchronous read-ahead for Go readers
- [pgzip](https://github.com/klauspost/pgzip) - Go parallel gzip (de)compression
- [compress](https://github.com/klauspost/compress) - Optimized compression packages
- [breader](https://github.com/shenwei356/breader) - breader (Buffered File Reader), asynchronous parsing and pre-processing while reading file. Safe cancellation is also supported.


## File format

- [xlsx](https://github.com/tealeg/xlsx) - Google Go (golang) library for reading and writing XLSX files.

## Algorithm

- [graph](https://github.com/gonum/graph) - Graph packages for the Go language
- [golearn](https://github.com/sjwhitworth/golearn) - Machine Learning for Go
- [gonn](https://github.com/fxsjy/gonn) -GoNN is an implementation of Neural Network in Go Language, which includes BPNN, RBF, PCN
- [CloudForest](https://github.com/ryanbressler/CloudForest) - Ensembles of decision trees in go/golang.

## Math

- [geom](https://github.com/skelterjohn/geom) - 2d geometry for golang
- [gonum](https://github.com/gonum)

## Statistics

- [stats](https://github.com/montanaflynn/stats) - A statistics package with common functions that are missing from the Golang standard library.
- [stat](https://github.com/grd/stat) - https://github.com/grd/stat  t-test
- [stat](https://github.com/gonum/stat) - Statistics package for Go

## NLP

- [go-pinyin]( https://github.com/mozillazg/go-pinyin)

## Util

log

- [log4go ](http://code.google.com/p/log4go/)- Logging package similar to log4j for the Go programming language
- [log15](https://github.com/inconshreveable/log15) - Simple, powerful logging for Go

Others

- [gouuid](https://github.com/nu7hatch/gouuid) - Pure Go UUID implementation
- [quarnster/util](https://github.com/quarnster/util) - Various Go utility code
- [daemon](https://github.com/takama/daemon) - A daemon package for use with Go (golang) services with no dependencies
- [shutdown](https://github.com/klauspost/shutdown) - Shutdown management library for Go
- [Gox](https://github.com/mitchellh/gox) - Simple Go Cross Compilation。更新go版本后，记得gox -build-toolchain
- [clipboard](https://github.com/atotto/clipboard) - clipboard for golang

Date

- [monday](https://github.com/mikespook/) - Monday is a minimalistic translator for month and day of week names in time.Date objects
- [Now](https://github.com/jinzhu/now) - Now is a time toolkit for golang


## CLI

- **[cobra](https://github.com/spf13/cobra)** - A Commander for modern Go CLI interactions
- [writ](https://github.com/bobziuchkovski/writ) - A flexible command and option parser for Go
- [go-arg](https://github.com/alexflint/go-arg) - Struct-based argument parsing in Go
- [cli](https://github.com/codegangsta/cli) - A small package for building command line apps in Go
- **[color](https://github.com/fatih/color)** - Color package for Go (golang) [http://godoc.org/github.com/fatih/color](http://godoc.org/github.com/fatih/color) . It has support for Windows too
- [Console progress bar for Golang](https://github.com/cheggaaa/pb)
- [emoji](https://github.com/kyokomi/emoji) - emoji terminal output for golang
- [go-sh](https://github.com/codeskyblue/go-sh) - like python-sh, for easy call shell with golang.
- [uitable ](https://github.com/gosuri/uitable) - A go library to improve readability in terminal apps using tabular data
- **[uiprogress](https://github.com/gosuri/uiprogress)** - A go library to render (multi) progress bars in terminal applications.
- [pb](https://github.com/cheggaaa/pb) - Console progress bar for Golang
- [viper](https://github.com/spf13/viper) -Go configuration with fangs
- [goconfig](https://github.com/Unknwon/goconfig) - goconfig is a easy-use comments-support configuration file(.ini) parser for the Go Programming Language
- [go-homedir](https://github.com/mitchellh/go-homedir) - Go library for detecting and expanding the user's home directory without cgo.

## JSON

- [ffjson](https://github.com/pquerna/ffjson): faster JSON for Go
- [megajson](https://github.com/benbjohnson/megajson) - A JSON parser generator for high performance encoding and decoding in Go.
- [gojson](https://github.com/ChimeraCoder/gojson) - A simple command-line tool for manipulating JSON for use in developing Go cod
- [jsonpp](https://github.com/jmhodges/jsonpp) - A command line JSON pretty printer.

## Text

- [go-humanize](https://github.com/dustin/go-humanize) - Go Humans! (formatters for units to human friendly sizes) https://godoc.org/github.com/dustin/go-humanize
- [A modern text indexing library for go](https://github.com/blevesearch/bleve)
- [govalidator](https://github.com/asaskevich/govalidator) - Package of string validators and sanitizers for Go lang
- [iconv](https://github.com/qiniu/iconv) - Golang bindings to libiconv - Convert string to requested character encoding

## Markdown

- [blackfriday ](https://github.com/russross/blackfriday)- a markdown processor for Go

## WEB

- [go.rice](https://github.com/GeertJohan/go.rice) is a Go package that makes working with resources such as html,js,css,images,templates, etc very easy.
- **[gin](https://gin-gonic.github.io/gin/)** - Gin is a HTTP web framework written in Go (Golang). It features a Martini-like API with much better performance, up to 40 times faster. If you need smashing performance, get yourself some Gin.
- [beego](https://github.com/astaxie/beego) - beego is an open-source, high-performance web framework for the Go programming language. [http://beego.me](http://beego.me/)
- [echo](https://github.com/labstack/echo) - Echo is a fast :rocket: and unfancy micro web framework for Golang. http://echo.labstack.com
- [ace](https://github.com/yosssi/ace) - HTML template engine for Go [http://ace.yoss.si/](http://ace.yoss.si/)
- [osin]https://github.com/RangelReale/osin - Golang OAuth2 server library
- [go-oauth](https://github.com/garyburd/go-oauth) - OAuth 1.0 client package for Go
- [go-http-auth](https://github.com/abbot/go-http-auth) - Basic and Digest HTTP Authentication for golang http
- [gomniauth](https://github.com/stretchr/gomniauth) - Authentication framework for Go applications.
- [hawk](https://github.com/hueniverse/hawk))  - HTTP Holk Authentication Schemz
- [gopencils](https://github.com/bndr/gopencils) - Easily consume REST APIs with Go (golang)
- [code.google.com/p/go.crypto/ssh](https://godoc.org/code.google.com/p/go.crypto/ssh) - Package ssh implements an SSH client and server. [example](http://kukuruku.co/hub/golang/ssh-commands-execution-on-hundreds-of-servers-via-go)
- [go-pkg-rss](https://github.com/jteeuwen/go-pkg-rss) - reads RSS and Atom feeds and provides a caching mechanism that adheres to the feed specs.
- [feeds](https://github.com/gorilla/feeds) - golang rss/atom generator library
- [postman](https://github.com/zachlatta/postman) - Command-line utility for batch-sending email. http://zachlatta.com/postman
- [gomail](https://github.com/go-gomail/gomail) - The best way to send emails in Go.
- [go-i18n](https://github.com/nicksnyder/go-i18n) - Translate your Go program into multiple languages with templates and CLDR plural support.
- [gorequest](https://github.com/parnurzeal/gorequest) - GoRequest -- Simplified HTTP client ( inspired by nodejs SuperAgent ) http://parnurzeal.github.io/gorequest/

## DB

KV

- [goleveldb](https://github.com/syndtr/goleveldb) - LevelDB key/value database in Go.
- [bolt](https://github.com/boltdb/bolt) - A low-level key/value database for Go.
- [etcd](https://github.com/coreos/etcd) - A highly-available key value store for shared configuration and service discovery

In-memory

- [go-memdb](https://github.com/hashicorp/go-memdb) - Golang in-memory database built on immutable radix trees
- [yakdb](https://github.com/needcaffeine/yakdb) - yakdb (yet another key-value database) is a highly-performant in-memory key-value store written in Go. http://vicvijayakumar.com/yakdb-a-nosql-database-in-go.html

doc

- [tiedot](https://github.com/HouzuoGuo/tiedot) - a document database engine that uses JSON as document notation

rich data structure

- [SSDB](https://github.com/ideawu/ssdb) - A fast NoSQL database for storing big list of data
- [ledisdb](https://github.com/siddontang/ledisdb) - a high performance NoSQL powered by Go
- [tidb](https://github.com/pingcap/tidb) - TiDB is a distributed SQL database compatible with MySQL protocol.

## ORM

- [gorm](https://github.com/jinzhu/gorm) - The fantastic ORM library for Golang, aims to be developer friendly
- [go-sqlite3](https://github.com/mattn/go-sqlite3) - sqlite3 driver for go that using database/sql [http://mattn.kaoriya.net/](http://mattn.kaoriya.net/)
- [beego orm](https://github.com/astaxie/beego/tree/master/orm) - A powerful orm framework for go
- [qbs](https://github.com/coocood/) - QBS stands for Query By Struct. A Go ORM

## GUI

- [go-qt5 ](https://github.com/salviati/go-qt5)- qt5 bindings for go

## Figure and Chart

- [plotinum](https://code.google.com/p/plotinum/) - A plotting library for the Go programming language.
- [chart](https://github.com/vdobler/chart) - Basic charts in go. This package focuses more on autoscaling, error bars, and logarithmic plots than on beautifull or marketing ready charts.
- [gosplat ](https://github.com/agonopol/gosplat)- Easily generate html/js graphs in go with dygraphs/gochart
- [svgo](https://github.com/ajstarks/svgo) - Go Language Library for SVG generation. [paper](http://www.svgopen.org/2011/papers/34-SVGo_a_Go_Library_for_SVG_generation/), [slide](https://speakerdeck.com/ajstarks/programming-pictures-with-svgo)
- [gonum/plot](https://github.com/gonum/plot/wiki/Example-plots), [example](https://github.com/gonum/plot/wiki/Example-plots)

## Image

- [gift](https://github.com/disintegration/gift) - Go Image Filtering Toolkit

## 3D

-  [ln](https://github.com/fogleman/ln) - 3D line art engine.


## HPC

- [hpcgo](https://github.com/drio/hpcgo) - Helping submit jobs to HPC cluster
- [mpi](https://github.com/marcusthierfelder/mpi) - mpi-binding for golang
- [circuit](https://github.com/gocircuit/circuit)
- [go-workers](https://github.com/jrallison/go-workers) - Sidekiq compatible background workers in golang
- [glow](https://github.com/chrislusf/glow) - Glow is an easy-to-use distributed computation system written in Go, similar to Hadoop Map Reduce, Spark, Flink, Samza, etc. Currently just started and not feature rich yet, but should be reliable to run most common cases.

## Flow / piple

- [goflow](https://github.com/trustmaster/goflow) - Flow-based and dataflow programming library for Go programming language


## Glue

- [gopy](https://github.com/go-python/gopy) generates a CPython extension module from a go package.

[Go projects index](https://code.google.com/p/go-wiki/wiki/Projects)

See more on [awesome-go](https://github.com/avelino/awesome-go), [golang opensource projects](http://www.open-open.com/lib/view/open1396063913278.html#Command-line_Option_Parsers)

## misc

- [range over interface{} which stores a slice](https://stackoverflow.com/questions/14025833/range-over-interface-which-stores-a-slice/14026030#14026030)
