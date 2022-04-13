==========
Data Model
==========

The Shamba oracle currently supports running two types of analytics on geospatial data. Below we describe each of these including their inputs and output.


Descriptive Statistics Analysis
-------------------------------

This analysis aims at getting descriptive statistics. Given an area of interest and a dataset to reference, this analysis returns standard metrics such as maximum, minimum, mean, median and variance. These descriptive statistics are useful for setting thresholds and triggers in many parametric smart contracts. The required statistical metric is specified in the “agg_x” parameter.


Inputs:

- "agg_x": "string",
- "dataset_code": "string",
- "selected_band": "string",
- "geometry": {json},
- "start_date": "string",
- "end_date": "string",
- "image_scale": integer,

Outputs:

- int256

Fire Analysis
-------------

This analysis aims at determining if an area of interest falls within a detected fire. It performs a topology analysis to determine if a fire extends to a specified area of interest. Given an area of interest and a dataset to reference, this analysis returns a boolean indicating whether a fire was detected or not. Boolean values (1 - TRUE, 9 - FALSE).

Inputs:

- "dataset_code": "string",
- "selected_band": "string",
- "geometry": {json},
- "start_date": "string",
- "end_date": "string",
- "image_scale": integer,

Outputs:

- uint256 (1 - TRUE, 9 - FALSE)

The GeoAPI that Powers our Oracle
---------------------------------

The Shamba oracle is powered by a geospatial API service running on Google Earth Engine. You can access this API service outside smart contracts for your other applications. Get in touch to learn more about integrating with our GeoAPI.


Thematic Areas & Dataset
------------------------

The Shamba oracle uses regularly updated geospatial data from various global providers. Different providers use different algorithms to compute the same metric, so it is recommended that users go through the literature for each dataset. Normalization has been performed where necessary to standardize values from different datasets under a common theme.

Air Quality
^^^^^^^^^^^

.. list-table::
   
   
    *   - .. figure:: _static/Shamba_Dataset_Flyers_21.png
                :target: Link_21_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | CO_column_number_density |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_21_                 |
                +--------------------------+--------------------------+

        - .. figure:: _static/Shamba_Dataset_Flyers_22.png
                :target: Link_22_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | CO_column_number_density |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_22_                 |
                +--------------------------+--------------------------+
    
    *   - .. figure:: _static/Shamba_Dataset_Flyers_23.png
                :target: Link_23_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | SO2_column_number_density|
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_23_                 |
                +--------------------------+--------------------------+

        - .. figure:: _static/Shamba_Dataset_Flyers_24.png
                :target: Link_24_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | SO2_column_number_density|
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_24_                 |
                +--------------------------+--------------------------+

    *   - .. figure:: _static/Shamba_Dataset_Flyers_25.png
                :target: Link_25_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | NO2_column_number_density|
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_25_                 |
                +--------------------------+--------------------------+

        - .. figure:: _static/Shamba_Dataset_Flyers_26.png
                :target: Link_26_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | NO2_column_number_density|
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_26_                 |
                +--------------------------+--------------------------+

    *   - .. figure:: _static/Shamba_Dataset_Flyers_27.png
                :target: Link_27_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1113.2                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 1 day                    |
                +--------------------------+--------------------------+
                | Bands                    | CH4_column_number_density|
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_27_                 |
                +--------------------------+--------------------------+
                
        -

Evapo-Transpiration
^^^^^^^^^^^^^^^^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_01.png
                :target: Link_1_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 248.2                    |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 10 days                  |
                +--------------------------+--------------------------+
                | Bands                    | L1_AETI_D                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Africa                   |
                +--------------------------+--------------------------+
                | Read More                | Link_1_                  |
                +--------------------------+--------------------------+

        - .. figure:: _static/Shamba_Dataset_Flyers_02.png
                :target: Link_2_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 18924                    |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | L1_RET_E                 |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Africa                   |
                +--------------------------+--------------------------+
                | Read More                | Link_2_                  |
                +--------------------------+--------------------------+
    
    *   - .. figure:: _static/Shamba_Dataset_Flyers_03.png
                :target: Link_3_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 8 days                   |
                +--------------------------+--------------------------+
                | Bands                    | ET                       |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_3_                  |
                +--------------------------+--------------------------+
                
        -

