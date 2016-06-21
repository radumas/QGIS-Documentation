.. index:: Work_with_Attribute_Table
.. _sec_attribute_table:

**********************************
 Working with the Attribute Table
**********************************

.. contents::
   :local:

The :index:`attribute table` displays features of a selected layer. Each row
in the table represents one map feature, and each column contains a particular
piece of information about the feature. Features in the table can be searched,
selected, moved or even edited.

To open the attribute table for a vector layer, make the layer active by
clicking on it in the map legend area. Then, from the main
:menuselection:`Layer` menu, choose |openTable| :menuselection:`Open Attribute
Table`. It is also possible to right click on the layer and choose
|openTable| :menuselection:`Open Attribute Table` from the drop-down menu,
and to click on the |openTable| :guilabel:`Open Attribute Table` button
in the Attributes toolbar.

This will open a new window that displays the feature attributes for the
layer (figure_attributes_1_). The number of features and the number of
selected features are shown in the attribute table title.

.. _figure_attributes_1:

.. only:: html

   **Figure Attributes 1:**

.. figure:: /static/user_manual/working_with_vector/vectorAttributeTable.png
   :align: center

   Attribute Table for regions layer

The buttons at the top of the attribute table window provide the
following functionality:

* |toggleEditing| :sup:`Toggle editing mode` to enable editing functionalities
  (also with :kbd:`Ctrl+e`)
* |saveEdits| :sup:`Save Edits` (also with :kbd:`Ctrl+s`)
* |draw| :sup:`Reload the table`
* |newTableRow| :sup:`Add feature`
* |deleteSelected| :sup:`Delete selected features` (also with
  :kbd:`Ctrl+d`)
* |expressionSelect| :sup:`Select features using an Expression`
* |selectAll| :sup:`Select all` (also with :kbd:`Ctrl+a`)
* |invertSelection| :sup:`Invert selection` (also with :kbd:`Ctrl+r`)
* |unselectAttributes| :sup:`Unselect all` (also with :kbd:`Ctrl+u`)
* |selectedToTop| :sup:`Move selected to top` (also with :kbd:`Ctrl+t`)
* |panToSelected| :sup:`Pan map to the selected rows` (also with :kbd:`Ctrl+p`)
* |zoomToSelected| :sup:`Zoom map to the selected rows` (also with
  :kbd:`Ctrl+j`)
* |copySelected| :sup:`Copy selected rows to clipboard` (also with
  :kbd:`Ctrl+c`)
* |editPaste| :sup:`Paste from clipboard to a new row` (also with
  :kbd:`Ctrl+v`)
* |deleteAttribute| :sup:`Delete Column` for PostGIS layers and for OGR
  layers with GDAL version >= 1.9 (also with :kbd:`Ctrl+l`)
* |newAttribute| :sup:`New Column` for PostGIS layers and for OGR
  layers with GDAL version >= 1.6 (also with :kbd:`Ctrl+w`)
* |calculateField| :sup:`Open field calculator` (also with :kbd:`Ctrl+i`)

Below these buttons is the Field Calculator bar (enabled only in editing mode),
which allows calculations to be quickly applied to either all or selected features
attributes in the table. This bar uses the same expressions as the |calculateField|
:sup:`Field Calculator` (see :ref:`vector_field_calculator`).

.. tip:: **Skip WKT geometry**

   If you want to use attribute data in external programs (such as Excel), use the
   |copySelected| :sup:`Copy selected rows to clipboard` button.
   You can copy the information without vector geometries if you deactivate
   :menuselection:`Settings --> Options -->` Data sources menu |checkbox|
   :guilabel:`Copy geometry in WKT representation from attribute table`.


.. index:: Attribute_Table_Selection

Selecting features in an attribute table
=========================================

**Each selected row** in the attribute table displays the attributes of a
selected feature in the layer. If the set of features selected in the main
window is changed, the selection is also updated in the attribute table.
Likewise, if the set of rows selected in the attribute table is changed, the
set of features selected in the main window will be updated.

Rows can be selected by clicking on the row number on the left side of the
row. **Multiple rows** can be marked by holding the :kbd:`Ctrl` key.
A **continuous selection** can be made by holding the :kbd:`Shift` key and
clicking on several row headers on the left side of the rows. All rows
between the current cursor position and the clicked row are selected.
Moving the cursor position in the attribute table, by clicking a cell in the
table, does not change the row selection. Changing the selection in the main
canvas does not move the cursor position in the attribute table.

