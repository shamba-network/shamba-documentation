===========
Quick Start
===========

Our data is accessible through the Chainlink decentralized oracle network. The table below gives the operator address and jobIDs that you need to specify so as to get data from our oracle. You can visit the Chainlink_ documentation_ to learn more about working with their oracle network.


Shamba Oracle and Job IDs
-------------------------

+---------------------+--------------------------------------------+
| Parameter           | Value                                      |
+=====================+============================================+
| ETH_CHAIN_ID        | 42                                         |
+---------------------+--------------------------------------------+
| Oracle Address      | 0xf4434feDd55D3d6573627F39fA39867b23f4Bf7F |
+---------------------+--------------------------------------------+
| Job ID - Statistics | 83191779e6c74593b7a99bea8c116e31           |
+---------------------+--------------------------------------------+
| Job ID - Fire       | fd78aec23f7d4995bf0799cdd38e7e6f           |
+---------------------+--------------------------------------------+


Accessing Shamba Chainlink Oracle
---------------------------------

The Shamba Chainlink oracle provides geospatial data to smart contracts. To access it you need to provide the operator address above and the jobID of the analytics you need performed on a dataset. To make this process easier, we have provided tools for generating boilerplate smart contract code to interact with our data oracle.


Requesting Data From The Oracle
-------------------------------

Format the data request using key-value pairs as shown in the README at this link_:

Request Format for Statistics Data
``````````````````````````````````
("data","{"agg_x" : "string", "dataset_code" : "string", "selected_band" : "string", "image_scale" : integer, "start_date" : "string", "end_date" : "string", "geometry" : {"object}}")

Request Format for Fire-Analysis Data
`````````````````````````````````````
("data","{"dataset_code" : "string", "selected_band" : "string", "image_scale" : integer, "start_date" : "string", "end_date" : "string", "geometry" : {"object}}")

So, basically depending upon the request body, the common external adapter will trigger the statistics and fire GeoAPI endpoints.

If the value of the data field is having “agg_x” field in its object, then the data will be sent to the statistics endpoint, otherwise it’ll be sent to the fire-analysis endpoint. 

Along with this request being sent to the respective endpoints, the response of the GeoAPI along with the request body and other parameters like operator address, contract address from which the oracle being called, transaction hash generated after the successful oracle call, all of this data is being saved into the Web3 Storage by using the IPFS/Filecoin implementation for the same. 

Response Data for Statistics
````````````````````````````

Data returned is of type map having two corresponding fields as a string storing the value of cid and an integer storing the value of geostatistic result (which is getting the value from the API multiplied by 10**18. This multiplication is done to remove all decimals from the data being returned on-chain).

Response Data for Fire-Analysis
```````````````````````````````

Data returned is of type map having two corresponding fields as a string that is storing the cid and an array that is storing the values of fire detection in the sequence of property ids, like 1 (if the fire is detected) and 9 (if the fire is not detected). The reason behind having the values as 1 and 9 is because the by-default value in the solidity (smart contract) is 0, so if there’s no data in any index of the array, then it returns it as 0.

We’re getting the value of fire-detection from the API as true or false, so assigning a value of 1 if it returns true and 9 if it returns false.

Solidity Smart Contract for Statistics
``````````````````````````````````````

https://github.com/shambadynamic/Shamba_Geostats_Fire_Common_Setup/blob/master/SoliditySmartContracts/GeoConsumer.sol


Solidity Smart Contract for Fire-Analysis
`````````````````````````````````````````

https://github.com/shambadynamic/Shamba_Geostats_Fire_Common_Setup/blob/master/SoliditySmartContracts/FireConsumer.sol


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