# npx oz tutorial

## prepare

### for localhost

> just to start a local ganache-cli

```sh
➜ yarn chain
yarn run v1.22.15
$ npx ganache-cli --deterministic
Ganache CLI v6.12.2 (ganache-core: 2.13.2)

Available Accounts
==================
(0) 0x90F8bf6A479f320ead074411a4B0e7944Ea8c9C1 (100 ETH)
(1) 0xFFcf8FDEE72ac11b5c542428B35EEF5769C409f0 (100 ETH)
(2) 0x22d491Bde2303f2f43325b2108D26f1eAbA1e32b (100 ETH)
(3) 0xE11BA2b4D45Eaed5996Cd0823791E0C93114882d (100 ETH)
(4) 0xd03ea8624C8C5987235048901fB614fDcA89b117 (100 ETH)
(5) 0x95cED938F7991cd0dFcb48F0a06a40FA1aF46EBC (100 ETH)
(6) 0x3E5e9111Ae8eB78Fe1CC3bb8915d5D461F3Ef9A9 (100 ETH)
(7) 0x28a8746e75304c0780E011BEd21C72cD78cd535E (100 ETH)
(8) 0xACa94ef8bD5ffEE41947b4585a84BdA5a3d3DA6E (100 ETH)
(9) 0x1dF62f291b2E969fB0849d99D9Ce41e2F137006e (100 ETH)

Private Keys
==================
(0) 0x4f3edf983ac636a65a842ce7c78d9aa706d3b113bce9c46f30d7d21715b23b1d
(1) 0x6cbed15c793ce57650b9877cf6fa156fbef513c4e6134f022a85b1ffdd59b2a1
(2) 0x6370fd033278c143179d81c5526140625662b8daa446c22ee2d73db3707e620c
(3) 0x646f1ce2fdad0e6deeeb5c7e8e5543bdde65e86029e2fd9fc169899c440a7913
(4) 0xadd53f9a7e588d003326d1cbf9e4a43c061aadd9bc938c843a79e7b4fd2ad743
(5) 0x395df67f0c2d2d9fe1ad08d1bc8b6627011959b79c53d7dd6a3536a33ab8a4fd
(6) 0xe485d098507f54e7733a205420dfddbe58db035fa577fc294ebd14db90767a52
(7) 0xa453611d9419d0e56f499079478fd72c37b251a94bfde4d19872c44cf65386e3
(8) 0x829e924fdf021ba3dbbc4225edfece9aca04b929d6e75613329ca6f1d31c0bb4
(9) 0xb0057716d5917badaf911b193b12b910811c1497b5bada8d7711f758981c3773

HD Wallet
==================
Mnemonic:      myth like bonus scare over problem client lizard pioneer submit female collect
Base HD Path:  m/44'/60'/0'/0/{account_index}

Gas Price
==================
20000000000

Gas Limit
==================
6721975

Call Gas Limit
==================
9007199254740991

Listening on 127.0.0.1:8545
```

### for ropsten public testnet as example

> create your own .env with a new mnemonics and get your infura project ID from https://infura.io/.

```sh
cp .env.example .env
cat .env
INFURA_PROJECT_ID=<YOUR INFURA PROJECT ID>
DEV_MNEMONIC=<YOUR MNEMONICS GETTING FROM "npx mnemonics">
```

> for example, to get your new mnemonics as follow;

```sh
➜ npx mnemonics
ensure citizen enable claw guard marine develop glad hurt knife flame ahead
```

## demo

### accounts

```sh
➜ yarn accounts
yarn run v1.22.15
$ npx oz accounts
? Pick a network ropsten
Accounts for ropsten:
Default: 0x8A98520c8B7e703E573A420c987AeA3eA47f1915
All:
- 0: 0x8A98520c8B7e703E573A420c987AeA3eA47f1915
✨  Done in 5.64s.
```

> or for localhost network

```sh
➜ yarn accounts
yarn run v1.22.15
$ npx oz accounts
? Pick a network development
Accounts for dev-1653735299608:
Default: 0x90F8bf6A479f320ead074411a4B0e7944Ea8c9C1
All:
- 0: 0x90F8bf6A479f320ead074411a4B0e7944Ea8c9C1
- 1: 0xFFcf8FDEE72ac11b5c542428B35EEF5769C409f0
- 2: 0x22d491Bde2303f2f43325b2108D26f1eAbA1e32b
- 3: 0xE11BA2b4D45Eaed5996Cd0823791E0C93114882d
- 4: 0xd03ea8624C8C5987235048901fB614fDcA89b117
- 5: 0x95cED938F7991cd0dFcb48F0a06a40FA1aF46EBC
- 6: 0x3E5e9111Ae8eB78Fe1CC3bb8915d5D461F3Ef9A9
- 7: 0x28a8746e75304c0780E011BEd21C72cD78cd535E
- 8: 0xACa94ef8bD5ffEE41947b4585a84BdA5a3d3DA6E
- 9: 0x1dF62f291b2E969fB0849d99D9Ce41e2F137006e
✨  Done in 4.51s.
```

### generate a new ERC20 token

```sh
➜ yarn deploy
yarn run v1.22.15
$ npx oz deploy
No contracts found to compile.
? Choose the kind of deployment (Use arrow keys)
? Choose the kind of deployment
? Choose the kind of deployment upgradeable
? Pick a network development
? Pick a contract to deploy @openzeppelin/contracts-ethereum-package/ER
C20PresetMinterPauserUpgradeSafe
✓ Deploying @openzeppelin/contracts-ethereum-package dependency to network dev-1653735299608
All implementations are up to date
? Call a function to initialize the instance after creating it? Yes
? Select which function initialize(name: string, symbol: string)
? name: string: "MING token"
? symbol: string: "MX1"
✓ Setting everything up to create contract instances
✓ Instance created at 0x59d3631c86BbE35EF041872d502F218A39FBa150
To upgrade this instance run 'oz upgrade'
0x59d3631c86BbE35EF041872d502F218A39FBa150
✨  Done in 46.88s.
```