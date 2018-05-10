# metrics in ETH

## Counter

### Counter Usage

```go
registeredCounter := NewRegisteredCounter(name, nil)
```

### ETH Counter

>*database_utils.go* `go-ethereum/core`

```go
preimageCounter    = metrics.NewRegisteredCounter("db/preimage/total", nil)
preimageHitCounter = metrics.NewRegisteredCounter("db/preimage/hits", nil)
```

>*tx_pool.go* `go-ethereum/core`

```go
// Metrics for the pending pool
pendingDiscardCounter   = metrics.NewRegisteredCounter("txpool/pending/discard", nil)
pendingReplaceCounter   = metrics.NewRegisteredCounter("txpool/pending/replace", nil)

// Dropped due to rate limiting
pendingRateLimitCounter = metrics.NewRegisteredCounter("txpool/pending/ratelimit", nil)
// Dropped due to out-of-funds
pendingNofundsCounter   = metrics.NewRegisteredCounter("txpool/pending/nofunds", nil)

// Metrics for the queued pool
queuedDiscardCounter   = metrics.NewRegisteredCounter("txpool/queued/discard", nil)
queuedReplaceCounter   = metrics.NewRegisteredCounter("txpool/queued/replace", nil)

 // Dropped due to rate limiting
queuedRateLimitCounter = metrics.NewRegisteredCounter("txpool/queued/ratelimit", nil)
 // Dropped due to out-of-funds
queuedNofundsCounter   = metrics.NewRegisteredCounter("txpool/queued/nofunds", nil)

// General tx metrics
invalidTxCounter     = metrics.NewRegisteredCounter("txpool/invalid", nil)
underpricedTxCounter = metrics.NewRegisteredCounter("txpool/underpriced", nil)
```

>*api.go* `go-ethereum/swarm/api`

```go
apiResolveCount    = metrics.NewRegisteredCounter("api.resolve.count", nil)
apiResolveFail     = metrics.NewRegisteredCounter("api.resolve.fail", nil)
apiPutCount        = metrics.NewRegisteredCounter("api.put.count", nil)
apiPutFail         = metrics.NewRegisteredCounter("api.put.fail", nil)
apiGetCount        = metrics.NewRegisteredCounter("api.get.count", nil)
apiGetNotFound     = metrics.NewRegisteredCounter("api.get.notfound", nil)
apiGetHttp300      = metrics.NewRegisteredCounter("api.get.http.300", nil)
apiModifyCount     = metrics.NewRegisteredCounter("api.modify.count", nil)
apiModifyFail      = metrics.NewRegisteredCounter("api.modify.fail", nil)
apiAddFileCount    = metrics.NewRegisteredCounter("api.addfile.count", nil)
apiAddFileFail     = metrics.NewRegisteredCounter("api.addfile.fail", nil)
apiRmFileCount     = metrics.NewRegisteredCounter("api.removefile.count", nil)
apiRmFileFail      = metrics.NewRegisteredCounter("api.removefile.fail", nil)
apiAppendFileCount = metrics.NewRegisteredCounter("api.appendfile.count", nil)
apiAppendFileFail  = metrics.NewRegisteredCounter("api.appendfile.fail", nil)
```

>*error.go* `go-ethereum/swarm/api/http`

```go
htmlCounter = metrics.NewRegisteredCounter("api.http.errorpage.html.count", nil)
jsonCounter = metrics.NewRegisteredCounter("api.http.errorpage.json.count", nil)
```

>*server.go* `go-ethereum/swarm/api/http`

```go
postRawCount     = metrics.NewRegisteredCounter("api.http.post.raw.count", nil)
postRawFail      = metrics.NewRegisteredCounter("api.http.post.raw.fail", nil)
postFilesCount   = metrics.NewRegisteredCounter("api.http.post.files.count", nil)
postFilesFail    = metrics.NewRegisteredCounter("api.http.post.files.fail", nil)
deleteCount      = metrics.NewRegisteredCounter("api.http.delete.count", nil)
deleteFail       = metrics.NewRegisteredCounter("api.http.delete.fail", nil)
getCount         = metrics.NewRegisteredCounter("api.http.get.count", nil)
getFail          = metrics.NewRegisteredCounter("api.http.get.fail", nil)
getFileCount     = metrics.NewRegisteredCounter("api.http.get.file.count", nil)
getFileNotFound  = metrics.NewRegisteredCounter("api.http.get.file.notfound", nil)
getFileFail      = metrics.NewRegisteredCounter("api.http.get.file.fail", nil)
getFilesCount    = metrics.NewRegisteredCounter("api.http.get.files.count", nil)
getFilesFail     = metrics.NewRegisteredCounter("api.http.get.files.fail", nil)
getListCount     = metrics.NewRegisteredCounter("api.http.get.list.count", nil)
getListFail      = metrics.NewRegisteredCounter("api.http.get.list.fail", nil)
requestCount     = metrics.NewRegisteredCounter("http.request.count", nil)
htmlRequestCount = metrics.NewRegisteredCounter("http.request.html.count", nil)
jsonRequestCount = metrics.NewRegisteredCounter("http.request.json.count", nil)
// requestTimer     = metrics.NewRegisteredResettingTimer("http.request.time", nil)
```

