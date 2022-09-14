---
#### <img src="https://raw.githubusercontent.com/SpaceWormETH/.github/main/profile/SpaceWormJim-icon.png" width="12" height="12" /> [SpaceWorm](https://github.com/SpaceWormETH) | [```API```](https://github.com/SpaceWormETH/SpaceWorm-API) | [Contract](https://github.com/SpaceWormETH/SpaceWorm-contract)
---

# SpaceWorm API

A Node.js based API for $WORM / SpaceWorm.

## Features

- [x] Circulating supply (total supply - total burned tokens)
- [x] Total burned
- [x] Total burned percent
- [x] Price (_USDperWORM_, _WORMperUSD_, _ETHperWORM_, _WORMperETH_, _USDperETH_)
- [x] Volume (_USD_ or _ETH_) - currently to hour/block
  - [ ] Live-To-Tx Volume
- [ ] Market Cap (_USD_ or _ETH_)
- [ ] Dashboard Data Output (_~started/WIP_)

## Usage

### Circulating Supply

```
GET https://api.spaceworm.army/v1/circulating-supply
```

```json
{ "circulatingSupply": "000000000000.000" }
```

### Total Burned

```
GET https://api.spaceworm.army/v1/total-burned
```

```json
{ "totalBurned": "000000000000.0000" }
```

### Total Burned as Percent of Starting Supply

```
GET https://api.spaceworm.army/v1/total-burned-percent
```

```json
{ "totalBurnedPercent": "00.00" }
```

### Price

_Get all options._

```
GET https://api.spaceworm.army/v1/price
```

```json
{
  "USDperWORM": "000.00000000000000000",
  "WORMperUSD": "0000.000000000000000",
  "ETHperWORM": "0.00000000000000000000000000000000000",
  "WORMperETH": "00000.00000000000000000000000000",
  "USDperETH": "0000.000000000000000000000000"
}
```

_Get only the requested price._

```
GET https://api.spaceworm.army/v1/price?n=USDperWORM|WORMperUSD|ETHperWORM|WORMperETH|USDperETH
```

```json
0.00000000000000001
```

<!-- ```json
{ "currency": "USDperWORM", "price": "0.000000000000000000" }
```

```json
{ "currency": "WORMperUSD", "price": "0.000000000000000000" }
```

```json
{ "currency": "ETHperWORM", "price": "0.000000000000000000" }
```

```json
{ "currency": "WORMperETH", "price": "0.000000000000000000" }
```

```json
{ "currency": "USDperETH", "price": "0.000000000000000000" }
``` -->

### Volume

Currently pulls from hourly blocks (to be dynamic to each block / timestamp in future).

_Get both options_

```
GET https://api.spaceworm.army/v1/24hVolume
```

```json
{ "volumeETH": "0000.000000000000000000", "volumeUSD": "000000.0000000000" }
```

_Get only the requested currency._

```
GET https://api.spaceworm.army/v1/24hVolume?currency=eth|usd
```

```json
{ "ethVolume": "0000.000000000000000000" }
```

```json
{ "usdVolume": "000000.0000000000" }
```

### Token Details

```
GET https://api.spaceworm.army/v1/token-details
```

```json
{
  "contract": "0xf7ecb2e5ddad17506e62f51a442f725a26053fb2",
  "uniswapPairAddress": "0x2c5eae2ac336e27a7c8737cf5fc3263c4f09a2f0",
  "symbol": "$WORM",
  "name": "SpaceWorm",
  "decimals": "18",
  "totalSupply": "1100000"
}
```

```
GET https://api.spaceworm.army/v1/total-supply
```

```json
{ "totalSupply": "1100000" }
```

### Dashboard (WIP)

Early iteration of part of the API that provides internal data to the dashboard.

_Note: this is a Work In Progress (WIP)_

```
GET https://api.spaceworm.army/v1/dashboard
```

```json
{
  "pair":{ "token1":{ "derivedETH":"0.000000000000000000"}, "reserve0":"00.000000000000000000", "reserve1":"0000000.000000000000000000", "reserveUSD":"00000.000000000000000000", "trackedReserveETH":"000.000000000000000000", "token0Price":"0.0000000000000000000000", "token1Price":"00000.000000000000000000", "untrackedVolumeUSD":"00000000.000000000000000000", "volumeToken0":"0000.000000000000000000", "volumeToken1":"00000000.000000000000000000", "txCount":"00000" },
    "pairDayDatas":[{ "date":000000000000, "dailyVolumeToken0":"000.000000000000000000", "dailyVolumeToken1":"00000000.000000000000000000", "dailyTxns":"0000", }],
      "_meta":{ "block":{ "hash":"000000000000000000", "timestamp":"000000000000000000" }},
  "volumeETH":"17.000000000000000000", "volumeUSD":"28572.000000000000000000", "totalBurned":"0000000.000000000000000000", "totalBurnedPercent":"00", "circulatingSupply":"000000.00000", "USDperWORM":"0.00000", "WORMperUSD":"00.0000000", "ETHperWORM":"0.00000000000000000000", "WORMperETH":"00000.000000000000000000", "USDperETH":"00000.000000000000000000" }
 }
```

---

© 2022 [SpaceWorm.army](https://SpaceWorm.army)
