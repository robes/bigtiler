# Installation and user guide for BigTiler utilities #

BigTiler is an open source software tool that converts small or large proprietary images into open formats. Its features include:

> Creating pyramidal tiles compatible with Zoomify viewers
> Creating a JPEG thumbnail image
> Converting proprietary annotation formats into Zoomify XML annotation format
> Retrieving proprietary metadata from the image

BigTiler uses the Bio-Formats library to read pixel data and metadata from proprietary images. For a list of supported image types, refer to the FAQ section in this guide.


# System Requirements #
## Tested Platforms ##
BigTiler has been tested on the following operating systems:
  * CentOS 5/6 64-bit Linux
  * Windows 7
## Hardware Recommendations ##
### Disk Capacity ###
You should provision at least 2.5X of the compressed size your expected image set for permanent disk capacity. However, actual disk usage resulting from BigTiler utilities depends on the compression of the original image.
### RAM ###
A minimum of 1 GB is recommended for each process that will simultaneously run BigTiler utilities.
### CPU ###
A 64-bit CPU with a minimum of two cores and 2.4GHz speed is recommended for a single BigTiler utility process. Additional simultaneous processes would require more CPU resources to be allocated, since the BigTiler utilities are extremely CPU-intensive.
### Network ###
N/A
## Prerequisites ##
  * Sun Java JRE 1.6+
# Installation #
  1. Download the latest BigTiler package from the downloads section.
  1. Extract the package onto your system. The package will create a bigtiler-bin directory containing the BigTiler utilities in your current directory.  _For license information on BigTiler and third-party libraries, refer to the licenses directory inside of the BigTiler package._
# Utilities #
## Convert image to Zoomify Tiles ##
### Usage ###
```
convert_image_to_zoomify_tiles.<sh|bat> <source image> <zoomify tile directory>
```
where <source image> is the image to convert to Zoomify tiles and <zoomify tile directory> is the base directory to write the tiles. If <zoomify tile directory> does not exist, it will be created.
## Create thumbnail image ##
### Usage ###
```
generate_thumbnail.<sh|bat> <source image> <thumbnail filename>
```
where <source image> is the image to create a thumbnail image from and <thumbnail filename> is the thumbnail file to create. The thumbnail will be written in JPEG format.
## Convert proprietary annotation to Zoomify XML format ##
### Usage ###
```
convert_image_annotation_to_zoomify.<sh|bat> <source image>
```
where <source image> is the image to convert the proprietary annotations from. If proprietary annotations were read from the image, the converted Zoomify XML document will be output to the shell.
## Retrieve proprietary metadata ##
### Usage ###
```
get_image_metadata.<sh|bat> [--series=<series>] <source image> [<metadata field 1> <metadata field 2>...]
```
where <source image> is the image to retrieve proprietary annotations from. Image metadata will be output to the shell in key=value format. If series is specified, it will retrieve metadata for that particular image series (default is to retrieve global metadata). If one or more metadata field arguments are specified, only those particular metadata fields will be output to the shell (default is to output all metadata).
# FAQ #
## Which image types are supported in BigTiler? ##
BigTiler supports any image type that is readable by the Bio-Formats library, but the following image types have been tested with BigTiler:
  * JPEG
  * TIFF (compressions - TBD)
  * BigTIFF
  * Aperio SVS
  * Hammamatsu NDPI (width and height < 65500 pixels)
  * Olympus VSI
For a complete list of supported image types, refer to the Bio-Formats supported type list.
[http://loci.wisc.edu/software/bio-formats](http://loci.wisc.edu/software/bio-formats)
_If you are interested in running BigTiler on image types that are listed in our tested list, feel free to contact us._
## How long will it take to convert an image to Zoomify JPEG tiles? ##
Since the BigTiler utilities are very CPU and disk-write intensive, performance will vary on each system. However we have noticed that it takes approximately 1 hour per 1 GB of compressed image space to finish processing the image into tiles.
# Contact Us #
Email support@birncommunity.org