Fire
^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_17.png
                :target: Link_5_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | MaxFRP                   |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_5_                  |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_18.png
                :target: Link_6_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | MaxFRP                   |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_6_                  |
                +--------------------------+--------------------------+
                
    *   - .. figure:: _static/Shamba_Dataset_Flyers_19.png
                :target: Link_7_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 2000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 5 - 15 minutes           |
                +--------------------------+--------------------------+
                | Bands                    | Power                    |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Americas, West Africa    |
                +--------------------------+--------------------------+
                | Read More                | Link_7_                  |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_20.png
                :target: Link_8_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 2000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 5 - 15 minutes           |
                +--------------------------+--------------------------+
                | Bands                    | Power                    |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Americas, West Africa    |
                +--------------------------+--------------------------+
                | Read More                | Link_8_                  |
                +--------------------------+--------------------------+

Precipitation
^^^^^^^^^^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_05.png
                :target: Link_9_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 27830                    |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | Precipitation            |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_9_                  |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_06.png
                :target: Link_10_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 5566                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | Precipitation            |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_10_                 |
                +--------------------------+--------------------------+
                
    *   - .. figure:: _static/Shamba_Dataset_Flyers_07.png
                :target: Link_11_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 11132                    |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Hourly                   |
                +--------------------------+--------------------------+
                | Bands                    | hourlyPrecipRate         |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_11_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_28.png
                :target: Link_28_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 4638.3                   |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 5 days                   |
                +--------------------------+--------------------------+
                | Bands                    | Precipitation            |
                +--------------------------+--------------------------+
                | Geographic Coverage      | USA                      |
                +--------------------------+--------------------------+
                | Read More                | Link_28_                 |
                +--------------------------+--------------------------+
 

Soil Moisture
^^^^^^^^^^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_08.png
                :target: Link_12_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 10000                    |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 2 - 3 days               |
                +--------------------------+--------------------------+
                | Bands                    | ssm                      |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_12_                 |
                +--------------------------+--------------------------+
        -

Temperature
^^^^^^^^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_09.png
                :target: Link_13_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | LST_Day_1km              |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_13_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_10.png
                :target: Link_14_

                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 1000                     |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | Daily                    |
                +--------------------------+--------------------------+
                | Bands                    | LST_Day_1km              |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_14_                 |
                +--------------------------+--------------------------+
                
Vegetation
^^^^^^^^^^

