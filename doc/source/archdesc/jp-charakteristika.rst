.. _ead_jp_char:

============================================
Charakteristika jednotky popisu
============================================

Charakteristikou jednotky popisu rozumíme uvedení vzájemně propojených 
významných prvků popisu a v rámci elementu 
:ead-el:`physdescstructured` s hodnotou atributů:

 - ``physdescstructuredtype="materialtype"``
 - ``coverage="whole"``

Element :ead-el:`physdescstructured` je povinný pro jednotky popisu, 
které odpovídají evidenčním jednotkám nebo jsou jednotkami popisu, 
které jsou podřízeny jednokám popisu, které odpovídají evidenčním jednotkám. 
Povinný je tedy pro složky odpovídající množstevním evidenčním jednotkám,
složky s typem evidenční jednotky (složky obsahující jednotlivosti stejného typu), 
jednotlivosti a části jednotlivosti. Povinné jsou vždy prvky popisu :ref:`druh archiválie <ead_item_types_druharch>`
(``<ead:unittype>``) a :ref:`počet archiválií <ead_item_types_pocet>` (``<ead:quantity>``).

Prvky popisu tvořící charakteristiku jednotky popisu:

 - :ref:`ead_item_types_druharch`
 - :ref:`ead_item_types_pocet`
 - :ref:`ead_item_types_technika`
 - :ref:`ead_item_types_legend`
 - :ref:`ead_item_types_popisobr`
 - :ref:`ead_item_types_corroboratio`
 - :ref:`ead_item_types_pocet_otisku`
 - :ref:`ead_item_types_poradi_otisku`
 - :ref:`ead_item_types_rozmery`
 - :ref:`ead_item_types_physdesc_expart`
