=============
Contract Tool
=============

The Contracts_ Tool_ aims to help a developer quickly generate smart contract boilerplate code with the parametric specifications of their choosing. It helps a user codify what they learned in the Insights tool into smart contract boilerplate code. This code can then be extended to serve any application a developer might need.

Introduction
------------

Below is an interface from the Contract tool. The webmap on the left allows you to designate your area of interest while the panel on the right helps you codify the specifications for your parametric smart contract.

.. list-table:: 

    *   - .. figure:: _static/defi_front.png

                Landing page

    *    - .. figure:: _static/defi_drawing.png

                Drawing section

    *   - .. figure:: _static/defi_params.png

                Parameter setup

    *    - .. figure:: _static/defi_api_request.png

                API request code

    *   - .. figure:: _static/defi_smart_code.png

                Smart contract code

Usage
-----

1. First do some research to determine the parameters for your area of interest.
2. The web map allows you to search for an area and designate its boundary.
3. Use the search input to search by name and zoom into your area of interest.
4. Use the drawing tools on the web map to specify what your area of interest is.
5. This will generate some Geojson that describes the boundaries of this area.
6. Next use the input tab to specify the dataset-metric-threshold combination.
7. Select the options for each input field and submit the form to generate code.
8. On the request tab, you will find the Json representation of your specification.
9. On the code tab, you will find the smart contract boilerplate code with these specs.
10. Copy this code from this tab and into your favorite development environment.
11. The code allows you to get geospatial data for an area into your smart contract. 
12. You can now use this data in any real-world application you are developing.


.. _Contracts: https://contracts.shamba.app
.. _Tool: https://contracts.shamba.app