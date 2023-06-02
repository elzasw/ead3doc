.. _ead_item_types_rozsah:

========================
Rozsah a doba trvání
========================

Další popis viz: ZP 5.2.4 Rozměry, hmotnost, velikost, množství

Rozsah (datový, počet kusů a další) se popisuje pomocí elementu
`<physdescstructured> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physdescstructured>`_
s hodnotou atributů:

 - ``physdescstructuredtype="spaceoccupied"``
 - ``coverage="whole"``


Povinně se uvádějí podřízené elementy:

 - `<quantity> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-quantity>`_ - obsahuje množství
 - `<unittype> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittype>`_ - veličina


Rozměry se struktrurovaně popisují v prvku: :ref:`ead_item_types_rozmery_structured`.

Níže je uvedena tabulka přípustných hodnot.


.. list-table:: Tabulka jednotek pro rozsah a dobu trvání
   :widths: 20 10
   :header-rows: 1

   * - Druh informace
     - `<unittype> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittype>`_
   * - hmotnost (gramy)
     - ``g``
   * - množství (byte)
     - ``byte``
   * - množství (kusy)
     - ``pieces``
   * - množství (strany)
     - ``pages``
   * - množství (listy)
     - ``sheets``
   * - trvání
     - ``s``
   * - běžné metry (bm)
     - ``bm``
   * - jednotky popisu
     - ``desc_units``


Rozsahy *běžné metry* a *jednotky popisu* se uvádí pouze na kořeni archivního popisu 
pro zápis množství archiválií popsaných archivních pomůckou (viz :ref:`ead_faintro_rozsah_arch`),
resp. pro počet zpřístupněných jednotek popisu (viz :ref:`ead_faintro_pocet_jp`).


Příklad velikosti v byte
====================================


.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="spaceoccupied" 
                           coverage="whole">
     <ead:quantity>1024</ead:quantity>
     <ead:unittype>byte</ead:unittype>
   </ead:physdescstructured>



.. _ead_item_types_rozsah_duration:

Délka filmového a zvukového záznamu
======================================

Další popis viz: 

 - ZP 5.13.1 Délka filmového záznamu
 - ZP 5.14.1 Délka zvukového záznamu

Délka filmového a zvukového záznamu je zapsána dle 
definice zápisu :ref:`ead_item_types_rozsah`.
Doba trvání se uvádí v sekundách.


Příklad doby trvání
====================================


.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="spaceoccupied" 
                           coverage="whole">
     <ead:quantity>100</ead:quantity>
     <ead:unittype>s</ead:unittype>
   </ead:physdescstructured>
