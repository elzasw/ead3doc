.. _ead_item_types_datum_zprac:

===================================================================
Datum (data) popisu
===================================================================

Další popis viz:

 - ZP 4.7.3 Datum (data) popisu
 - ISAD(G) 3.7.3 Datum (data) popisů


Datum (data) vytvoření nebo revize popisu se uvádí v elementu 
:ead-el:`processinfo` s vnořeným jedním elementem 
:ead-el:`p`. Na úrovni elementu :ead-el:`processinfo`
se povinně uvádí atribut ``localtype="DESCRIPTION_DATE"``.


.. code-block:: xml
  :caption: Příklad uvedení datumu vzniku popisu

  <ead:processinfo localtype="DESCRIPTION_DATE">
    <ead:p>1998, revize 2004</ead:p>
  </ead:processinfo>
