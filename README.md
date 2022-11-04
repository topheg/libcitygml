libcitygml
==========
[![Build Status](https://travis-ci.org/jklimke/libcitygml.svg?branch=master)](https://travis-ci.org/jklimke/libcitygml)

[CityGML](http://www.citygml.org/) (City Geography Markup Language) is an XML-based schema for the modelling and exchange of georeferenced 3D city and landscape models that is quickly being adopted on an international level.

libcitygml is a small and easy to use open source C++ library for parsing CityGML files in such a way that data can be easily exploited by 3D rendering applications (geometry data are tesselated and optimized for rendering during parsing). For instance, it can be used to develop readers of CityGML files in many 3D based applications (OpenGL, OpenSceneGraph, ...) Most metadata are not lost, they are available through a per-node hashmap.

The project also contains a loader plugin for [OpenSceneGraph](http://www.openscenegraph.org/). It enables OpenSceneGraph (if installed) to read citygml documents for easy rendering and further graphical optimization.

libcitygml was initally developed by the 3D team of BRGM (the French leading public institution involved in the Earth Science field for the sustainable management of natural resources and surface and subsurface risks) for the research project DeepCity3D. It is now conducted as a Github open source project.

It was moved to github due to inactivity of the project on google code (https://code.google.com/p/libcitygml/).


How to Setup
============

The project is based on the CMAKE build system and should be pretty straight forward to setup.

Dependencies:

The XercesC xml parsing library is the only requirement compiling and using libcitygml. Please use a version > 3.1 compiled with an SDK that is compatible with C++11.

OpenGL is required if you want to use the tesselator provided in the project. Otherwise, you can provide another implementation by inheriting TesselatorBase, or not use tesselation. Set the cmake option "LIBCITYGML_USE_OPENGL" to OFF to disable the use of OpenGL.

GDAL is required if coordinate transformations should be applied during paring.
Set the cmake option "LIBCITYGML_USE_GDAL" to OFF to disable the use of GDAL.

OpenSceneGraph is required to build the plugin.
Set the cmake option "LIBCITYGML_OSGPLUGIN" to ON to enable the build of the plugin.

Test Data Attribution
=====================


Overview over the testing data within the "data" directory:

| Dataset                               | Attribution                                               | Source                                                                                                    |
| -------------------------             |:---------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------:| 
| data/b1_lod2_cs_w_sem.gml             | https://www.citygml.org/samplefiles/building/             | [https://www.citygml.org](https://www.citygml.org/samplefiles/)                                           |
| data/b1_lod2_s.gml                    | https://www.citygml.org/samplefiles/building/             | [https://www.citygml.org](https://www.citygml.org/samplefiles/)                                           |
| data/berlin_open_data_sample_data.gml | Berlin Partner für Wirtschaft und Technologie GmbH        | [Berlin Partner Download Portal](http://www.businesslocationcenter.de/berlin3d-downloadportal/?lang=en)   |
| data/FZK-Haus-LoD0-KIT-IAI-KHH-B36-V1.gml | Institute for Automation and Applied Computer Science (IAI) / Karlsruhe Institute of Technology (KIT) | https://www.citygmlwiki.org/index.php?title=FZK_Haus |





