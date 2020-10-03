# LegoToR & LegoToRHD
**LegoToR** is a LEGO Digital Designer (LDD) to RenderMan converter. LegoToR takes a LDD lxf file as input and converts it into RenderMan compliant rib files which then can be rendered with Pixar RenderMan.

**LegoToRHD** is a LEGO Digital Designer (LDD) to Universal Scene Descriptor (USD) converter. LegoToRHD takes a LDD lxf file as input and converts it into a set of USD compliant files. USD is used by Apple's ARKit and in a multitude of other professional applications from Pixar, Autodesk, etc.

### Requirements

* Python (tested on Python 2.7.10 on macOS and Python 3.8 on Windows 10)
* LDD 4.3.11
* macOS (tested on macOS 10.14) or Windows 10 (Linux may work with small modifications)
* Pixar RenderMan (tested on RenderMan 22.3 - 23.4)

## LegoToR

### Usage

**on Windows LDD must be closed, otherwise the tools can not read the db.lif file**

#### Simple Usage

```
/LegoToR.py myLDDinputfile.lxf -v -cam 0
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
```

## LegoToRHD

### Usage

#### Simple Usage

```
/LegoToRHD.py myLDDinputfile.lxf -np
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
```

# Credits

* jonnysp https://github.com/jonnysp for pyldd2obj.py. Most of the work is based on this great tool.
