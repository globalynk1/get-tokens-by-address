## Overview
This repository contains a JavaScript script that utilizes Alchemy's SDK to fetch a list of all the ERC-20 tokens owned by an address on Ethereum or Polygon with a single API request. The balances of the tokens are calculated using Alchemy's [getTokenBalances](https://alchemyenterprisegroup.readme.io/alchemy-docs/reference/alchemy-gettokenbalances) endpoint. For each token, the fields below are printed, however, to see all fields of metadata refer to the [getTokenMetadata](https://alchemyenterprisegroup.readme.io/alchemy-docs/reference/alchemy-gettokenmetadata) endpoint:

- Name
- Balance
- Symbol


## Steps to Run

Before running the script, ensure that you have [Node.js](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm), [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm), and [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable) installed on your system. 

Follow these steps to run the script:

1. Clone this repository to your local machine:
`git clone https://github.com/alchemyplatform/get-tokens-by-address.git`


2. Navigate to the project folder: `cd get-tokens-by-address`


3. Install the Alchemy SDK and the `dotenv` package running either of the following commands:
    - `yarn add alchemy-sdk dotenv`
    - `npm i alchemy-sdk dotenv`
  
4. Open the `sample.env` file and update the value for the API Key to your own value and rename file to `.env`. If you don't have an Alchemy API Key yet you can [create one for free here](https://alchemy.com/?a=starter-code). Simply make an account and find the "Access Keys" section in the dashboard to generate your own key! 

5. Open `getTokens.js` and update the value of the Wallet Address found within the main function on line 13 and to reflect the wallet that you will be querying. 


6. Run the script in the terminal: `node getTokens.js`


By following these steps, the script will execute and fetch the ERC-20 tokens owned by the specified address, printing out the desired fields to the console.


## Frequently Used Options and Best Practices
When working with the Alchemy SDK, there are several options and best practices that you can consider:

### Pagination
By default, the request for tokens has a page size of 100. If you have a large number of tokens and want to retrieve all of them, you can implement pagination. Alchemy's API supports pagination using the `page` and `size` parameters. You can adjust the `size` parameter to specify the number of tokens to retrieve per page and use the `page` parameter to iterate through the pages of results.

### Filtering and Excluding Tokens
The Alchemy API allows you to apply filters to your token requests. For example, you can exclude certain tokens based on specific criteria. The exact filtering options depend on the available fields and operators supported by Alchemy's API. Please refer to the linked API reference doc above for more information on how to apply filters to your requests.
