# Berkeley Segmentation Software

This repository is intended to contain the Berkeley Segmentation Software source files and isolate the execution inside a docker container. The docker container is based on an image that comes powered with a compiled GDAL. In order to make it run, the segmentation folder must be atached as a volume:

```
docker run -v /Users/agutierrez/Development/madmex/segmentation/segmentation/:/usr/local/bin/segmentation/ -it segmentation/v7 python /usr/local/bin/segmentation/segment.py /usr/local/bin/segmentation/test/ag.bmp
```