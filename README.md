# Berkeley Segmentation Software

This repository is intended to contain the Berkeley Segmentation Software source files and isolate the execution inside a docker container. The docker container is based on an image that comes powered with a compiled GDAL. 

To build the image, run the following command from the directory where the Dockerfile is found:

```
docker build -t <image-name> .
```

A file with the license must be included when the segmentation runs for example, a file named license.txt including (not an actual license number):

```
58062427312
```

In order to run an example, the segmentation folder must be atached as a volume:

```
docker run -v <path-to-docker-segmentation>/segmentation/:/segmentation/ -v <path-to-license-file>/license.txt:/segmentation/license.txt  <image-name> python /segmentation/segment.py /segmentation/test/ag.bmp
```



The result will be written in the same place where the original image was found, in this case:

```
<path-to-docker-segmentation>/segmentation/test
```