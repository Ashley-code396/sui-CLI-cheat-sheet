# sui CLI DEV CHEAT SHEET

To confirm that Sui has been installed successfully:

```bash

sui --version

```

If this command returns sui not found, then Sui is not installed and you must follow the installation instructions.

## sui Client

Run the Sui CLI with the command:

```bash

sui client

```

The first prompt confirms if you want to create the client.yaml file, select Y:

Config file ["<PATH-TO-FILE>/client.yaml"] doesn't exist, do you want to connect to a Sui full node server [y/N]?   

The second prompt configures the network server URL to connect to:

Sui full node server URL (Defaults to Sui Testnet if not specified) :





To create a new Sui address outside of the initial client configuration, run:

```bash

sui client new-address ed25519

```

To view the current active address, use the command:

```bash

sui client active-address

```

### Change the active address

If you want to switch to another address, first confirm which address is the active address and which addresses are available for you to switch to:

```bash

sui client addresses

```
Then, to switch to another address, use the command:

```bash

sui client switch --address <ADDRESS>

```

### Verify token balance

To check your balance of SUI tokens and confirm you received some from the faucet, use the command:


```bash

sui client balance 

```

You should have a balance of SUI tokens:

```bash

╭────────────────────────────────────────────╮
│ Balance of coins owned by this address     │
├────────────────────────────────────────────┤
│ ╭────────────────────────────────────────╮ │
│ │ coin       balance (raw)  balance      │ │
│ ├────────────────────────────────────────┤ │
│ │ Sui        56804696124     0.50 SUI    │ │
│ ╰────────────────────────────────────────╯ │
╰────────────────────────────────────────────╯

```

If you do not have a balance, request SUI tokens from  https://faucet.sui.io/,  or use an alternative faucet method.

### Network commands

To get the active environment:

```bash 

sui client active-env

```

To list defined environments:

```bash

sui client envs

```

To create a new environment with URL and alias:

```bash

sui client new-env --rpc URL --alias ALIAS

```

Example:

```bash

sui client new-env --alias=mainnet --rpc https://fullnode.mainnet.sui.io:443

```

To switch to the given environment:

```bash

sui client switch --env ENV_ALIAS

```

Example:

```bash

sui client switch --env mainnet

```

### Create, build, and test a Move project commands


To create a new Move project in the given folder:

```bash

sui move new <PROJECT_NAME>

```

To build the Move project in the current directory:

```bash

sui move build

```

To publish Move project:

```bash
sui client publish

```

To test the Move project in the current directory

```bash

sui move test

```