.. list-table:: 

    *   - .. figure:: _static/Shamba_Dataset_Flyers_04.png
                :target: Link_15_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 10                       |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 5 days                   |
                +--------------------------+--------------------------+
                | Bands                    | NDVI, EVI                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_15_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_11.png
                :target: Link_16_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 4 days                   |
                +--------------------------+--------------------------+
                | Bands                    | Fpar, Lai                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_16_                 |
                +--------------------------+--------------------------+
                
    *   - .. figure:: _static/Shamba_Dataset_Flyers_12.png
                :target: Link_17_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 250                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 16 days                  |
                +--------------------------+--------------------------+
                | Bands                    | NDVI, EVI                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_17_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_13.png
                :target: Link_18_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 250                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 16 days                  |
                +--------------------------+--------------------------+
                | Bands                    | NDVI, EVI                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_18_                 |
                +--------------------------+--------------------------+
                
    *   - .. figure:: _static/Shamba_Dataset_Flyers_14.png
                :target: Link_19_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 8 days                   |
                +--------------------------+--------------------------+
                | Bands                    | Fpar, Lai                |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_19_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_15.png
                :target: Link_20_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 16 days                  |
                +--------------------------+--------------------------+
                | Bands                    | NDVI, EVI, EVI2          |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_20_                 |
                +--------------------------+--------------------------+

    *   - .. figure:: _static/Shamba_Dataset_Flyers_29.png
                :target: Link_29_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 30                       |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 16 days                  |
                +--------------------------+--------------------------+
                | Bands                    | GPP                      |
                +--------------------------+--------------------------+
                | Geographic Coverage      | USA                      |
                +--------------------------+--------------------------+
                | Read More                | Link_29_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_30.png
                :target: Link_30_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 250                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 8 days                   |
                +--------------------------+--------------------------+
                | Bands                    | GPP                      |
                +--------------------------+--------------------------+
                | Geographic Coverage      | USA                      |
                +--------------------------+--------------------------+
                | Read More                | Link_30_                 |
                +--------------------------+--------------------------+

    *   - .. figure:: _static/Shamba_Dataset_Flyers_31.png
                :target: Link_31_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 8 days                   |
                +--------------------------+--------------------------+
                | Bands                    | Gpp                      |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_31_                 |
                +--------------------------+--------------------------+
                
        - .. figure:: _static/Shamba_Dataset_Flyers_32.png
                :target: Link_32_
                
                ..

                +--------------------------+--------------------------+
                | Properties               | Value                    |
                +==========================+==========================+
                | Pixel Size (metres)      | 500                      |
                +--------------------------+--------------------------+
                | Image Capture Frequency  | 8 days                   |
                +--------------------------+--------------------------+
                | Bands                    | Gpp                      |
                +--------------------------+--------------------------+
                | Geographic Coverage      | Global                   |
                +--------------------------+--------------------------+
                | Read More                | Link_32_                 |
                +--------------------------+--------------------------+
                
.. _Link_3: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD16A2
.. _Link_1: https://developers.google.com/earth-engine/datasets/catalog/FAO_WAPOR_2_L1_AETI_D
.. _Link_2: https://developers.google.com/earth-engine/datasets/catalog/FAO_WAPOR_2_L1_RET_E
.. _Link_7: https://developers.google.com/earth-engine/datasets/catalog/NOAA_GOES_16_FDCF
.. _Link_8: https://developers.google.com/earth-engine/datasets/catalog/NOAA_GOES_17_FDCF
.. _Link_5: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD14A1
.. _Link_6: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MYD14A1
.. _Link_10: https://developers.google.com/earth-engine/datasets/catalog/UCSB-CHG_CHIRPS_DAILY
.. _Link_11: https://developers.google.com/earth-engine/datasets/catalog/JAXA_GPM_L3_GSMaP_v6_operational
.. _Link_9: https://developers.google.com/earth-engine/datasets/catalog/NOAA_PERSIANN-CDR
.. _Link_12: https://developers.google.com/earth-engine/datasets/catalog/NASA_USDA_HSL_SMAP10KM_soil_moisture
.. _Link_13: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD11A1
.. _Link_14: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MYD11A1
.. _Link_16: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MCD15A3H
.. _Link_17: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD13Q1
.. _Link_18: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MYD13Q1
.. _Link_19: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MYD15A2H
.. _Link_15: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR
.. _Link_20: https://developers.google.com/earth-engine/datasets/catalog/NOAA_VIIRS_001_VNP13A1
.. _Link_21: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_NRTI_L3_CO
.. _Link_22: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_CO
.. _Link_23: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_NRTI_L3_SO2
.. _Link_24: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_SO2
.. _Link_25: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_NRTI_L3_NO2
.. _Link_26: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_NO2
.. _Link_27: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S5P_OFFL_L3_CH4
.. _Link_28: https://developers.google.com/earth-engine/datasets/catalog/GRIDMET_DROUGHT
.. _Link_29: https://developers.google.com/earth-engine/datasets/catalog/UMT_NTSG_v2_LANDSAT_GPP
.. _Link_30: https://developers.google.com/earth-engine/datasets/catalog/UMT_NTSG_v2_MODIS_GPP
.. _Link_31: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MYD17A2H
.. _Link_32: https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD17A2H