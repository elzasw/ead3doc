.. _ead_item_types_meritko:

===================================================
Měřítko
===================================================

Další popis viz: ZP5.2.5 Měřítko

Měřítko se uvádí v elementu `<materialspec> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-materialspec>`_
s uvedeným atributem ``localtype="SCALE"``. Měřítko se zapisuje jako prostý text.


Příklad
===========

Uvedení měřítka mapy 1:200


.. code-block:: xml

   <ead:did>
     <ead:materialspec localtype="SCALE">1:200</ead:materialspec>
   </ead:did>
