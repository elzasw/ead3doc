.. _ead_item_types_phystech:

=========================================================
Fyzický stav jednotky popisu a technické požadavky
=========================================================

Další popis viz:

 - ZP 4.4.4 Fyzický stav jednotky popisu a technické požadavky
 - ISAD(G) 3.4.4

Fyzický stav jednotky popisu a technické požadavky se uvádí v elementu 
`<phystech> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-phystech>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.
Fyzický stav se zapisuje jako prostý text.


.. code-block:: xml
   :caption: Příklad zápisu fyzického stavu jednotky popisu

   <ead:phystech>
     <ead:p>...stav...</ead:p>
   </ead:phystech>

