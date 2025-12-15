.. _ead_item_types_rozmery:

===================================================
Rozměry, hmotnost, velikost, množství
===================================================

Další popis viz: ZP 5.2.4 Rozměry, hmotnost, velikost, množství

Textová podoba rozměrů, hmotnosti, velikosti a množství
============================================================

Textová podoba rozměrů, hmotnosti, velikosti a množství se 
uvádí se v elementu :ead-el:`dimensions`,
který je součástí :ref:`ead_jp_char`. Element je nutné uvést v kontextu souvisejících hodnot.

Pokud jsou k dispozici strukturované hodnoty uvedených veličin, uvádí se ve strukturované podobě
v samostatných elementech, viz:

 * :ref:`ead_item_types_rozmery_structured`
 * :ref:`ead_item_types_rozmery_structured_weight`
 * :ref:`ead_item_types_rozmery_structured_quantity`


Příklad textově uvedených rozměrů
---------------------------------

Neuvedený druh jednotlivosti s textově uvedenými rozměry: 10cm x 15cm:

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:dimensions>10cm x 15cm</ead:dimensions>
   </ead:physdescstructured>


.. _ead_item_types_rozmery_structured:

Strukturovaná podoba rozměrů
================================

Strukturovaná hodnota rozměrů se popisuje pomocí jednoho nebo více zanořených elementů
:ead-el:`dimensions`.

Každý zanořený element musí obsahovat atributy:

 - druh informace - rozměr: `localtype <https://www.loc.gov/ead/EAD3taglib/#attr-localtype>`_
 - jednotka: `unit <https://www.loc.gov/ead/EAD3taglib/#attr-unit>`_
 

Uvnitř elementu se uvádí příslušná číselná hodnota ve formátu bez mezer a 
s tečkou pro oddělení desetinných míst.

Tabulka možný hodnot pro `localtype <https://www.loc.gov/ead/EAD3taglib/#attr-localtype>`_
a `unit <https://www.loc.gov/ead/EAD3taglib/#attr-unit>`_:

.. list-table:: Tabulka hodnot pro localtype a unit
   :widths: 20 10 10
   :header-rows: 1

   * - Druh informace
     - ``localtype=``
     - ``unit=``
   * - šířka
     - :token:`WIDTH`
     - ``mm``
   * - výška
     - :token:`HEIGHT`
     - ``mm``
   * - hloubka
     - :token:`DEPTH`
     - ``mm``


Příklad strukturovaných rozměrů
---------------------------------

Neuvedený druh jednotlivosti se strukturovaně uvedenými rozměry: 100mm x 150mm:

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:dimensions>
       <ead:dimensions localtype="WIDTH" unit="mm">100</ead:dimensions>
       <ead:dimensions localtype="HEIGHT" unit="mm">150</ead:dimensions>
     </ead:dimensions>
   </ead:physdescstructured>


.. _ead_item_types_rozmery_structured_weight:

Strukturovaná podoba hmotnosti
========================================================

Strukturovaná hodnota hmotnosti se popisuje pomocí elementu
:ead-el:`physdescstructured`
s uvedením typu `otherphysdescstructuredtype="weight" <https://www.loc.gov/ead/EAD3taglib/#attr-otherphysdescstructuredtype>`_.
Povinně musí být uveden atribut ``coverage="whole"``.

Povinně se uvádějí podřízené elementy:

 - :ead-el:`quantity` - obsahuje hmotnost
 - :ead-el:`unittype` - veličina


Níže je uvedena tabulka přípustných hodnot.

.. list-table:: Tabulka jednotek pro hmotnost
   :widths: 20 10
   :header-rows: 1

   * - Druh informace
     - :ead-el:`unittype`
   * - hmotnost (gramy)
     - ``g``


Příklad uvedení hmotnosti
---------------------------------

Příklad archiválie vážící 30 g.

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                           otherphysdescstructuredtype="weight"
                           coverage="whole">
     <ead:quantity>30</ead:quantity>
     <ead:unittype>g</ead:unittype>
   </ead:physdescstructured>



.. _ead_item_types_rozmery_structured_quantity:

Strukturovaná podoba množství a velikosti
========================================================

Strukturovaná hodnota množství a velikosti se popisuje pomocí elementu
:ead-el:`physdescstructured`
s uvedením typu `otherphysdescstructuredtype="quantity" <https://www.loc.gov/ead/EAD3taglib/#attr-otherphysdescstructuredtype>`_.
Povinně musí být uveden atribut ``coverage="whole"``.

Povinně se uvádějí podřízené elementy:

 - :ead-el:`quantity` - obsahuje množství
 - :ead-el:`unittype` - veličina


Níže je uvedena tabulka přípustných hodnot.

.. list-table:: Tabulka jednotek pro množství a velikost
   :widths: 20 10
   :header-rows: 1

   * - Druh informace
     - :ead-el:`unittype`
   * - množství (byte)
     - ``byte``
   * - množství (kusy)
     - ``pieces``
   * - množství (strany)
     - ``pages``
   * - množství (listy)
     - ``sheets``
   * - jednotky popisu
     - ``desc_units``


*Jednotky popisu* se uvádí pouze na kořeni archivního popisu 
pro počet zpřístupněných jednotek popisu (viz :ref:`ead_faintro_pocet_jp`).


Strukturované uvedení množství
---------------------------------

Příklad archiválie s 20 stranami.

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                           otherphysdescstructuredtype="quantity"
                           coverage="whole">
     <ead:quantity>20</ead:quantity>
     <ead:unittype>pages</ead:unittype>
   </ead:physdescstructured>


Příklad velikosti v byte
-----------------------------

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                           otherphysdescstructuredtype="quantity"
                           coverage="whole">
     <ead:quantity>1024</ead:quantity>
     <ead:unittype>byte</ead:unittype>
   </ead:physdescstructured>

