.. _ead_item_types_prav_zprac:

===================================================================
Pravidla zpracování jednotky popisu
===================================================================

Další popis viz:

 - ZP 4.7.2 Pravidla zpracování jednotky popisu
 - ISAD(G) 3.7.2 Pravidla nebo zásady


Mezinárodní, národní nebo místní pravidla a zásady, kterými se popis řídí,
se uvádějí v elementu `<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_. Na úrovni 
elementu `<processinfo> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-processinfo>`_
se povinně uvádí atribut ``localtype="RULES"``.


.. code-block:: xml
  :caption: Příklad zápisu pravidel zpracování jednotky popisu

  <ead:processinfo localtype="RULES">
    <ead:p>Dle Základní pravidla pro zpracování archiválií, vydání 2022.</ead:p>
  </ead:processinfo>
