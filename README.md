# **Civil STAC**

Experimental Python toolkit for the discovery and cataloguing of geospatial assets using STAC.

## **The Problem**

Organizations that design, build, and maintain civil infrastructure face increasing demands to manage large amounts of geospatial data. While digital deliverables increase in size and complexity, data management best practices remain largely manual. 

Many organizations do not have a searchable catalog of existing geospatial assets. As a result, organizations and projects struggle to determine the following:

* **Which geospatial assets does each organization already own?** Large repositories of geospatial assets are frequently exchanged as .zip archives and manually extracted and inspected at the beginning of projects. Directory structures and file naming conventions vary and are enforced manually. Duplicate data is often purchased, stored, and transferred unnecessarily.   
* **What are the geographic boundaries of each of these geospatial assets?** Information about CRS and geographic bounds may be inaccurate, incomplete, or difficult to discover.   
* **Which geospatial assets are suitable for use in specific projects?** Geospatial assets are uploaded to individual project directories with manual or no validation of CRS metadata.

There is no easy way for users to view geospatial assets already owned by an organization.

## **Project Goals**

The aim of this project is to develop a toolset that makes STAC accessible to organizations involved in the lifecycle of civil infrastructure assets. The end goal would be the development of a complete workflow organizations can use to catalogue and validate existing assets in geospatial repositories. Key design principles include:

* All data remains under the control of the owners  
* Read only-access of source repositories  
* Easy eventual IT deployment and minimal user training

## 

## **Initial Scope and Implementation**

Version 0.1 focuses exclusively on discovering and cataloguing GeoTIFFs stored in Amazon S3.

Planned functionality:

1. Connect to client-owned S3 buckets accessed using read-only AWS permissions.  
2. Discover GeoTIFF files in project directories.  
3. Extract geospatial metadata, including CRS, bounds, and resolution.  
4. Identify missing or invalid metadata.  
5. Generate STAC Items referencing the original files.  
6. Catalogue and organize STAC metadata.

Initial implementation uses:

* boto3 to discover GeoTIFFs stored in S3.  
* Rasterio to inspect raster metadata.  
* rio-stac to generate STAC Items from raster files.  
* PySTAC to catalogue STAC Items.

## **Future Scope**

Future functionality may include:

1. Discovery of other common geospatial file formats (e.g. LAS, LAZ, OBJ, GLB, IFC, LandXML, etc) and generation of STAC Items.  
2. Searchable catalogue of all STAC Items / STAC API implementation.  
3. OpenLayers frontend for interactive map search of STAC Items.  
4. Validation of suitability of each STAC Item for specific project specifications. 

## **License**

This project is licensed under the MIT License.

