# Test UI

## Setup Metamask

1. Create a [chrome](https://support.google.com/chrome/answer/2364824?co=GENIE.Platform%3DDesktop&hl=en) or [firefox profile](https://support.mozilla.org/en-US/kb/profile-manager-create-remove-switch-firefox-profiles) for testing.

2. Install metamask and create accounts using the following seed phrase

   ```
   test test test test test test test test test test test junk
   ```

3. In the metamask, click network and setup local network
   - Network Name: Hardhat or (something other you want).
   - New RPC URL: http://127.0.0.1:8545
   - Chain ID: 31337

## Start dev server

Run this command on the workspace root directory.

```
task develop
```

## Start UI testing

_When you restart the dev server, don't forget to reset your metamask account in the advanced settings. Otherwise, you will encounter nonce related error during the test._

### 1. Stable Reserve

#### Buy Commitment

1. Go to Stable Reserve tab
2. Type 5000 DAI. Then, approve and buy 2500 $COMMIT.
3. Balance should be 5000 DAI / 2500 COMMIT

#### Redeem Commitment

1. Go to redeem tab.
2. Type 2000
3. Approve and redeem.
4. Balance should be 7000 DAI / 500 COMMIT

### 2. Job posting & governance

#### Post a job

1. Go to Job Board > Post a job tab.
2. Fill the form and submit.
3. Upload data to IPFS & Arweave and then send transaction w/ Metamask.
4. You can check the new posted job on the Inactive/Pending project tab.
5. Copy project id.

#### Approve the project

1. Go to Gov > Proposal tab
2. Select Timelock > JobBoard > approveProject
3. Paste the copied project id.
4. Submit the schedule request.
5. Go to Gov > Transactions tab and see timelock waiting.
6. Increase the block timestamp by
   ```
   cd protocol
   yarn localhost increase-time 86400
   ```
7. Reload transaction tab and execute the scheduled transaction. (In rinkeby, you should use multisig.)
8. Go back to work tab and check the posted project is active.

### 3. Add budget & compensate

#### Add tokens to the distribution tokens list

1. Go to Gov > Transactions tab
2. The 2nd scheduled tx is a transaction that appends the test ERC20 & COMMIT to the distribution token list.
3. Click execute. (In Rinkeby, you should use multisig.)

#### Add budget

1. Go back to Work > Job Board > Active Project
2. Click Go to admin tool. This button is only shown to the budget owner.
3. Go to budget
4. Increase amount to 3000
5. Approve and then click add & execute.

### Compensate

1. Go to pay tab of the project admin tool.
2. Paste metamask's 2nd account address (should be `0x70997970C51812dc3A010C7d01b50e0d17dc79C8`) and increase amount to 1000.
3. Click pay.
4. Switch account and go to Work menu to check the commit balance.

### 4. Mining test

#### Liquidity Mining

1. If you are on Rinkeby, go to rinkeby uniswap v2 page and add liquidity there.
2. If you are on the local testnet, run the following command to add liquidity.
   ```.shell
   cd protocol
   yarn localhost run scripts/demo/5-add-liquidity.ts
   ```

### 5. Voting Test

#### Create a lock for voting escrow

#### Delegate Vote

#### Distribute rewards and claim dividends

#### Workers Union Voting

### 6. Marketplace Test

#### Manufacture New Product

#### Purchase & Dividend