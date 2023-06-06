.. _ead_item_types_ex_kopii:

===========================================
Existence kopií jednotky popisu
===========================================

Další popis viz: ZP 4.5.3 Existence kopií jednotky popisu

Informace o existenci kopií jednotek popisu se zachycuje pomocí 
elementu `<altformavail> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-altformavail>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.


Uplatnění :ref:`dědičnosti <ead_item_types_inheritance>` je zaznamenáno pomocí 
atributu `altrender="inherited"` na úrovni elementu `altformavail <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-altformavail>`_.


.. code-block:: xml
  :caption: Příklad zápisu kopií jednotky popisu

  <ead:altformavail altrender="inherited">
    <ead:p>Mikrofilm č. 452</ead:p>
  </ead:altformavail>
