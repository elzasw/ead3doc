.. _ead_item_types_scopecontent:

==================================
Tematický popis jednotky popisu
==================================

Další popis viz: 

 - ZP 4.3.4 Tematický popis jednotky popisu
 - ISAD(G) 3.3.1 Rozsah a obsah


Informace o obsahu, časovém a geografickém rozsahu archiválií
se uvádí v elementu `<scopecontent> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-scopecontent>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.

Prvek umožňuje :ref:`ead_archdesc_multilang`.


.. code-block:: xml
  :caption: Příklad zápisu tematického popisu

  <ead:scopecontent>
    <ead:p>... tematický popis...</ead:p>
  </ead:scopecontent>