The table can be sorted by any column, by clicking on the column header. A
small arrow indicates the sort order (downward pointing means descending
values from the top row down, upward pointing means ascending values from
the top row down).

For a **simple search by attributes** on only one column, choose the
:menuselection:`Column filter -->` from the menu in the bottom left corner.
Select the field (column) on which the search should be
performed from the drop-down menu, and hit the **[Apply]** button. Then, only
the matching features are shown in the attribute table.

To make a selection, you have to use the |expressionSelect| :sup:`Select features using an Expression`
icon on top of the attribute table.
|expressionSelect| :sup:`Select features using an Expression` allows you
to define a subset of a table using a :guilabel:`Function List` like in the
|calculateField| :sup:`Field Calculator` (see :ref:`vector_field_calculator`).
The query result can then be saved as a new vector layer.
For example, if you want to find regions that are boroughs from :file:`regions.shp`
of the QGIS sample data, you have to open the :guilabel:`Fields and Values` menu
and choose the field that you want to query. Double-click the field 'TYPE_2' and also
**[Load all unique values]** . From the list, choose and double-click 'Borough'.
In the :guilabel:`Expression` field, the following query appears:

::

 "TYPE_2"  =  'Borough'

Here you can also use the :menuselection:`Function list --> Recent (Selection)` to
make a selection that you used before. The expression builder remembers the last 20
used expressions.

The matching rows will be selected, and the total number of matching rows will
appear in the title bar of the attribute table, as well as in the status bar of
the main window. For searches that display only selected features on the map,
use the Query Builder described in section :ref:`vector_query_builder`.

To show selected records only, use :guilabel:`Show Selected Features` from the menu
at the bottom left. See next section for more information on filter feature.

The field calculator bar allows you to make calculations on the selected rows only.
For example, you can alter the number of the ID field of the layer :file:`regions.shp`
with the expression

::

 ID+5

as shown in figure_attributes_1_ .

Filter features
===============

At the bottom of the attribute table, you have a dropdown list of different
filter:

* Show All Features;
* Show Selected Features;
* Show Features visible on map;
* Show Edited and New Features;
* Field Filter;
* Advanced filter (Expression);

The first four are self explanatory, the two last are expression filters. Field
Filter allows user to choose a column name in the list and add a simple form to
the right of the drop-down list to filter with a *like* expression parameter.
This filter will create an expression filter as an :guilabel:`Advanced filter`.
The last kind of filter will open an expression window, see :ref:`vector_expressions`
for more information.


Tab/form mode
=============

By default the attribute window displays a table layout. In some case one
should prefer to use a form layout to help edit some features more easily.

You can switch to form layout by clicking in the bottom right, on |openForm|
and switch back to table layout with |openTable|.

Zoom to feature
===============

To zoom into a feature, without having to select it, right-click on the feature
you want to zoom in, within the attribute table, and select :guilabel:`Zoom to feature`.

Save selected features as new layer
===================================

The selected features can be saved as any OGR-supported vector format and
also transformed into another coordinate reference system (CRS). Just open
the right mouse menu of the layer and click on :menuselection:`Save
as` to define the name of the output file, its format and CRS (see section
:ref:`label_legend`). To save the selection ensure that the |checkbox|
:menuselection:`Save only selected features` is selected.
It is also possible to specify OGR creation options within the dialog.

.. _paste_into_layer:

Paste into new layer
=====================

Features that are on the clipboard may be pasted into a new
layer.  To do this, first make a layer editable.  Select some features, copy them to the
clipboard, and then paste them into a new layer using
:menuselection:`Edit --> Paste Features as` and choosing
:menuselection:`New vector layer` or :menuselection:`New memory
layer`.

This applies to features selected and copied within QGIS and
also to features from another source defined using well-known text (WKT).

.. index:: Field_Calculator, Calculator_Field, Derived_Fields

.. _calculate_fields_values:

Editing attribute values
=========================

.. contents::
   :local:

The |calculateField| :sup:`Field Calculator` button in the attribute
table allows you to perform calculations on the basis of existing attribute values or
defined functions, for instance, to calculate length or area of geometry features. The
results can be written to a new attribute field, a virtual field, or
they can be used to update values in an existing field.

A :index:`virtual field` is a field based on an expression calculated on the fly,
meaning that its value is automatically updated as soon as the underlying parameter
changes. The expression is set once; you no longer need to recalculate the field
each time underlying values change.
For example, you may want to use a virtual field if you need area to be evaluated
as you digitize features or to automatically calculate a duration between dates
that may change (e.g., using ``now()`` function).

