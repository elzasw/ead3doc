.. _ead_item_types_technika:

===================================================
Technika, adjustace, nosič a látka záznamu
===================================================

Další popis viz: ZP5.2.8 Technika, adjustace, nosič a látka záznamu

Uvádí se v elementu `<physfacet> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="TECHNIQUE"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot.

V elementu se uvádí jen textová hodnota.

Příklad
===========

Neuvedený druh jednotlivosti napsaný na stroji (strojopis):


.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localType="TECHNIQUE">strojopis</ead:physfacet>
   </ead:physdescstructured>
