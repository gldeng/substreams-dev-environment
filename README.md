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
2. `task run_db_sink`
3. `task deploy_subgraph`
