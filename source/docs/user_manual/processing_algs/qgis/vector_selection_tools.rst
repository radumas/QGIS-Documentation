.. only:: html

   |updatedisclaimer|

Vector selection
================

.. only:: html

   .. contents::
      :local:
      :depth: 1

Extract by attribute
--------------------

Description
...........

Creates new vector layer that only contains certain features from an input layer.
The criteria for adding features to the resulting layer is defined based on
the values of an attribute from the input layer.

Parameters
..........

``Input Layer`` [vector: any]
  <put parameter description here>

``Selection attribute`` [tablefield: any]
  <put parameter description here>

``Operator`` [selection]
  <put parameter description here>

  Options:

  * 0 --- =
  * 1 --- !=
  * 2 --- >
  * 3 --- >=
  * 4 --- <
  * 5 --- <=
  * 6 --- begins with
  * 7 --- contains

  Default: *0*

``Value`` [string]
  <put parameter description here>

  Default: *(not set)*

Outputs
.......

``Extracted (attribute)`` [vector]
  <put output description here>

Console usage
.............

::

  processing.runalg('qgis:extractbyattribute', input, field, operator, value, output)

See also
........

Extract by location
-------------------

Description
...........

Creates new vector layer that only contains certain features from an input layer.
The criteria for adding features to the resulting layer is defined based on
the spatial relationship between each feature and the features in an additional layer.

Parameters
..........

``Layer to select from`` [vector: any]
  <put parameter description here>

``Additional layer (intersection layer)`` [vector: any]
  <put parameter description here>

``Predicate`` [array of Unicode strings]
  Condition for the selection. Array of one or more of the following predicates:

  * disjoint
  * intersects
  * contains
  * equals
  * touches
  * overlaps
  * within
  * crosses

  For console usage the predicates must be defined as an array of Unicode
  strings, eg. [u'intersects',u'contains']

``Precision`` [number]
  <put parameter description here>
  
Outputs
.......

``Extracted (location)``
  <put output description here>

Console usage
.............

::

  processing.runalg('qgis:extractbylocation', input, intersect, predicates, precision, output)

See also
........

Random extract
--------------

Description
...........

Takes a vector layer and generates a new one that contains only a subset of the features in the input layer.
The subset is defined randomly, using a percentage or count value to define the total number of features in the subset.

Parameters
..........

``Input layer`` [vector: any]
  <put parameter description here>

``Method`` [selection]
  <put parameter description here>

  Options:

  * 0 --- Number of selected features
  * 1 --- Percentage of selected features

  Default: *0*

``Number/percentage of selected features`` [number]
  <put parameter description here>

  Default: *10*

Outputs
.......

``Extracted (random)`` [vector]
  <put output description here>

Console usage
.............

::

  processing.runalg('qgis:randomextract', input, method, number, output)

See also
........

Random extract within subsets
-----------------------------

Description
...........

Takes a vector layer and generates a new one that contains only a subset of the features in the input layer.
The subset is defined randomly, using a percentage or count value to define the total number of features in the subset.
The percentage/count value is not applied to the whole layer, but instead to each category.
Categories are defined according to a given attribute, which is also specified as an input parameter for the algorithm.

Parameters
..........

``Input layer`` [vector: any]
  <put parameter description here>

``ID Field`` [tablefield: any]
  <put parameter description here>

``Method`` [selection]
  <put parameter description here>

  Options:

  * 0 --- Number of selected features
  * 1 --- Percentage of selected features

  Default: *0*

``Number/percentage of selected features`` [number]
  <put parameter description here>

  Default: *10*

Outputs
.......

````Extracted (random stratified)`` [vector]
  <put output description here>

Console usage
.............

::

  processing.runalg('qgis:randomextractwithinsubsets', input, field, method, number, output)

See also
........

Random selection
----------------

Description
...........

Takes a vector layer and selects a subset of its features. No new layer is generated by this algorithm.
The subset is defined randomly, using a percentage or count value to define the total number of
features in the subset.

Parameters
..........

``Input layer`` [vector: any]
  <put parameter description here>

``Method`` [selection]
  <put parameter description here>

  Options:

  * 0 --- Number of selected features
  * 1 --- Percentage of selected features

  Default: *0*

``Number/percentage of selected features`` [number]
  <put parameter description here>

  Default: *10*

Outputs
.......

Same vector input layer with selected features

Console usage
.............

