.. _ead_item_types_meritko:

===================================================
Měřítko
===================================================

Další popis viz: ZP 5.2.5 Měřítko

Měřítko se uvádí v elementu :ead-el:`materialspec`
s uvedeným atributem ``localtype="SCALE"``. Měřítko se zapisuje jako prostý text. 
Preferovanou poodobou je vyjádření měřítka pomocí číselné hodnoty v prvku popisu 
:ref:`ead_item_types_meritko_cislo`.



.. code-block:: xml
  :caption: Příklad uvedení měřítka mapy 1:200

   <ead:did>
     <ead:materialspec localtype="SCALE">1:200, zapsáno rukou</ead:materialspec>
   </ead:did>


.. _ead_item_types_meritko_cislo:

Číselné vyjádření měřítka
===========================

Číselné vyjádření měřítka ve tvaru 1:N, [1:N] (odhad), případně M:N, resp. [M:N] 
se zapisuje v samostatném elementu :ead-el:`materialspec`
s uvedením atributem ``localtype="SCALE_RATIO"``. Jedná se opakovatelný prvek popisu. 
Uvedený poměr musí být bezrozměrný a musí umožnit správný výpočet skutečného rozměru, 
tj. nelze uvádět hodnoty 1cm=6km jako 1:6, ale je nutné uvést 1:600000. Číselná hodnota 
se uvádí ve formátu bez mezer a jako poměr dvou celočíselných hodnot. Odhad měřítka 
se uvede v hranatých závorkách. Žádná jiná podoba měřítka v tomto elementu není povolena,
případné upřesnění hodnoty a doplňující informace se uvádí v textové části elementu.

.. code-block:: xml
  :caption: Příklad uvedení měřítka mapy 1:200

   <ead:did>
     <ead:materialspec localtype="SCALE_RATIO">1:200</ead:materialspec>
   </ead:did>


