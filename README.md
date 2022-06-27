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

Hamburguer`

# voting

#### code and output

`npx ts-node scripts/vote.ts 0x38e642426b9de8e7dbd5c1939956f099a23e767f 1`

<img src="https://github.com/jieunyoo/ballot/blob/main/screenshots/voteEtherscan.png" width="500">


# query votes

#### code
![code](https://github.com/jieunyoo/ballot/blob/main/screenshots/queryVotes.png)


# additional votes given

- contract address: 0x38e642426b9de8e7dbd5c1939956f099a23e767f
- chairperson address: 0xb99404011f03c4913d8d5d6d6a567960a87aa352

Summary so far ...
- chairperson gave right to vote to: 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5
- also did another transaction where chairperson gave right to vote to: 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42
- and another right to vote to: 0x332CB795369d64E1af9Bad9785e10477360c3443 and to 0x8a13f3c95168bD99935514F14679dC746B45c37B
- then, via etherscan, 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42 delegated vote to: 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5
- (the chairperson) 0xb99404011f03c4913d8d5d6d6a567960a87aa352 voted for: proposal 1

## successful delegation - part 1

- 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5's vote weight changed to 2.

<img src="https://github.com/jieunyoo/ballot/blob/main/screenshots/delegatedVote.png" width="500">

## successful delegation - part 2

- 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42's info. now shows that it voted and delegated its vote

<img src="https://github.com/jieunyoo/ballot/blob/main/screenshots/gotVoteDelegatedTo.png" width="500">

# delegate via script

- 0x8a13f3c95168bD99935514F14679dC746B45c37B delegated a vote to 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42

`npx ts-node scripts/delegateVote.ts 0x38e642426b9de8e7dbd5c1939956f099a23e767f 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42`

<img src="https://github.com/jieunyoo/ballot/blob/main/screenshots/delegateViaScript.png" width="1500">

# more votes

-  voted for proposal 2

`npx ts-node scripts/queryVoting.ts 0x38e642426B9De8e7dBd5C1939956F099a23E767f`

<img src="https://github.com/jieunyoo/ballot/blob/main/screenshots/queryVoteAgain.png" width="1500">

- the outcome makes senses
- the chairperson voted for proposal 1
- 0x82867D7Ecf15Bb63D626904802D831b9bDbFD0b5 voted for proposal 2
- two addresses delegated their vote to: 0x82867d7ecf15bb63d626904802d831b9bdbfd0b5
  - 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42 gave vote to 0x82867d7ecf15bb63d626904802d831b9bdbfd0b5
  - 0x8a13f3c95168bD99935514F14679dC746B45c37B delegated a vote to 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42, but 0x9f9E1b02f25FE6308c7B57e84D49d4386BB0Da42 had already delegated its vote to 0x82867d7ecf15bb63d626904802d831b9bdbfd0b5, so that means that 0x82867d7ecf15bb63d626904802d831b9bdbfd0b5 got two votes delegated to it
  - 0x82867d7ecf15bb63d626904802d831b9bdbfd0b5 had its vote, plus the two votes delegated to it, so in total, had 3 votes, and proposal 2 got 3 votes.
