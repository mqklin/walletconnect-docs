# Javascript API Reference

## For Dapps (Browser SDK)

```js
/**
 * @desc returns if walletconnect session is connected
 * @returns {Boolean}
 */
const isConnected

/**
 * @desc returns walletconnect session uri
 * @returns {String}
 */
const uri

/**
 * @desc returns walletconnect active listeners
 * @returns {Array}
 */
const listeners

/**
 * @desc stops last activated listener
 * @returns {Boolean}
 */
function stopLastListener() {}


/**
 * @desc returns walletconnect session data
 * @returns {Object}
 */
function toJSON() {}

/**
 * @desc initiates new or existing session
 * @returns {Promise}
 */
async function initSession() {}


/**
 * @desc creates new session
 * @returns {Promise}
 */
async function createSession() {}


/**
 * @desc send transaction - call eth_sendTransaction
 * @param   {Object}  [tx]
 * @returns {Promise}
 */
async function sendTransaction() {}

/**
 * @desc sign message - call eth_sign
 * @param   {String}  [msg]
 * @returns {Promise}
 */
async function signMessage() {}

/**
 * @desc sign typed data - call eth_signTypedData
 * @param   {Object}  [msgParams]
 * @returns {Promise}
 */
async function signTypedData() {}

/**
 * @desc create JSON RPC call request
 * @param   {Object}  [msgParams]
 * @returns {Promise}
 */
async function createCallRequest() {}

/**
 * @desc get session status from bridge url
 * @returns {Promise}
 */
async function getSessionStatus() {}

/**
 * @desc get call status from bridge url
 * @returns {Promise}
 */
async function getCallStatus() {}

/**
 * @desc listen for session status (short-polling)
 * @param   {Number}    [interval]
 * @param	  {Number}    [timeout]
 * @returns {Promise}
 */
async function listenSessionStatus() {}

/**
 * @desc listen for call status (short-polling)
 * @param   {Number}    [interval]
 * @param	  {Number}    [timeout]
 * @returns {Promise}
 */
async function listenCallStatus() {}
```
