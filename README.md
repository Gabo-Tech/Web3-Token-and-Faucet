<h1 align="center"><strong>DGABO TOKEN</strong></h1>


![Web Mockup](Mockup.png)
<br>

## Getting Started
Hi everyone! This is my personal cryptotoken it's real, though it's not deployed and publicly available due to expensive blockchain fees. You can claim your free tokens by just pressing a button.

### You want to own this website?

On the other hand if you'd like to host this website on your local machine just clone this repository with ```git clone https://github.com/Gabo-Tech/Web3-Token-and-Faucet.git```. just copy and paste that command on your terminal and keep scrolling to see how to set up the DFINITY enviorment.

## Deployment

Even though this is been develop to run in the cheapest blockchain (The Internet Computer), it's still quite expensive for me to deploy this into the real blockachian, but you can download it and run the emulator, keep scrolling to see the instructions.

## Built With

* [JavaScript](https://www.javascript.com/) - The web programming languaje
* [Motoko](https://internetcomputer.org/docs/current/developer-docs/build/languages/motoko/) - Let's code smart contracts!
* [HTML](https://html.com/) - Your favourite Markup Languaje
* [CSS](https://www.css3.info/) - Used to stylize this awesome website
* [React](https://reactjs.org/) - The "reactive" library

## Contributing

  Like, share, subscribe, follow and join my Patreon! Just kidding this is totally for free. 

## Authors

* **Gabriel Clemente, aka Gabo, your favourite web developer.** - *Initial work* - [Gabo](https://github.com/Gabo-Tech)

## License

This project is licensed under the Creative Commons Public Domain License - Feel free to copy the code, I did it too.


<br>
<p align="center">
  <img 
    width="400"
    height="130"
    src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Public_Domain_Mark_button.svg/220px-Public_Domain_Mark_button.svg.png"
    alt="Creative Commons Public Domain License"
  ></p>
  <p align="center">
  <img 
    width="800"
    height="1000"
    src="https://preview.redd.it/hwurhp7crzf81.png?auto=webp&s=3f230e79f360c9fbc9394e70ea72330391bf8f27"
    alt="This meme represents you"
  ></p>
<br>


## Acknowledgments

* Thanks to Angela Yu, it's been the best teacher I ever had, I learn most of the things I know with her.

## Intruction to create the enviorment to run this DAPP

[In this link](https://internetcomputer.org/docs/current/developer-docs/quickstart/hello10mins)

# Check your Balance

1. Find out your principal id:

```
dfx identity get-principal
```

2. Save it somewhere.

e.g. My principal id is: gwtbp-s23g7-ymbe4-6qdr7-ft2wt-gmv57-ixsas-evm7o-q2jae-uxyht-fae


3. Format and store it in a command line variable:
```
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:
```
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:
```
dfx canister call token balanceOf "( $OWNER_PUBLIC_KEY )"
```

# Charge the Canister


1. Check canister ID:
```
dfx canister id token
```

2. Save canister ID into a command line variable:
```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

3. Check canister ID has been successfully saved:
```
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:
```
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 1_000_000_000_000_000)"
```

# Deploy the Project to the Live IC Network

1. Create and deploy canisters:

```
dfx deploy --network ic
```

2. Check the live canister ID:
```
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:
```
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:
```
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:
```
dfx canister --network ic call token transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get live canister front-end id:
```
dfx canister --network ic id token_assets
```
7. Copy the id from step 6 and add .raw.ic0.app to the end to form a URL.
e.g. zdv65-7qaaa-aaaai-qibdq-cai.raw.ic0.app