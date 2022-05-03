.. _ead_item_types_datum_zprac:

===================================================================
Datum (data) popisu
===================================================================

Další popis viz:

 - ZP 4.7.3 Datum (data) popisu
 - ISAD 3.7.3 Datum (data) popisů


Datum (data) vytvoření nebo revize popisu se uvádí v elementu 
`<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_. Na úrovni 
elementu `<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
se povinně uvádí atribut ``localtype="DESCRIPTION_DATE"``.


Příklad
=============


.. code-block:: xml

  <ead:processinfo localtype="DESCRIPTION_DATE">
    <ead:p>1998, revize 2004</ead:p>
  </ead:processinfo>
