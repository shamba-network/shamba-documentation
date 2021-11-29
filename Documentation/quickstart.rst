===========
Quick Start
===========

Our data is accessible through the Chainlink decentralized oracle network. The table below gives the address and jobIDs that you need to specify so as to get various data from our oracle. You can visit the Chainlink documentation to learn more about working with their oracle network.


Shamba Oracle and Job IDs
-------------------------

+-------------------+--------------------------------------------+
| Parameter         | Value                                      |
+===================+============================================+
| ETH_CHAIN_ID      | 42                                         |
+-------------------+--------------------------------------------+
| Contract Address  | 0xd5CEd81bcd8D8e06E6Ca67AB9988c92CA78EEfe6 |
+-------------------+--------------------------------------------+
| Job ID - Mean     | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+
| Job ID - Max      | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+
| Job ID - Min      | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+
| Job ID - Median   | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+
| Job ID - StdDev   | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+
| Job ID - Variance | 3bea9c0a18fc4a7f8c9b5fead223270f           |
+-------------------+--------------------------------------------+


Accessing Shamba Chainlink Oracle
---------------------------------

The Shamba Chainlink oracle provides geospatial data to smart contracts. To access it you need to provide the oracle address above and the jobID of the analytics you need performed on a dataset. To make this process easier, we have provided tools for generating boilerplate smart contract code to interact with our data oracle.
