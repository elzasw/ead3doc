.. _ead_item_types_pocet_otisku:

=============================================================
Počet otisků původní a současný
=============================================================

Další popis viz: ZP 5.7.4 Počet otisků původní a současný

Uvádí se v elementu :ead-el:`physfacet`
s uvedením hodnoty ``localtype="IMPRINT_COUNT"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 

V elementu se uvádí textová hodnota.

Příklad
===========

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>lio</ead:unittype>
     <ead:physfacet localtype="IMPRINT_COUNT">5?/1</ead:physfacet>
   </ead:physdescstructured>

