# Ballot

Currently, deployed on ropsten testnet [here](https://ropsten.etherscan.io/address/0x38e642426b9de8e7dbd5c1939956f099a23e767f)

# deployed
- `npx ts-node scripts/deployment.ts Pizza Cake Hamburguer `
- 3 proposals in proposal array
  - [0] = Pizza - as 32 bytes: 0x50697a7a61000000000000000000000000000000000000000000000000000000
  - [1] = Cake - 0x43616b6500000000000000000000000000000000000000000000000000000000
  - [2] = Hamburguer - 0x48616d6275726775657200000000000000000000000000000000000000000000


# give right to vote

- `npx ts-node scripts/giveVotingRights.ts 0x38e642426b9de8e7dbd5c1939956f099a23e767f 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5`
- the address of the deployer of this contract is the chairperson: 0xb99404011f03c4913d8d5d6d6a567960a87aa352 
- contract address is: 0x38e642426b9de8e7dbd5c1939956f099a23e767f
- voter address is: 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5

### output

Using address 0xB99404011F03c4913d8d5D6D6A567960a87AA352

Wallet balance 19.98321489042167

Attaching ballot contract interface to address 0x38e642426b9de8e7dbd5c1939956f099a23e767f

Giving right to vote to 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5

Awaiting confirmations

Transaction completed. 

Hash: 0x53c6eca59101a92d6c9eeeee2581313093adb06d67ab70f9808a4ef7e96d16b7

# query proposals

`npx ts-node scripts/query.ts 0x38e642426B9De8e7dBd5C1939956F099a23E767f`

### output

Using address 0xB99404011F03c4913d8d5D6D6A567960a87AA352

Wallet balance 19.98314190492133

Querying proposal

Pizza

Cake

Hamburguer

