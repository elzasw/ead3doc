.. _ead_item_types_corroboratio:

=============================================================
Koroborace dokumentu, k němuž byl popisovaný otisk připojen
=============================================================

Další popis viz: ZP 5.7.3 Koroborace dokumentu, k němuž byl popisovaný otisk připojen

Uvádí se v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="CORROBORATIO"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 

V elementu se uvádí textová hodnota.

Příklad
===========

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>lio</ead:unittype>
     <ead:physfacet localtype="CORROBORATIO">Tomu na svědomí pečeť naší královsku kázali sme přivěsiti k tomuto listu.</ead:physfacet>
   </ead:physdescstructured>