::

  processing.runalg('qgis:randomselection', input, method, number)

See also
........

Random selection within subsets
-------------------------------

Description
...........

Takes a vector layer and selects a subset of its features. No new layer is generated by this algorithm.
The subset is defined randomly, using a percentage or count value to define the total number of features in the subset.
The percentage/count value is not applied to the whole layer, but instead to each category.
Categories are defined according to a given attribute, which is also specified as an input parameter for the algorithm.

Parameters
..........

``Input layer`` [vector: any]
  <put parameter description here>

``ID Field`` [tablefield: any]
  <put parameter description here>

``Method`` [selection]
  <put parameter description here>

  Options:

  * 0 --- Number of selected features
  * 1 --- Percentage of selected features

  Default: *0*

``Number/percentage of selected features`` [number]
  <put parameter description here>

  Default: *10*

Outputs
.......

Same vector input layer with selected features

Console usage
.............

::

  processing.runalg('qgis:randomselectionwithinsubsets', input, field, method, number)

See also
........

Remove null geometries
----------------------

Description
...........

Removes any features which do not have a geometry from a vector layer.
All other features will be copied unchanged.

Parameters
..........

``Input layer`` [vector: any]
  <put parameter description here>

Outputs
.......

``Selection`` [vector]
  <put output description here>

Console usage
.............

::

  processing.runalg('qgis:removenullgeometries', input, output)

See also
........

Select by attribute
-------------------

Description
...........

Creates a selection in a vector layer. The criteria for selected features is defined
based on the values of an attribute from the input layer.

Parameters
..........

``Input Layer`` [vector: any]
  Layer to process.

``Selection attribute`` [tablefield: any]
  Field on which perform the selection.

``Operator`` [selection]
  Comparison operator.

  Options:

  * 0 --- =
  * 1 --- !=
  * 2 --- >
  * 3 --- >=
  * 4 --- <
  * 5 --- <=
  * 6 --- begins with
  * 7 --- contains

  Default: *0*

``Value`` [string]
  Value to compare.

  Default: *(not set)*

Outputs
.......

Same vector input layer with selected features

Console usage
.............

::

  processing.runalg('qgis:selectbyattribute', input, field, operator, value)

See also
........

Select by attribute sum
------------------------

Description
...........

<put algorithm description here>

Parameters
..........

``Input Layer`` [vector: any]
  <put parameter description here>

``Selection attribute`` [tablefield: number]
  <put parameter description here>

``Value`` [number]
  Value to compare.

  Default: *0*

Outputs
.......

``Output`` [vector]
  <put parameter description here>

Console usage
.............

::

  processing.runalg('qgis:selectbyattributesum', input, field, value)

See also
........


Select by expression
--------------------

Description
...........

Creates a selection in a vector layer. The criteria for selecting
features is based on a QGIS expression.

Parameters
..........

``Input Layer`` [vector: any]
  <put parameter description here>

``Expression`` [string]
  <put parameter description here>

  Default: *(not set)*

``Modify current selection by`` [selection]
  <put parameter description here>

  Options:

  * 0 --- creating new selection
  * 1 --- adding to current selection
  * 2 --- removing from current selection
  * 3 --- selecting within current selection

  Default: *0*

Outputs
.......

Same vector input layer with selected features

Console usage
.............

::

  processing.runalg('qgis:selectbyexpression', layername, expression, method)

See also
........

Select by location
------------------

Description
...........

Creates a selection in a vector layer. The criteria for selecting
features is based on the spatial relationship between each feature and
the features in an additional layer.

Parameters
..........

``Layer to select from`` [vector: any]
  <put parameter description here>

``Additional layer (intersection layer)`` [vector: any]
  <put parameter description here>

``Predicate`` [array of Unicode strings]
  Condition for the selection. Array of one or more of the following predicates:

  * disjoint
  * intersects
  * contains
  * equals
  * touches
  * overlaps
  * within
  * crosses

  For console usage the predicates must be defined as an array of Unicode strings,
  eg. [u'intersects',u'contains']


``Modify current selection by`` [selection]
  <put parameter description here>

  Options:

  * 0 --- creating new selection
  * 1 --- adding to current selection
  * 2 --- removing from current selection

  Default: *0*

Outputs
.......

Same vector input layer with selected features

Console usage
.............

::

  processing.runalg('qgis:selectbylocation', input, intersect, predicate, precision, method)

See also
........