>*depo.go* `go-ethereum/swarm/network`

```go
syncReceiveCount  = metrics.NewRegisteredCounter("network.sync.recv.count", nil)
syncReceiveIgnore = metrics.NewRegisteredCounter("network.sync.recv.ignore", nil)
syncSendCount     = metrics.NewRegisteredCounter("network.sync.send.count", nil)
syncSendRefused   = metrics.NewRegisteredCounter("network.sync.send.refused", nil)
syncSendNotFound  = metrics.NewRegisteredCounter("network.sync.send.notfound", nil)
```

>*hive.go* `go-ethereum/swarm/network`

```go
// peersNumGauge     = metrics.NewRegisteredGauge("network.peers.num", nil)
addPeerCounter    = metrics.NewRegisteredCounter("network.addpeer.count", nil)
removePeerCounter = metrics.NewRegisteredCounter("network.removepeer.count", nil)

```

>*kademlia.go* `go-ethereum/swarm/network/kademlia`

```go
bucketAddIndexCount[i] = metrics.NewRegisteredCounter(
    fmt.Sprintf("network.kademlia.bucket.add.%d.index", i), nil)
bucketRmIndexCount[i] = metrics.NewRegisteredCounter(
    fmt.Sprintf("network.kademlia.bucket.rm.%d.index", i), nil)
```

>*protocol.go* `go-ethereum/swarm/network`

```go
storeRequestMsgCounter    = metrics.NewRegisteredCounter("network.protocol.msg.storerequest.count", nil)
retrieveRequestMsgCounter = metrics.NewRegisteredCounter("network.protocol.msg.retrieverequest.count", nil)
peersMsgCounter           = metrics.NewRegisteredCounter("network.protocol.msg.peers.count", nil)
syncRequestMsgCounter     = metrics.NewRegisteredCounter("network.protocol.msg.syncrequest.count", nil)
unsyncedKeysMsgCounter    = metrics.NewRegisteredCounter("network.protocol.msg.unsyncedkeys.count", nil)
deliverRequestMsgCounter  = metrics.NewRegisteredCounter("network.protocol.msg.deliverrequest.count", nil)
paymentMsgCounter         = metrics.NewRegisteredCounter("network.protocol.msg.payment.count", nil)
invalidMsgCounter         = metrics.NewRegisteredCounter("network.protocol.msg.invalid.count", nil)
handleStatusMsgCounter    = metrics.NewRegisteredCounter("network.protocol.msg.handlestatus.count", nil)

```

>*chunker.go* `go-ethereum/swarm/storage`

```go
newChunkCounter = metrics.NewRegisteredCounter("storage.chunks.new", nil)
```

>*dbstore.go* `go-ethereum/swarm/storage`

```go
gcCounter            = metrics.NewRegisteredCounter("storage.db.dbstore.gc.count", nil)
dbStoreDeleteCounter = metrics.NewRegisteredCounter("storage.db.dbstore.rm.count", nil)
```

>*localstore.go* `go-ethereum/swarm/storage`

```go
dbStorePutCounter = metrics.NewRegisteredCounter("storage.db.dbstore.put.count", nil)
```

>*memstore.go* `go-ethereum/swarm/storage`

```go
memstorePutCounter    = metrics.NewRegisteredCounter("storage.db.memstore.put.count", nil)
memstoreRemoveCounter = metrics.NewRegisteredCounter("storage.db.memstore.rm.count", nil)
```

>*swarm.go* `go-ethereum/swarm`

```go
startCounter       = metrics.NewRegisteredCounter("stack,start", nil)
stopCounter        = metrics.NewRegisteredCounter("stack,stop", nil)
// uptimeGauge        = metrics.NewRegisteredGauge("stack.uptime", nil)
// dbSizeGauge        = metrics.NewRegisteredGauge("storage.db.chunks.size", nil)
// cacheSizeGauge     = metrics.NewRegisteredGauge("storage.db.cache.size", nil)
```

