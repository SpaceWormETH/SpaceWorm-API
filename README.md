---
#### <img src="https://raw.githubusercontent.com/SpaceWormETH/.github/main/profile/SpaceWormJim-icon.png" width="12" height="12" /> [SpaceWorm](https://github.com/SpaceWormETH) | [```API```](https://github.com/SpaceWormETH/SpaceWorm-API) | [Contract](https://github.com/SpaceWormETH/SpaceWorm-contract)
---

# SpaceWorm API

A Node.js based API for $WORM / SpaceWorm.

## Features

- [x] Circulating supply (total supply - total burned tokens)
- [x] Total burned
- [x] Total burned percent
- [x] Price (USD or ETH)
- [x] Volume (USD or ETH) - currently to hour/block
  - [ ] Live-To-Tx Volume
- [ ] Market Cap (USD or ETH)
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
  "WORMperETH": "00000.25380714577138850130420076793",
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

### Dashboard (WIP)

Early iteration of part of the API that provides initial data to the dashboard.

_Note this is a Work In Progress (WIP)_

```
GET https://api.spaceworm.army/v1/dashboard
```

```
{"pair":{"token0":{"id":"0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2","symbol":"WETH","name":"Wrapped Ether","derivedETH":"1"},"token1":{"id":"0xf7ecb2e5ddad17506e62f51a442f725a26053fb2","symbol":"$WORM","name":"SpaceWorm","derivedETH":"0.00000000000"},"reserve0":"000.00000000000","reserve1":"000000.00000000000","reserveUSD":"000000.00000000000","trackedReserveETH":"0000.00000000000","token0Price":"0.00000000000","token1Price":"00000.00000000000","untrackedVolumeUSD":"00000000000.00000000000","volumeToken0":"00000000000.00000000000","volumeToken1":"00000000000.00000000000","txCount":"0000000"},"tokenDayDatas":[{"dailyTxns":"000","dailyVolumeETH":"0000.00000000000","dailyVolumeUSD":"00000.00000000000","dailyVolumeToken":"00000.00000000000","priceUSD":"0.00000000000","totalLiquidityETH":"0000.00000000000","totalLiquidityUSD":"0000.00000000000","totalLiquidityToken":"00000000000.00000000000"}],"pairDayDatas":[{"id":"0x2c5eae2ac336e27a7c8737cf5fc3263c4f09a2f0-xxxxx","date":0000000000,"dailyVolumeToken0":"0000.00000000000","dailyVolumeToken1":"00000.00000000000","reserveUSD":"00000.00000000000","reserve0":"0000.00000000000","reserve1":"00000.00000000000","dailyVolumeUSD":"0","dailyTxns":"0000","pairAddress":"0x2c5eae2ac336e27a7c8737cf5fc3263c4f09a2f0"}],"_meta":{"block":{"hash":"0x0000000","timestamp":"0x0000000"}},"volumeETH":"0000.00000000000","volumeUSD":"00000000000.00000000000","totalBurned":"00000.0000000000000000000000","totalBurnedPercent":"0000.00000000000","circulatingSupply":"0000000.00000000000"}
```

---

© 2022 [SpaceWorm.army](https://SpaceWorm.army)
