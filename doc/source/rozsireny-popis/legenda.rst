.. _ead_item_types_legend:

===================================================
Legenda, opis, nápis, exerque
===================================================

Další popis viz:

 - ZP 5.7.1 Opis, nápis, exerque
 - ZP 5.11.1 Legenda

Uvádí se v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="LEGEND"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot.

V elementu se uvádí textová hodnota.

Příklad
===========

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localtype="LEGEND">praenomen et nomen</ead:physfacet>
   </ead:physdescstructured>
