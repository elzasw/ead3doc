.. _ead_item_types_zpracovatel:

===================================================================
Zpracovatel jednotky popisu
===================================================================

Další popis viz:

 - ZP 4.7.1 Zpracovatel jednotky popisu
 - ISAD(G) 3.7.1 Poznámka zpracovatele


Informace o zpracovatelích jednotky popisu nebo autorovi popisu
se uvádí v elementu `<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_. Na úrovni 
elementu `<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
se povinně uvádí atribut ``localtype="ARCHIVIST_NOTE"``.


.. code-block:: xml
  :caption: Příklad zápisu zpracovatele jednotky popisu

  <ead:processinfo localtype="ARCHIVIST_NOTE">
    <ead:p>vypracoval v roce 1977 Pavel Brožka</ead:p>
  </ead:processinfo>
