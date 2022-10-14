.. _ead_item_types_acqinfo:

========================
Přímý zdroj akvizice
========================

Další popis viz: 

 - ZP 4.3.5 Přímý zdroj akvizice
 - ISAD(G) 3.2.4 Přímý zdroj akvizice


Informace o bezprostředním zdroji příjmu archiválií, jejich výběru
se uvádí v elementu `<acqinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-acqinfo>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.


.. code-block:: xml
  :caption: Příklad zápisu přímého zdroje akvizice

  <ead:acqinfo>
    <ead:p>Písemnosti obce Braníku byly do archivu převzaty dne 20.7.1960 pod přír. č. 51/60.</ead:p>
  </ead:acqinfo>
