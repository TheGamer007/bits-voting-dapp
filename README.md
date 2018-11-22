# BITS Voting DApp

A decentralized voting application built on the Ethereum blockchain. Features a Voter Dashboard for casting of votes, and an Admin Dashboard for management of candidates and posts / designations, and tallying of votes. Votes for the selected post are displayed both in tabular form, and as a Pie Chart (via [Chart.js](https://www.chartjs.org/)).

The contract supports multiple posts (i.e. designations), and multiple candidates can be added for each post. Each voter is permitted to cast one vote per post, and the vote fails if they attempt to re-cast a vote.

The contract **does not** ensure that newly added candidates or posts are distinct. Therefore, this must be handled as appropriate in the frontend as of now. However, this allows for the same candidate to contest for multiple positions.

### Dependencies:

- [NodeJS](https://nodejs.org/en/)
- [Truffle](https://github.com/trufflesuite/truffle)
- [Ganache](http://truffleframework.com/ganache/)

## Quick Setup

Once NodeJS and npm are installed, run the following to install Truffle:
```
npm install -g truffle
```

Then install Ganache by following the instructions in [the quickstart](https://truffleframework.com/docs/ganache/quickstart).

Finally, clone this repo and install the necessary node modules:
```
git clone https://github.com/TheGamer007/bits-voting-dapp.git
cd bits-voting-dapp
npm install
```

To get it running, open up a new terminal tab (navigate to the same directory):
```
truffle develop
> compile
> migrate
```
This creates a new local Ganache blockchain network, pre-loaded with 10 accounts, each with 100 ETH. Then it compiles and loads our contracts onto this network.

Next, go back to your previous tab and run:
```
npm run dev
```
This hosts our web application locally on port `8080`. So our Voter Dashboard can be accessed at `localhost:8080/`, while the Admin Dashboard is at `localhost:8080/admin.html`.

The application will not have any candidates or posts populated by default, so you will first have to add some via the Admin Dashboard before being able to vote.

## Potential Feature Additions

- Granular Voter Permissions: Currently voters can vote for all posts (though they aren't **required** to do so), but there may be cases where they are eligible to vote only for some posts out of the pool.

- Candidate / Post Uniqueness Check: Can be enforced in the contract, and the method call can emit an event, similar to the `vote` function.

## License

This app is under the [MIT License](./LICENSE.md).
