# docker-openfalcon-nodata

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-nodata .
```

## Run

### Basic Run

Use default configuration, and falcon-nodata package.

```
$sudo docker run -dti --name nodata -p 6090:6090 openfalcon-nodata
```

### Advanced Run

+ Self-defined configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Nodata](http://book.open-falcon.com/zh/install_from_src/nodata.html).

+ New falcon-nodata package

    Replace file **falcon-nodata.tar.gz** in the volume */package*.
    
For example, **cfg.json** in /tmp/config and **falcon-nodata.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name nodata -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 6090:6090 openfalcon-nodata
```
