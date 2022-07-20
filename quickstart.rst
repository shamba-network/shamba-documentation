===========
Quick Start
===========

Our data is accessible through the Chainlink decentralized oracle network. The table below gives the list of networks supported by our oracle and their corresponding details that you need to specify so as to get data from our oracle. You can visit the Chainlink_ documentation_ to learn more about working with their oracle network.


Shamba Oracle and Operator Numbers
-------------------------

+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+
| Operator_Number |      Network     | ETH_CHAIN_ID | Mainnet Block Explorer for getting API key | Testnet Block Explorer for deployed contract |
+=================+==================+==============+============================================+==============================================+
|        1        | Arbitrum Rinkeby |    421611    |      https://arbiscan.io/myapikey          |       https://testnet.arbiscan.io/           |
+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+
|        2        | Avalanche Fuji   |    43113     |      https://snowtrace.io/myapikey         |       https://testnet.snowtrace.io/          |
+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+
|        3        | Ethereum Goerli  |    5         |      https://etherscan.io/myapikey         |       https://goerli.etherscan.io/           |
+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+
|        4        | Ethereum Rinkeby |    4         |      https://etherscan.io/myapikey         |       https://rinkeby.etherscan.io/          |
+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+
|        5        | Polygon Mumbai   |    80001     |      https://polygonscan.com/myapikey      |       https://mumbai.polygonscan.com/        |
+-----------------+------------------+--------------+--------------------------------------------+----------------------------------------------+




Accessing Shamba Chainlink Oracle
---------------------------------

The Shamba Chainlink oracle provides geospatial data to smart contracts. To access it you need to import the ShambaGeoConsumer_ and ShambaFireConsumer_ smart-contracts from our smart-contract-kit_ or intall it via our npm_ module_. To make this process easier, we have provided tools like our contracts_ tool_ for generating boilerplate smart contract code to interact with our data oracle. And we also have our brownie_ and hardhat_ mixes setup for the Oracle Facing Smart Contracts to interact with the same.


Requesting Data From The Oracle
-------------------------------

Deploy your Oracle Facing Smart Contract and then fund the same with 1 test LINK corresponding to your deployed contract's network, and then call the ``requestGeostatsData()`` or ``requestFireData()`` function with the required parameters as explained in this README_. 

**NOTE**: You can get the LINK addresses and their corresponding faucets from here_.

Response Data for Geo-Statistics
````````````````````````````

Data returned is of type map having two corresponding fields as a string storing the value of cid and an integer storing the value of geostatistic result (which is getting the value from the API multiplied by 10**18. This multiplication is done to remove all decimals from the data being returned on-chain).

You can see the response by calling the ``getGeostatsData()`` and ``getCid()`` functions.

Response Data for Fire-Analysis
```````````````````````````````

Data returned is of type map having two corresponding fields as a string that is storing the cid and an array that is storing the values of fire detection in the sequence of property ids, like 1 (if the fire is detected) and 9 (if the fire is not detected). The reason behind having the values as 1 and 9 is because the by-default value in the solidity (smart contract) is 0, so if there’s no data in any index of the array, then it returns it as 0.

We’re getting the value of fire-detection from the API as true or false, so assigning a value of 1 if it returns true and 9 if it returns false.

You can see the response by calling the ``getFireData()`` and ``getCid()`` functions.

Known Issues
------------

The geospatial analytics engine for this oracle is built on the Google Cloud Platform. Any performance bottlenecks on services such as Google Earth Engine will affect the availability of this analytics engine. Developers are advised to build their smart contracts in such a way that data requests can be retried later if they fail at any given time.

Similarly, how up-to-date a dataset served by this oracle is, depends on how up-to-date the GEE data registries are. We recommend reading more about a dataset you intend to use to learn about its details including granularity and availability.

In particular, users are advised to check the geographic coverage of the dataset they want to use. Some datasets offer regional coverage while others offer global coverage.

Links to the GEE pages for each dataset we provide are given in the datasets section of this documentation.

Specifications with very large areas of interest or long durations of time may cause the analytics API to time out. Developers are advised to keep this in mind when specifying their geographical extents.



.. _link: https://github.com/shambadynamic/Shamba_Geostats_Fire_Common_Setup
.. _Chainlink: https://docs.chain.link
.. _documentation: https://docs.chain.link
.. _smart-contract-kit: https://github.com/shambadynamic/shamba-smartcontractkit
.. _ShambaGeoConsumer: https://github.com/shambadynamic/shamba-smartcontractkit/blob/main/contracts/ShambaGeoConsumer.sol
.. _SHambaFireConsumer: https://github.com/shambadynamic/shamba-smartcontractkit/blob/main/contracts/ShambaFireConsumer.sol
.. _npm: https://www.npmjs.com/package/@shambadynamic/contracts
.. _module: https://www.npmjs.com/package/@shambadynamic/contracts
.. _contracts: https://contracts.shamba.app
.. _tool: https://contracts.shamba.app
.. _brownie: https://github.com/shambadynamic/BrownieSetup_OracleFacingSmartContracts
.. _hardhat: https://github.com/shambadynamic/HardhatSetup_OracleFacingSmartContracts
.. _here: https://docs.chain.link/docs/link-token-contracts
.. _README: https://github.com/shambadynamic/HardhatSetup_OracleFacingSmartContracts#readme