>*trie.go* `go-ethereum/trie`

```go
cacheMissCounter   = metrics.NewRegisteredCounter("trie/cachemiss", nil)
cacheUnloadCounter = metrics.NewRegisteredCounter("trie/cacheunload", nil)
```

## Gauge

### Gauge Usage

```go
registeredGauge := NewRegisteredGauge(name, nil)
```

### ETH Gauge

>*hive.go* `go-ethereum/swarm/network`

```go
peersNumGauge     = metrics.NewRegisteredGauge("network.peers.num", nil)
// addPeerCounter    = metrics.NewRegisteredCounter("network.addpeer.count", nil)
// removePeerCounter = metrics.NewRegisteredCounter("network.removepeer.count", nil)
```

>*swarm.go* `go-ethereum/swarm`

```go
// startCounter       = metrics.NewRegisteredCounter("stack,start", nil)
// stopCounter        = metrics.NewRegisteredCounter("stack,stop", nil)
uptimeGauge        = metrics.NewRegisteredGauge("stack.uptime", nil)
dbSizeGauge        = metrics.NewRegisteredGauge("storage.db.chunks.size", nil)
cacheSizeGauge     = metrics.NewRegisteredGauge("storage.db.cache.size", nil)
```

## Histogram

### Histogram Usage

```go
registeredHistogram := NewRegisteredHistogram(name, nil)
```

### ETH Histogram

> no Histogram

## Meter

### Meter Usage

```go
registeredMeter := NewRegisteredMeter(name, nil)
```

### ETH Meter

>*metrics.go* `go-ethereum/eth/downloader`

```go
headerInMeter      = metrics.NewRegisteredMeter("eth/downloader/headers/in", nil)
// headerReqTimer     = metrics.NewRegisteredTimer("eth/downloader/headers/req", nil)
headerDropMeter    = metrics.NewRegisteredMeter("eth/downloader/headers/drop", nil)
headerTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/headers/timeout", nil)

bodyInMeter      = metrics.NewRegisteredMeter("eth/downloader/bodies/in", nil)
// bodyReqTimer     = metrics.NewRegisteredTimer("eth/downloader/bodies/req", nil)
bodyDropMeter    = metrics.NewRegisteredMeter("eth/downloader/bodies/drop", nil)
bodyTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/bodies/timeout", nil)

receiptInMeter      = metrics.NewRegisteredMeter("eth/downloader/receipts/in", nil)
// receiptReqTimer     = metrics.NewRegisteredTimer("eth/downloader/receipts/req", nil)
receiptDropMeter    = metrics.NewRegisteredMeter("eth/downloader/receipts/drop", nil)
receiptTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/receipts/timeout", nil)

stateInMeter   = metrics.NewRegisteredMeter("eth/downloader/states/in", nil)
stateDropMeter = metrics.NewRegisteredMeter("eth/downloader/states/drop", nil)
```

>*metrics.go* `go-ethereum/eth/fetcher`

```go
propAnnounceInMeter   = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/in", nil)
// propAnnounceOutTimer  = metrics.NewRegisteredTimer("eth/fetcher/prop/announces/out", nil)
propAnnounceDropMeter = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/drop", nil)
propAnnounceDOSMeter  = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/dos", nil)

propBroadcastInMeter   = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/in", nil)
// propBroadcastOutTimer  = metrics.NewRegisteredTimer("eth/fetcher/prop/broadcasts/out", nil)
propBroadcastDropMeter = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/drop", nil)
propBroadcastDOSMeter  = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/dos", nil)

headerFetchMeter = metrics.NewRegisteredMeter("eth/fetcher/fetch/headers", nil)
bodyFetchMeter   = metrics.NewRegisteredMeter("eth/fetcher/fetch/bodies", nil)

headerFilterInMeter  = metrics.NewRegisteredMeter("eth/fetcher/filter/headers/in", nil)
headerFilterOutMeter = metrics.NewRegisteredMeter("eth/fetcher/filter/headers/out", nil)
bodyFilterInMeter    = metrics.NewRegisteredMeter("eth/fetcher/filter/bodies/in", nil)
bodyFilterOutMeter   = metrics.NewRegisteredMeter("eth/fetcher/filter/bodies/out", nil)
```

>*metrics.go* `go-ethereum/eth`

