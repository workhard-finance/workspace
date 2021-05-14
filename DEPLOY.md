# Deployment

## Steps
1. Deploy Contracts to mainnet or testnet(rinkeby) [more details](#contract-deployment)
2. Commit the updated deployement result **deploy.json** and push it to the upstream repo.
3. Go to https://github.com/workhard-finance/protocol and create a release
4. Go to the frontend-v1 app, and update the dependency.
5. Commit the updated dependency and push it to the upstream repo..


## Contract Deployment

1. Setup Gnosis Safe Multisig address & deployer account in the workspace/.env

    ```
    # .env
    ALCHEMY_API_KEY=
    DEPLOYER_KEY=
    MULTISIG_WALLET=
    ```

2. Run deployment script

    Rinkeby:
    ```
    task rinkeby:deploy
    ```
    Mainnet:
    ```
    task mainnet:deploy
    ```
 