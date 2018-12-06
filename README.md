![NEM Meteor Wallet Promo Image](https://s3.amazonaws.com/devslopes-qa-forum/readme-nem-meteor-promo.png)
# NEM Meteor Wallet

[Download For iOS](https://itunes.apple.com/us/app/nem-meteor-wallet/id1418697062?mt=8&ign-mpt=uo%3D4)

The NEM Meteor Wallet is a powerful wallet for managing XEM and NEM-based tokens known as Mosaics.

After spending many weeks prototyping this wallet using React Native and Ionic we could not achieve the desire performance needed for a high-quality application. We went back to the drawing board to figure out a way to interface with the NEM blockchain using native Swift for iOS and native Kotlin for Android.  

We accomplished what we set out to achieve and NEM Meteor Wallet was born.

## App Features

*  Send and receive XEM
*  Send and receive any Mosaic
*  Import wallets from Nano Wallet
*  Export wallets
*  Send money requests to other people
*  Switch between NEM Main Net and NEM Test Net
*  Fun animations and slick UX
*  Displays current XEM price and includes currency conversions
*  Built in support for localization
*  Push notifications for incoming & confirmed transactions
*  Supports multiple wallets

Note: Multi Signature is coming soon and NOT yet included in the code

![NEM Meteor Phone Images](https://s3.amazonaws.com/devslopes-qa-forum/meteor-readme-phones-3.png)

## App Architecture

NEM Meteor Wallet uses [NEM Library](https://github.com/aleixmorgadas/nem-library-ts) to communicate with the NEM blockchain.

The reason we built this application is so we could enjoy the high-performance of native mobile applications while also using the well-tested Javascript based NEM Library and associated Crypto tooling.


![NEM Meteor architecture](https://s3.amazonaws.com/devslopes-qa-forum/meteor-readme-architecture.png)

1. The app user interface is all built using native Swift or Kotlin
2. The app has a built in C++ Node runtime that acts as an interal intermediary server
3. We have a REST API that sits on top of the runtime and utilizes NEM Library to communicate with NEM blockchain
4. Mobile apps in their native language make HTTP requests and web sockets to communicate with intermediary API
5. The API and NEM Library is compiled into a single file using Webpack and that file is added to mobile project

![NEM meteor bundlejs](https://s3.amazonaws.com/devslopes-qa-forum/meteor-readme-bundle-js.png)

6. Xcode will automatically build API and load `bundle.js` each time you build the project

![NEM meteor build](https://s3.amazonaws.com/devslopes-qa-forum/meteor-readme-build.png)

The best part is the API code and C++ Node runtime is 100% re-useable between iOS and Android. This means that the only work to do is build user interface on each platform!

# Developer Instructions

If you are building this app for NIS1:

1.  Clone this repo
2.  Run `git submodule update --init`
5.  Run `cd nem-meteor-wallet-api && npm install`


When you run the app it will build the node project and copy it into Xcode.


If you add a framework follow steps:
Run `carthage update --platform iOS --no-use-binaries`
Run `open carthage`
Drag framework into frameworks folder from finder.
Delete Carthage directory
Add framework as embedded framework in general settings

# LICENSE

Copyright 2018 Blockstart, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

All images, logos, or brandings depicting Blockstart cannot be distributed as they are copyrighted material owned by Blockstart LLC