```go
propTxnInPacketsMeter     = metrics.NewRegisteredMeter("eth/prop/txns/in/packets", nil)
propTxnInTrafficMeter     = metrics.NewRegisteredMeter("eth/prop/txns/in/traffic", nil)
propTxnOutPacketsMeter    = metrics.NewRegisteredMeter("eth/prop/txns/out/packets", nil)
propTxnOutTrafficMeter    = metrics.NewRegisteredMeter("eth/prop/txns/out/traffic", nil)
propHashInPacketsMeter    = metrics.NewRegisteredMeter("eth/prop/hashes/in/packets", nil)
propHashInTrafficMeter    = metrics.NewRegisteredMeter("eth/prop/hashes/in/traffic", nil)
propHashOutPacketsMeter   = metrics.NewRegisteredMeter("eth/prop/hashes/out/packets", nil)
propHashOutTrafficMeter   = metrics.NewRegisteredMeter("eth/prop/hashes/out/traffic", nil)
propBlockInPacketsMeter   = metrics.NewRegisteredMeter("eth/prop/blocks/in/packets", nil)
propBlockInTrafficMeter   = metrics.NewRegisteredMeter("eth/prop/blocks/in/traffic", nil)
propBlockOutPacketsMeter  = metrics.NewRegisteredMeter("eth/prop/blocks/out/packets", nil)
propBlockOutTrafficMeter  = metrics.NewRegisteredMeter("eth/prop/blocks/out/traffic", nil)
reqHeaderInPacketsMeter   = metrics.NewRegisteredMeter("eth/req/headers/in/packets", nil)
reqHeaderInTrafficMeter   = metrics.NewRegisteredMeter("eth/req/headers/in/traffic", nil)
reqHeaderOutPacketsMeter  = metrics.NewRegisteredMeter("eth/req/headers/out/packets", nil)
reqHeaderOutTrafficMeter  = metrics.NewRegisteredMeter("eth/req/headers/out/traffic", nil)
reqBodyInPacketsMeter     = metrics.NewRegisteredMeter("eth/req/bodies/in/packets", nil)
reqBodyInTrafficMeter     = metrics.NewRegisteredMeter("eth/req/bodies/in/traffic", nil)
reqBodyOutPacketsMeter    = metrics.NewRegisteredMeter("eth/req/bodies/out/packets", nil)
reqBodyOutTrafficMeter    = metrics.NewRegisteredMeter("eth/req/bodies/out/traffic", nil)
reqStateInPacketsMeter    = metrics.NewRegisteredMeter("eth/req/states/in/packets", nil)
reqStateInTrafficMeter    = metrics.NewRegisteredMeter("eth/req/states/in/traffic", nil)
reqStateOutPacketsMeter   = metrics.NewRegisteredMeter("eth/req/states/out/packets", nil)
reqStateOutTrafficMeter   = metrics.NewRegisteredMeter("eth/req/states/out/traffic", nil)
reqReceiptInPacketsMeter  = metrics.NewRegisteredMeter("eth/req/receipts/in/packets", nil)
reqReceiptInTrafficMeter  = metrics.NewRegisteredMeter("eth/req/receipts/in/traffic", nil)
reqReceiptOutPacketsMeter = metrics.NewRegisteredMeter("eth/req/receipts/out/packets", nil)
reqReceiptOutTrafficMeter = metrics.NewRegisteredMeter("eth/req/receipts/out/traffic", nil)
miscInPacketsMeter        = metrics.NewRegisteredMeter("eth/misc/in/packets", nil)
miscInTrafficMeter        = metrics.NewRegisteredMeter("eth/misc/in/traffic", nil)
miscOutPacketsMeter       = metrics.NewRegisteredMeter("eth/misc/out/packets", nil)
miscOutTrafficMeter       = metrics.NewRegisteredMeter("eth/misc/out/traffic", nil)
```

>*database.go* `go-ethereum/ethdb`

```go
// Initialize all the metrics collector at the requested prefix
db.compTimeMeter = metrics.NewRegisteredMeter(prefix+"compact/time", nil)
db.compReadMeter = metrics.NewRegisteredMeter(prefix+"compact/input", nil)
db.compWriteMeter = metrics.NewRegisteredMeter(prefix+"compact/output", nil)
db.diskReadMeter = metrics.NewRegisteredMeter(prefix+"disk/read", nil)
db.diskWriteMeter = metrics.NewRegisteredMeter(prefix+"disk/write", nil)

// Initialize write delay metrics no matter we are in metric mode or not.
db.writeDelayMeter = metrics.NewRegisteredMeter(prefix+"compact/writedelay/duration", nil)
db.writeDelayNMeter = metrics.NewRegisteredMeter(prefix+"compact/writedelay/counter", nil)
```

