.. _ead_item_types_prav_zprac:

===================================================================
Pravidla zpracování jednotky popisu
===================================================================

Další popis viz:

 - ZP 4.7.2 Pravidla zpracování jednotky popisu
 - ISAD(G) 3.7.2 Pravidla nebo zásady


Mezinárodní, národní nebo místní pravidla a zásady, kterými se popis řídí,
se uvádějí v elementu :ead-el:`processinfo`
s vnořeným jedním elementem :ead-el:`p`. Na úrovni 
elementu :ead-el:`processinfo` se povinně uvádí atribut ``localtype="RULES"``.


.. code-block:: xml
  :caption: Příklad zápisu pravidel zpracování jednotky popisu

  <ead:processinfo localtype="RULES">
    <ead:p>Základní pravidla pro zpracování archiválií, vydání 2022.</ead:p>
  </ead:processinfo>
