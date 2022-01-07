Wethio Network Intelligence API
============

This is the backend service which runs along with Wethio and tracks the network status, fetches information through JSON-RPC and connects through WebSockets to [wethio-netstats](https://stats.wethio.io) to feed information.


## Prerequisite
* zyn - Wethio blockchain node
* node - Make sure to use node version 10
* npm


## Installation 

* Install node modules - npm install
* Install pm2 - npm install pm2 -g

## Configuration

Configure the app modifying app.json file in the main directory.

```json
"env":
	{
		"NODE_ENV"        : "production", // tell the client we're in production environment
		"RPC_HOST"        : "localhost", // wethio JSON-RPC host
		"RPC_PORT"        : "8545", // wethio JSON-RPC port
		"LISTENING_PORT"  : "30303", // wethio listening port (only used for display)
		"INSTANCE_NAME"   : "", // whatever you wish to name your node
		"CONTACT_DETAILS" : "", // add your contact details here if you wish (email/skype)
		"WS_SERVER"       : "https://stats.wethio.io", // path to wethio-netstats WebSockets api server
		"WS_SECRET"       : "", // WebSockets api server secret used for login
		"VERBOSITY"       : 2 // Set the verbosity (0 = silent, 1 = error, warn, 2 = error, warn, info, success, 3 = all logs)
	}
```

## Run

Run it using pm2:

```bash
pm2 start app.json
```
