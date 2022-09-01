.. _ead_item_types_dil:

===================================================
Díl, část, pořadí vydání jednotky popisu
===================================================

Další popis viz: ZP 5.2.9 Díl, část, pořadí vydání jednotky popisu

Hodnota se uvádí v elementu `<materialspec> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-materialspec>`_
s uvedeným atributem ``localtype="VOLUME"``. Zapisuje se jako prostý text.


Příklad
===========

Informace o vydání v rámci: Ročník XII., číslo 12.


.. code-block:: xml

   <ead:did>
     <ead:materialspec localtype="VOLUME">Ročník XII., číslo 12.</ead:materialspec>
   </ead:did>
