# Encora GO

## 3. Find the right package for following:
### 3.1: Exposing a websocket server to a browser for server push communication
We can use [gorilla-websocket](https://github.com/gorilla/websocket).
It provides a complete and tested implementation of the WebSocket protocol. The package API is stable.


### 3.2: Parsing an xml file (DOM or SAX, when do you choose which?)
> SAX (Simple API for XML)
- Event based parser (Sequence of events).
- SAX parses the file as it reads it, i.e. parses node by node.
- No memory constraints as it does not store the XML content in the memory.
- SAX is read only i.e. can’t insert or delete the node.
- Use SAX parser when memory content is large.
- SAX reads the XML file from top to bottom and backward navigation is not possible.
- Faster at run time.

We can use [gosax](https://pkg.go.dev/github.com/eliben/gosax), Its GO wrapper for libxml SAX 
because sometimes the DOM tree output is just too large to fit reasonably into memory, it's better to use the SAX interface of libxml.

> DOM (Document Object Model)
- Tree model parser (Object based) (Tree of nodes).
- DOM loads the file into the memory and then parse the file.
- Has memory constraints since it loads the whole XML file before parsing.
- DOM is read and write (can insert or delete nodes).
- If the XML content is small, then prefer DOM parser.
- Backward and forward search is possible, so this gives the ease of navigation.
- Slower at run time.

We can use [go-xmldom](https://pkg.go.dev/github.com/stmath/go-xmldom), Its XML DOM processing for Golang, supports xpath query.


### 3.3: An embedded Key Value store which would typically have ~100mb of data and be 99% reads
We can use [BadgerDB](https://github.com/dgraph-io/badger).
BadgerDB is an embeddable, persistent and fast key-value (KV) database written in pure Go.
It is the underlying database for Dgraph, a fast, distributed graph database. 
It's meant to be a performant alternative to non-Go-based key-value stores like RocksDB.
Badger is stable and is being used to serve data sets worth hundreds of terabytes


### 3.4: A system to auto-discover other instances of a service on the same network
We can use [go-sdiscovery](https://pkg.go.dev/github.com/nathan-osman/go-sdiscovery).
It provides an extremely simple API that abstracts the process of registering a service available over the local network and discovering other peers providing the service.
This is accomplished by sending broadcast (IPv4) and multicast (IPv6) packets at regular intervals over connected network interfaces.

