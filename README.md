# Bramble
Programmable Crypto Rewards API for Apps & Games

## Vision

To make cryptocurrency accessible and usable to every person on the planet.

## Objectives and Goals

To increase engagement & revenue of an app or game by rewarding users in Bramble

### User Interaction Design

The current implementation of Blockchain is not meant for regular/novice users. Added steps to ensure privacy, decentralization while maintaining the usability aspect of the app has further made things complex.

Focusing more on user interface i.e. making it easy for non-tech users to access cryptocurrency, abstracting the core-tech of blockchain to get a product-market fit. This ensures that users can use the app without the knowledge of private keys, public keys, gas charges etc.


### Bramble Reward Mechanism

A player scores a reward, in background he redeems the brambles. If in game server he gets a daily quest completion / achievement completion, it will report this information to his bramble wallet via the game server. So he will not need to redeem every bramble, he will get that automatically once he links the bramble wallet to in-game account. So the game would just make push notifications to the wallet and not request any info. If he wants to see the wallet, he would need to login manually or from in-game link to bramble wallet. After a quest completion the game will send something as simple as 
````
{ user: 'user_id', reward: 'crossing_100_pipes'} 
````
and then the Bramble API will manage the data. If there are too easy and frequent gained rewards then the algorithm would decrease the reward. If the reward would be gained very rare, the algorithm would increase its value. The wallet will be linked to the game via Oauth 2.0 authorization. User would click on the in-game link to Bramble Wallet. The algorithm works on numerous parameters to mint tokens which users will be rewarded in, eventually.

````
for example: bramblewallet.com/link_account/flappybird?user=user_id&token=some_random_token
````
Bramble OAuth API will generate some wallet_token and send to game developer's backend to
````
flappybird.com/bramble_link?user=user_id&token=some_random_token&wallet_token=your_wallet_token
````
So the next time when user gets reward, the game will just send the wallet_token nd the reward info and if user wants to see Bramble wallet info, he will be redirected to Bramble page bramblewallet.com/login?user=user_id
So this would be an easy integration from the developer's side. The game developer don't need any info of your wallet, just will export data to the server on every achievement user gets and the game will have just a link to Bramble wallet. If user has linked, there will be a login link to the website. If user not yet linked the account, on the first time the account will be linked, transfered all yet gained old rewards. This flow can work for In-App purchases too where the game's native currency is replaced by Bramble. This process flow will be automated.


### Also look at

[Bramble Developer API Documentation](https://github.com/rahul-soshte/bramble-api-flow)

### Contact Email

hunterlabsc@gmail.com