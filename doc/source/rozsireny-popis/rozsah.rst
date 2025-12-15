.. _ead_item_types_rozsah:

========================
Rozsah a doba trvání
========================

Další popis viz: ZP 5.2.4 Rozměry, hmotnost, velikost, množství

Část popisuje způsob uložení rozsahu (běžné metry) a doby trvání (např. zvukového záznamu).
Další související viz :ref:`ead_item_types_rozmery_structured`.


.. _ead_item_types_rozsah_bm:

Rozsah archiválií
====================
Rozsah slouží k zachycení rozsahu archiválií v běžných metrech.

Rozsahy *běžné metry* se uvádí pouze na kořeni archivního popisu 
pro zápis množství archiválií popsaných archivních pomůckou (viz :ref:`ead_faintro_rozsah_arch`).

Popisuje se pomocí elementu
:ead-el:`physdescstructured`
s hodnotou atributů:

 - ``physdescstructuredtype="spaceoccupied"``
 - ``coverage="whole"``


Povinně se uvádějí podřízené elementy:

 - :ead-el:`quantity` - obsahuje množství
 - :ead-el:`unittype` - veličina


Níže je uvedena tabulka přípustných hodnot.

.. list-table:: Tabulka jednotek pro rozsah
   :widths: 20 10
   :header-rows: 1

   * - Druh informace
     - :ead-el:`unittype`
   * - běžné metry (bm)
     - ``bm``
   * - byte
     - ``byte``


Příklad rozsahu (bm)
------------------------------

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="spaceoccupied" 
                           coverage="whole">
     <ead:quantity>15</ead:quantity>
     <ead:unittype>bm</ead:unittype>
   </ead:physdescstructured>



.. _ead_item_types_rozsah_duration:

Délka filmového a zvukového záznamu
========================================

Další popis viz: 

 - ZP 5.13.1 Délka filmového záznamu
 - ZP 5.14.1 Délka zvukového záznamu

Doba trvání se uvádí v sekundách.

Strukturovaná hodnota doby trvání se popisuje pomocí elementu
:ead-el:`physdescstructured`
s uvedením typu `otherphysdescstructuredtype="duration" <https://www.loc.gov/ead/EAD3taglib/#attr-otherphysdescstructuredtype>`_.
Povinně musí být uveden atribut ``coverage="whole"``.

Povinně se uvádějí podřízené elementy:

 - :ead-el:`quantity` - obsahuje dobu trvání
 - :ead-el:`unittype` - veličina


Níže je uvedena tabulka přípustných hodnot.

.. list-table:: Tabulka jednotek pro dobu trvání
   :widths: 20 10
   :header-rows: 1

   * - Druh informace
     - :ead-el:`unittype`
   * - trvání (sekundy)
     - ``s``


Příklad doby trvání
------------------------------

Záznam v délce 100 s.

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                           otherphysdescstructuredtype="duration"
                           coverage="whole">
     <ead:quantity>100</ead:quantity>
     <ead:unittype>s</ead:unittype>
   </ead:physdescstructured>