.. note:: **Use of Virtual Fields**

   * Virtual fields are not permanent in the layer attributes, meaning that
     they're only saved and available in the project file they've been created.
   * A field can be set virtual only at its creation and the expression used
     can't be changed later: you'll need to delete and recreate that field.

The :index:`field calculator` is available on any layer that supports edit.
When you click on the field calculator icon the dialog opens (see
figure_attributes_2_). If the layer is not in edit mode, a warning is
displayed and using the field calculator will cause the layer to be put in
edit mode before the calculation is made.

The quick field calculation bar on top of the attribute table is only
visible if the layer is in edit mode.

In quick field :index:`calculation bar`, you first select the existing field name
then open the expression dialog to create your expression or write it directly
in the field then click on **[Update All]**, **[Update Selected]** or
**[Update Filtered]** button according to your need.

.. _vector_field_calculator:

Field Calculator
----------------

Based on the :ref:`Expression Builder <functions_list>` dialog, the field calculator
dialog offers a complete interface to define an expression and apply it to an
existing or a newly created field.
To use the field calculator dialog, you first must select whether you want to only
update selected features, create a new attribute field where the results of the
calculation will be added or update an existing field.

.. _figure_attributes_2:

.. only:: html

   **Figure Attributes 2:**

.. figure:: /static/user_manual/working_with_vector/fieldcalculator.png
   :align: center

   Field Calculator

If you choose to add a new field, you need to enter a field name, a field type
(integer, real or string), the total field width, and the field precision (see
figure_attributes_2_). For example, if you choose a field width of 10 and a field
precision of 3, it means you have 6 digits before the dot, then the dot and another
3 digits for the precision.

A short example illustrates how field calculator works when using the
:guilabel:`Expression` tab. We want to calculate the length in km of the
``railroads`` layer from the QGIS sample dataset:

#. Load the shapefile :file:`railroads.shp` in QGIS and press |openTable|
   :sup:`Open Attribute Table`.
#. Click on |toggleEditing| :sup:`Toggle editing mode` and open the
   |calculateField| :sup:`Field Calculator` dialog.
#. Select the |checkbox| :guilabel:`Create a new field` checkbox to save the
   calculations into a new field.
#. Add ``length`` as Output field name and ``real`` as Output field type, and
   define Output field width to be 10 and Precision, 3.
#. Now double click on function ``$length`` in the :guilabel:`Geometry` group
   to add it into the Field calculator expression box.
#. Complete the expression by typing ``/ 1000`` in the Field calculator
   expression box and click **[Ok]**.
#. You can now find a new field ``length`` in the attribute table.


.. index:: Non_Spatial_Attribute_Tables

Working with non spatial attribute tables
=========================================

QGIS allows you also to load non-spatial tables. This currently includes tables
supported by OGR and delimited text, as well as the PostgreSQL, MSSQL and Oracle provider.
The tables can be used for field lookups or just generally browsed and edited using the table
view. When you load the table, you will see it in the legend field. It can be
opened with the |openTable| :sup:`Open Attribute Table` tool and
is then editable like any other layer attribute table.

As an example, you can use columns of the non-spatial table to define attribute
values, or a range of values that are allowed, to be added to a specific vector
layer during digitizing. Have a closer look at the edit widget in section
:ref:`vector_attributes_menu` to find out more.


.. index:: conditional_formatting

Conditional formatting of Table Cells
=====================================

You can enable the :index:`conditional formatting` panel clicking on
|rendererAttributeTable| at the top right of the attributes window in table
view (not available in form view).

The new panel allows user to add new rules for conditional formatting of field
or full row in regard of the expression on field. Adding new rule open a form
to define:

* the name of the rule,
* a condition from expression window,
* a preset formatting
* some other parameters to improve, change or setup the formatting:

  * background and text colors,
  * use of icon,
  * bold, italic underline, or strikeout,
  * text field,
  * font.

.. _figure_attributes_3:

.. only:: html

   **Figure Attributes 3:**

.. figure:: /static/user_manual/working_with_vector/attribute_table_conditional_formating.png
   :align: center

   Conditional Formatting of an attribute table


.. index:: Relations
.. _vector_relations:

Creating one to many relations
==============================

Relations are a technique often used in databases. The concept is, that
features (rows) of different layers (tables) can belong to each other.

