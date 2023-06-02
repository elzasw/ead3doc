.. _ead_item_types_poradi_otisku:

=============================================================
Pořadí otisku
=============================================================

Další popis viz: ZP 5.7.5 Pořadí otisku

Uvádí se v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="IMPRINT_ORDER"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 

V elementu se uvádí textová hodnota.

Příklad
===========

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>otd</ead:unittype>
     <ead:physfacet localtype="IMPRINT_ORDER">6. ze 17</ead:physfacet>
   </ead:physdescstructured>

