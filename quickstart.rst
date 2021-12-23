===========
Quick Start
===========

Our data is accessible through the Chainlink decentralized oracle network. The table below gives the address and jobIDs that you need to specify so as to get data from our oracle. You can visit the Chainlink_ documentation_ to learn more about working with their oracle network.


Shamba Oracle and Job IDs
-------------------------

+---------------------+--------------------------------------------+
| Parameter           | Value                                      |
+=====================+============================================+
| ETH_CHAIN_ID        | 42                                         |
+---------------------+--------------------------------------------+
| Contract Address    | 0xd5CEd81bcd8D8e06E6Ca67AB9988c92CA78EEfe6 |
+---------------------+--------------------------------------------+
| Job ID - Statistics | 5000f186a1b34b19998aa8e5a5e08c92           |
+---------------------+--------------------------------------------+


Accessing Shamba Chainlink Oracle
---------------------------------

The Shamba Chainlink oracle provides geospatial data to smart contracts. To access it you need to provide the oracle address above and the jobID of the analytics you need performed on a dataset. To make this process easier, we have provided tools for generating boilerplate smart contract code to interact with our data oracle.


Requesting Data From The Oracle
-------------------------------

Format the data request using key-value pairs as shown in the README at this link_:

Request Format
``````````````
("data","{"agg_x" : "string", "dataset_code" : "string", "selected_band" : "string", "image_scale" : integer, "start_date" : "string", "end_date" : "string", "geometry" : {"object}}")


Response Data
`````````````

Data returned is of type integer, and is the value from the API multiplied by 10**18. This multiplication is done to remove all decimals from the data being returned on-chain.

Known Issues
------------

The geospatial analytics engine for this oracle is built on the Google Cloud Platform. Any performance bottlenecks on services such as Google Earth Engine will affect the availability of this analytics engine. Developers are advised to build their smart contracts in such a way that data requests can be retried later if they fail at any given time.

Similarly, how up-to-date a dataset served by this oracle is depends on how up-to-date the GCP GEE archives are. We recommend reading more about a dataset you intend to use to learn about its details including granularity and availability.

In particular, users are advised to check the geographic coverage of the dataset they want to use. Some datasets offer regional coverage while others offer global coverage.

Links to the GEE archives for each dataset we provide are given in the Data Model section of this documentation.

Specifications with very large areas of interest or long durations of time may cause the analytics engine to time out. Again this is an inherent limitation of the GCP GEE service and developers are advised to keep this in mind when specifying their geospatial analytics requests.



.. _link: https://github.com/shambadynamic/geostatsExternalAdapter
.. _Chainlink: https://docs.chain.link
.. _documentation: https://docs.chain.link