>*metrics.go* `go-ethereum/les`

```go
miscInPacketsMeter  = metrics.NewRegisteredMeter("les/misc/in/packets", nil)
miscInTrafficMeter  = metrics.NewRegisteredMeter("les/misc/in/traffic", nil)
miscOutPacketsMeter = metrics.NewRegisteredMeter("les/misc/out/packets", nil)
miscOutTrafficMeter = metrics.NewRegisteredMeter("les/misc/out/traffic", nil)
```

>*metrics.go* `go-ethereum/p2p`

```go
ingressConnectMeter = metrics.NewRegisteredMeter("p2p/InboundConnects", nil)
ingressTrafficMeter = metrics.NewRegisteredMeter("p2p/InboundTraffic", nil)
egressConnectMeter  = metrics.NewRegisteredMeter("p2p/OutboundConnects", nil)
egressTrafficMeter  = metrics.NewRegisteredMeter("p2p/OutboundTraffic", nil)
```

## Timer

### Timer Usage

```go
registeredTimer := NewRegisteredTimer(name, nil)
```

### ETH Timer

>*blockchain.go* `go-ethereum/core`

```go
blockInsertTimer = metrics.NewRegisteredTimer("chain/inserts", nil)
```

>*metrics.go* `go-ethereum/eth/downloader`

```go
// headerInMeter      = metrics.NewRegisteredMeter("eth/downloader/headers/in", nil)
headerReqTimer     = metrics.NewRegisteredTimer("eth/downloader/headers/req", nil)
// headerDropMeter    = metrics.NewRegisteredMeter("eth/downloader/headers/drop", nil)
// headerTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/headers/timeout", nil)

// bodyInMeter      = metrics.NewRegisteredMeter("eth/downloader/bodies/in", nil)
bodyReqTimer     = metrics.NewRegisteredTimer("eth/downloader/bodies/req", nil)
// bodyDropMeter    = metrics.NewRegisteredMeter("eth/downloader/bodies/drop", nil)
// bodyTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/bodies/timeout", nil)

// receiptInMeter      = metrics.NewRegisteredMeter("eth/downloader/receipts/in", nil)
receiptReqTimer     = metrics.NewRegisteredTimer("eth/downloader/receipts/req", nil)
// receiptDropMeter    = metrics.NewRegisteredMeter("eth/downloader/receipts/drop", nil)
// receiptTimeoutMeter = metrics.NewRegisteredMeter("eth/downloader/receipts/timeout", nil)

// stateInMeter   = metrics.NewRegisteredMeter("eth/downloader/states/in", nil)
// stateDropMeter = metrics.NewRegisteredMeter("eth/downloader/states/drop", nil)
```

>*metrics.go* `go-ethereum/eth/fetcher`

```go
// propAnnounceInMeter   = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/in", nil)
propAnnounceOutTimer  = metrics.NewRegisteredTimer("eth/fetcher/prop/announces/out", nil)
// propAnnounceDropMeter = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/drop", nil)
// propAnnounceDOSMeter  = metrics.NewRegisteredMeter("eth/fetcher/prop/announces/dos", nil)

// propBroadcastInMeter   = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/in", nil)
propBroadcastOutTimer  = metrics.NewRegisteredTimer("eth/fetcher/prop/broadcasts/out", nil)
// propBroadcastDropMeter = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/drop", nil)
// propBroadcastDOSMeter  = metrics.NewRegisteredMeter("eth/fetcher/prop/broadcasts/dos", nil)

// headerFetchMeter = metrics.NewRegisteredMeter("eth/fetcher/fetch/headers", nil)
// bodyFetchMeter   = metrics.NewRegisteredMeter("eth/fetcher/fetch/bodies", nil)

// headerFilterInMeter  = metrics.NewRegisteredMeter("eth/fetcher/filter/headers/in", nil)
// headerFilterOutMeter = metrics.NewRegisteredMeter("eth/fetcher/filter/headers/out", nil)
// bodyFilterInMeter    = metrics.NewRegisteredMeter("eth/fetcher/filter/bodies/in", nil)
// bodyFilterOutMeter   = metrics.NewRegisteredMeter("eth/fetcher/filter/bodies/out", nil)
```