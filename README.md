
# Metaplex Candy Machine Reference UI  
## :dart: $\textcolor{gray}{In\ this\ project\ you\ have\ to\ know:}$ 

<div>
     <img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/typescript/typescript-original.svg" title="typescript" **alt="typescript" width="40" height="40"/> 
  <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="html" **alt="html" width="40" height="40"/>
  <img src="https://user-images.githubusercontent.com/109158340/207687793-d2fe408f-6bfc-4ce6-bfd0-ca7e8bcc17e7.png" title="solana" **alt="solana" width="40" height="40"/>
 </div>

##  🛠  $\textcolor{gray}{Install\ the\ CLIs}$
Before we can get into this, we'll need to install:

* The Solana CLI - the Sugar CLI needs this. You can install it [here](https://docs.solana.com/cli/install-solana-cli-tools) for your OS.
* The Sugar CLI - you can install it [here](https://docs.metaplex.com/developer-tools/sugar/overview/installation).

 ##  🍬 $\textcolor{gray}{Set\ up\ your\ collection }$ 
 * Make a new project folder in your Solana workspace and create an assets folder inside it. I have made a SMURFS collection.:heart_eyes:
```json
{
  "name": "The Smurfs",
  "symbol": "SMURF",
  "description": "The Smurfs (French: Les Schtroumpfs; Dutch: De Smurfen) is a Belgian comic franchise centered on a fictional colony of small, blue, humanoid creatures who live in mushroom-shaped houses in the forest.",
  "image": "collection.jpg",
  "attributes": [],
  "properties": {
    "files": [
      {
        "uri": "collection.jpg",
        "type": "image/jpg"
      }
    ]
  }
}

```
*  You need to pair each NFT asset with a metadata JSON file, numbering each pair from zero.
```json
{
  "name": "Smurfette Smurf",
  "symbol": "SMURF",
  "description": "Smurfette has stereotypical feminine features, with long blonde wavy hair, long eyelashes, and wears a white dress and white high heels. She is the love interest of almost every Smurf.",
  "image": "0.jpg",
  "attributes": [
    {
      "trait_type": "Skin",
      "value": "blue"
    },
    {
      "trait_type": "Hat",
      "value": "white"
    },
    {
      "trait_type": "Dress",
      "value": "white"
    },
    {
      "trait_type": "Shoes",
      "value": "white"
    },
    {
      "trait_type": "Hair",
      "value": "blonde"
    }
  ],
  "properties": {
    "files": [
      {
        "uri": "0.jpg",
        "type": "image/jpg"
      }
    ]
  }
}

```
* It's time to set up your local Solana wallet on the devnet. 
Run these command and note the <i>pubkey</i>
```ruby
solana-keygen new --outfile ./wallet.json
```
and then run these:
```ruby
solana config set --keypair ./wallet.json
solana config set --url https://metaplex.devnet.rpcpool.com/
```
 ##  🍭 $\textcolor{gray}{Configure\ your\ Candy\ Machine }$ 
 *Candy machine does everything for you. You can deploy your collections [step by step](https://docs.metaplex.com/developer-tools/sugar/tutorials/my-first-candy-machine#set-up-your-project) to create .config file or you can use <i>sugar launch</i>.
 
* Run <i>sugar launch</i> in the terminal and set your nfts metadata.
```ruby
Starting Sugar launch...

✔ What is the price of each NFT? · 0.4
? Found 10 file pairs in "assets". Is this how many NFTs you will have in your candy m✔ Found 10 file pairs in "assets". Is this how many NFTs you will have in your candy machine? · yes
✔ Found symbol "SMURF" in your metadata file. Is this value correct? · yes
✔ What is the seller fee basis points? · 100
? What is your go live date? Many common formats are supported. If unsure, try YYYY-MM-DD HH:MM:SS [+/-]UTC-OFFSET or type 'now' for current time. For example 2022-05-02 18✔ What is your go live date? Many common formats are supported. If unsure, try YYYY-MM-DD HH:MM:SS [+/-]UTC-OFFSET or type 'now' for current time. For example 2022-05-02 18:00:00 +0000 for May 2, 2022 18:00:00 UTC. · now
✔ How many creator wallets do you have? (max limit of 4) · 1
✔ Enter creator wallet address #1 · "write your pubkey"           
? Enter royalty percentage share for creator #1 (e.g., 70). Total shares must add to 1✔ Enter royalty percentage share for creator #1 (e.g., 70). Total shares must add to 100. · 100
? Which extra features do you want to use? (use [SPACEBAR] to select options you want 
✔ Which extra features do you want to use? (use [SPACEBAR] to select options you want 
and hit [ENTER] when done) ·
✔ What is your SOL treasury address? · "write your pubkey"    
✔ What upload method do you want to use? · Bundlr
? Do you want to retain update authority on your NFTs? We HIGHLY recommend you choose 
✔ Do you want to retain update authority on your NFTs? We HIGHLY recommend you choose 
yes. · yes
✔ Do you want your NFTs to remain mutable? We HIGHLY recommend you choose yes. · yes
```
* Run in the terminal this commant and mint your nfts
```ruby
sugar mint
```
 ### 🎉: $\textcolor{gray}{And\ Here\ is\ your\ collection}$ 

![image](https://user-images.githubusercontent.com/109158340/207702055-53bf0987-9f51-4ff2-8cf6-8d9a8fd3c7ec.png)


 ### :sparkles: $\textcolor{gray}{Open\ your\ wallet\ and\ see\ your\ collection}$ 

![image](https://user-images.githubusercontent.com/109158340/207700751-c1083134-db6f-4246-8267-e303df848ee8.png)

