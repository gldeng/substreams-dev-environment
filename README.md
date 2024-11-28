This repository contains developer environments for several Substreams use cases:

## Graph Node Local Development

If you are developing a Substreams-powered subgraph, you can use the local Docker set-up to test the indexing locally.


```graphql
{
  transfers(first: 10, orderBy: blockNumber, orderDirection: desc) {
    from
    to
    contract
    symbol
    amount
    memo
    id
    blockNumber
    ordinal
    transaction
    callPath
    timestamp
  }
}
```

```graphql
{
  transfers(where: {from: "W1ptWN5n5mfdVvh3khTRm9KMJCAUdge9txNyVtyvZaYRYcqc1"}) {
    to
    symbol
    amount
    memo
    blockNumber
    timestamp
  }
}
```

```graphql
{
  balances(
    first: 10
    where: {owner: "5i8gir5PhkkGr6a7RWdxzPf5ns3Sd9cp9jQF7maVQUwi6kc4U"}
  ) {
    balance
    owner
    symbol
    contract
    timestamp
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
