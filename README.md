# LegoToR & LegoToRHD
**LegoToR** is a LEGO Digital Designer (LDD) to RenderMan converter. LegoToR takes a LDD lxf file as input and converts it into RenderMan compliant rib files which then can be rendered with Pixar RenderMan.

**LegoToRHD** is a LEGO Digital Designer (LDD) to Universal Scene Descriptor (USD) converter. LegoToRHD takes a LDD lxf file as input and converts it into a set of USD compliant files. USD is used by Apple's ARKit and in a multitude of other professional applications from Pixar, Autodesk, etc.

Both LegoToR & LegoToRHD rely on **pylddlib**. pylddlib.py can be used stand-alone as well. In that case it will export an obj file of the provided LDD lxf file.

### Requirements

* Python (tested with Python 2.7.10 on macOS, Python 3.8.3 on Windows 10, Python 3.8.5 on Linux)
* LDD 4.3.11 (see https://www.eurobricks.com/forum/index.php?/forums/topic/149308-lego-digital-designer-install-problem/ on how to get LDD 4.3.11 for Windows)
* OS 
  - tested on macOS 10.14
  - minor testing on Windows 10 
  - preliminary testing on Linux with Wine 5.0.2 for running LDD on Linux (specifically Ubuntu 20.04.1 LTS was used, others may work with small modifications)
* Pixar RenderMan (tested on RenderMan 22.3 - 23.5)

## LegoToR

### Usage

* **on Windows LDD must be closed, otherwise the tool can not read the db.lif file !**

#### Simple Usage

```
./LegoToR.py myLDDinputfile.lxf -v -cam 0
```

#### Detailed Usage

```
Detailed usage: LegoToR.py [-h] [-s [SRATE]] [-p [PIXELVAR]] [-fo [FOV]] [-fs [FSTOP]]
                  [-wd [WIDTH]] [-ht [HEIGHT]] [-sa [SEARCHARCHIVE]]
                  [-st [SEARCHTEXTURE]] [-cam [CAMERA]] [-d] [-v] [-u] [-o]
                  [-t] [-w] [-n] [-z] [-b] [-fl] [-np] [-nn] [-nl]
                  infile

mandatory arguments:
  infile                required input LXF file

optional arguments:
  -h, --help            show this help message and exit
  -s [SRATE], --srate [SRATE]
                        modify shading rate. Default 10
  -p [PIXELVAR], --pixelvar [PIXELVAR]
                        modify the pixel variance. Default 0.1
  -fo [FOV], --fov [FOV]
                        projection fov. Default 25.0
  -fs [FSTOP], --fstop [FSTOP]
                        fStop. Default 9.99999968e+37 (unlimited)
  -wd [WIDTH], --width [WIDTH]
                        width of image. Default 1280
  -ht [HEIGHT], --height [HEIGHT]
                        height of image. Default 720
  -sa [SEARCHARCHIVE], --searcharchive [SEARCHARCHIVE]
                        searchpath archive. Default current working dir
  -st [SEARCHTEXTURE], --searchtexture [SEARCHTEXTURE]
                        searchpath texture. Default current working dir
  -cam [CAMERA], --camera [CAMERA]
                        set active camera. Default is -1 for Cam--1 'Minus 1'
  -d, --default         use PxrPathTracer
  -v, --vcm             use PxrVCM
  -u, --unified         use PxrUnified. Enable also in rendermn.ini to work!
  -o, --occlusion       use Occlusion
  -t, --direct          use PxrDirect
  -w, --wire            use PxrVisualizer with wireframe shaded
  -n, --normals         use PxrVisualizer with wireframe and Normals
  -z, --wst             use PxrVisualizer with wireframe and ST
  -b, --bxdf            use PxrVisualizer with wireframe and bxdf
  -fl, --flat           use PxrVisualizer with wireframe flat
  -np, --noplane        disable ground plane. Useful for space ships!
  -nn, --nonormals      disable writing of normals, as some normals in LDD may have problems
  -nl, --nologo         disable logo on studs
  -nc, --nocsv          disable reading of color values from csv file. Use LDD's built-in colors instead
```

## LegoToRHD

### Usage

* **on Windows LDD must be closed, otherwise the tool can not read the db.lif file !**

#### Simple Usage

```
./LegoToRHD.py myLDDinputfile.lxf -np
```

#### Detailed Usage

```
Detailed usage: LegoToR.py [-h] [-np] [-nn] [-nl]
                  infile

mandatory arguments:
  infile                required input LXF file

optional arguments:
  -h, --help            show this help message and exit
  -np, --noplane        disable ground plane. Useful for space ships!
  -nn, --nonormals      disable writing of normals, as some normals in LDD may have problems
  -nl, --nologo         disable logo on studs
  -nc, --nocsv          disable reading of color values from csv file. Use LDD's built-in colors instead
```

# Credits

* jonnysp https://github.com/jonnysp for pyldd2obj.py. Most of the work is based on this great tool.
