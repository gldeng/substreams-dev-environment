This repository contains developer environments for several Substreams use cases:

## Graph Node Local Development

If you are developing a Substreams-powered subgraph, you can use the local Docker set-up to test the indexing locally.


```graphql
{
  transfers(first: 1000) {
    id
    timestamp
    blockNumber
    contract
    symbol
    amount
    from
    to
    transaction
    callPath
    ordinal
  }
}
```

Demo Steps:

1. `task up`
2. `task xfer -- 10000`
3. `task ss -- 450` # Run substreams output
4. `task blk -- 450` # Run firehose output
5. `task db_sink`
6. `task subgraph`
