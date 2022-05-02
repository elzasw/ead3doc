.. _ead_item_types_popisobr:

===================================================
Popis obrazu v poli typáře či otisku
===================================================

Další popis viz: ZP5.7.2 Popis obrazu v poli typáře či otisku

Uvádí se v elementu `<physfacet> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="IMPRINT_IMAGE"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 

V elementu se uvádí textová hodnota.

Příklad
===========

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localtype="IMPRINT_IMAGE">sv. Ignác s metlou</ead:physfacet>
   </ead:physdescstructured>