As an example you have a layer with all regions of alaska (polygon)
which provides some attributes about its name and region type and a
unique id (which acts as primary key).

Foreign keys
-------------

Then you get another point layer or table with information about airports
that are located in the regions and you also want to keep track of these. If
you want to add them to the region layer, you need to create a one to many
relation using foreign keys, because there are several airports in most regions.

.. _figure_relations_1:

.. only:: html

   **Figure Relations 1:**

.. figure:: /static/user_manual/working_with_vector/relations1.png
   :align: center

   Alaska region with airports

In addition to the already existing attributes in the airports attribute table
another field fk_region which acts as a foreign key (if you have a database, you will
probably want to define a constraint on it).

This field fk_region will always contain an id of a region. It can be seen
like a pointer to the region it belongs to. And you can design a custom edit
form for the editing and QGIS takes care about the setup. It works with different
providers (so you can also use it with shape and csv files) and all you have
to do is to tell QGIS the relations between your tables.

Layers
-------

QGIS makes no difference between a table and a vector layer. Basically, a vector
layer is a table with a geometry. So can add your table as a vector layer. To
demonstrate you can load the 'region' shapefile (with geometries) and the 'airport'
csv table (without geometries) and a foreign key (fk_region) to the layer
region. This means, that each airport belongs to exactly one region while each
region can have any number of airports (a typical one to many relation).


Definition (Relation Manager)
------------------------------

The first thing we are going to do is to let QGIS know about the relations between the layer.
This is done in :menuselection:`Project --> Project Properties`.
Open the :guilabel:`Relations` menu and click on :guilabel:`Add`.

* **name** is going to be used as a title. It should be a human readable string,
  describing, what the relation is used for. We will just call say "Airports" in this case.
* **referencing layer** is the one with the foreign key field on it. In our case
  this is the airports layer
* **referencing field** will say, which field points to the other layer so this
  is fk_region in this case
* **referenced layer** is the one with the primary key, pointed to, so here it
  is the regions layer
* **referenced field** is the primary key of the referenced layer so it is ID
* **id** will be used for internal purposes and has to be unique. You may need
  it to build custom forms once this is supported. If you leave it empty, one
  will be generated for you but you can assign one yourself to get one that is
  easier to handle.

.. _figure_relations_2:

.. only:: html

   **Figure Relations 2:**

.. figure:: /static/user_manual/working_with_vector/relations2.png
   :align: center

   Relation Manager


Forms
-----

Now that QGIS knows about the relation, it will be used to improve the
forms it generates. As we did not change the default form method (autogenerated)
it will just add a new widget in our form. So let's select the layer region in
the legend and use the identify tool. Depending on your settings, the form might
open directly or you will have to choose to open it in the identification dialog
under actions.

.. _figure_relations_3:

.. only:: html

   **Figure Relations 3:**

.. figure:: /static/user_manual/working_with_vector/relations3.png
   :align: center

   Identification dialog regions with relation to airports

As you can see, the airports assigned to this particular region are all shown in a
table. And there are also some buttons available. Let's review them shortly

* The |toggleEditing| button is for toggling the edit mode. Be aware that it
  toggles the edit mode of the airport layer, although we are in the feature
  form of a feature from the region layer. But the table is representing features
  of the airport layer.
* The |signPlus| button will add a new feature to the airport layer. And it will
  assign the new airport to the current region by default.
* The |remove| button will delete the selected airport permanently.
* The |link| symbol will open a new dialog where you can select any existing
  airport which will then be assigned to the current region. This may be handy
  if you created the airport on the wrong region by accident.
* The |unlink| symbol will unlink the selected airport from the current region,
  leaving them unassigned (the foreign key is set to NULL) effectively.
* The two buttons to the right switch between table view and form view where
  the later let's you view all the airports in their respective form.

If you work on the airport table, a new widget type is available which lets you
embed the feature form of the referenced region on the feature form of the airports.
It can be used when you open the layer properties of the airports table, switch to
the :menuselection:`Fields` menu and change the widget type of the foreign key
field 'fk_region' to Relation Reference.

If you look at the feature dialog now, you will see, that the form of the region
is embedded inside the airports form and will even have a combobox, which allows you
to assign the current airport to another region.

.. _figure_relations_4:

.. only:: html

   **Figure Relations 4:**

.. figure:: /static/user_manual/working_with_vector/relations4.png
   :align: center

   Identification dialog airport with relation to regions