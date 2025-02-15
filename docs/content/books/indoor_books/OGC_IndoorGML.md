# Indoor GML: A Standard Approach for Indoor Maps

## 1 - Introduction

Indoor location technologies are a diverse set of technologies that use different physical phenomena and processing techniques to gather and present information. All information has to come together for visualisation purposes, usually in the shape of a map. Compared to a visualisation of the outdoor environment, the specifications for indoor maps are not as easily defined. Therefore a standard, the OGC's IndoorGML was developed, serving as a standard data model.

## 2 - Requirements

The required features of a map arise from the constraints the environments present. Other than for an outdoor space, the euclidian distance does not represent the actual distance from point $a$ to $b$ as doors, walls and ceilings might be in the way. Another difference is the purpose of the map. One might divide it up into rooms and hallways, however other representations like public and private areas is possible as well. This requires contextual information of the space, which might be more interesting than the 3D spatial extent of a room.

Rooms, also called cells, are therefore along with their 2- or 3D spatial extent given a set of attributes, such as a classification, usage etc. 

## 3 - Basic Concepts

The OGC published a set of requirements for indoor maps that include but are not limited to:
* Reflecting properties of indoor space
* Cellular space model
* Minimal set of specifications
* Interoperability with other standards
* Extensibility

The OGC's model is based on the cellular space model. A cellular space is defined as a set of non-overlapping cells, where each cell has an identifier and the union of cells is a subet of the entire indoor space. This is integrated by four main concepts:
* Cell geometry
* Topology between cells
* Cell semantics
* Multilayered space model

### Cell Geometry

A 2D surface or 3D solid, defined by one of 3 options:
* No spatial information, only topology
* Spatial and topology
* Only topology, with reference to spatial data sets

### Topology between cells

Important for navigation is the spatial relationship between cells. The connection of cells via doors is given via a dual topological graph. The nodes represent rooms, the edges represent doors. Several other attributes may be derived from these like accessibility or travel time between cells.

### Cell Semantics

Given that all spaces have different functions, the semantics of cells need to be specified. This includes different applications like indoor facility management. It may also be useful to include a cell boundary as a semantic.

### Multilayered Space Model

A space can and needs to be interpreted by different specifications of usage. Therefore a mechanism to include multiple layers for the same space must exist, called interpretations. Each one corresponds to a cellular space layer with its own geometric and topological properties. For example, the topology of a space might be different from the walking and wheelchair interpretation as they are partitioned differently.
