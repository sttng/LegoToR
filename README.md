# LegoToR & LegoToRHD
**LegoToR** is a Lego Digital Designer (LDD) to RenderMan converter. LegoToR takes a LDD lfx file as input and converts it into RenderMan compliant rib files which then can be rendered with Pixar RenderMan.

**LegoToRHD** is a Lego Digital Designer (LDD) to Universal Scene Descriptor (USD) converter. LegoToRHD takes a LDD lfx file as input and converts it into a set of USD compliant files. USD is used by Apple's ARKit and in a multitude of other professional applications from Pixar, Autodesk, etc.

## LegoToR

### Requirements

* Python
* LDD
* macOS (Windows, Linux may work with small modifications)
* Pixar RenderMan

### Usage

#### Simple Usage

```
/LegoToR.py myLDDinputfile.lxf -v -cam 0
```

#### Detailed Usage

## LegoToRHD

### Requirements

* Python
* LDD
* macOS (Windows, Linux may work with small modifications)

### Usage

#### Simple Usage

```
/LegoToRHD.py myLDDinputfile.lxf -np
```

#### Detailed Usage
