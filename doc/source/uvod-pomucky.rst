.. _ead_faintro:

========================================
Uložení úvodu a prvků popisu tiráže
========================================

Úvod, úvodní list a tiráž archivní pomůcky jsou tvořeny
prvky popisu. Jejich hodnoty jsou primárně zachyceny v části
:ref:`ead_control`. Primárně se uvádí v případě, že je v souboru uložena archivní pomůcka.

Informace o publikaci pomůcky
===============================

Informace vztahující se k publikaci pomůcky jsou hlavně
zachyceny v elementu :ead-el:`publicationstmt`.

Element obsahuje podřízené prvky popisu zachycující:

 - :ref:`kdo archivní pomůcku schválil <ead_faintro_approvedby>`
 - :ref:`datum a místo vydání <ead_faintro_releasedateplace>`
 - :ref:`datum vyhotovení archivního popisu <ead_faintro_descdate>`
 - :ref:`datum popsaného stavu archiválií <ead_faintro_fadate>`
 - :ref:`kdo archivní pomůcku sestavil/editor <ead_faintro_faeditor>`
 - :ref:`původce archiválií <ead_faintro_originator>`
 - :ref:`zpracovatele <ead_faintro_arranger>`


.. _ead_faintro_approvedby:

Schvalovatel archivní pomůcky
-------------------------------

Schvalovatel je uložen v samostatném bloku ``<ead:p>``
a vnořeném elementu ``<ead:name localtype="FINDING_AID_APPROVED_BY">``.
Atribut ``localtype="FINDING_AID_APPROVED_BY"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Elementy ``<ead:p>``, ``<ead:name>`` a ``<ead:part>`` nejsou opakovatelné.

.. code-block:: xml

 <ead:publicationstmt>
     <!-- Schválil archivní pomůcku -->
     <ead:p>
        <ead:name localtype="FINDING_AID_APPROVED_BY">
          <ead:part>... jméno osoby ...</ead:part>
        </ead:name>
     </ead:p>
     ...
 </ead:publicationstmt>


.. _ead_faintro_releasedateplace:

Datum a místo vydání
------------------------

Datum a místo vydání archivní pomůcky jsou uloženy v samostatném bloku ``<ead:date>``.
Atribut ``localtype="RELEASE_DATE_PLACE"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Datum a místo vydání  -->
    <ead:date localtype="RELEASE_DATE_PLACE">V Praze 25.8.2020</ead:date>
    ...
 </ead:publicationstmt>


.. _ead_faintro_descdate:

Datum (data) popisu
---------------------

Datum (data) popisu jsou uložena v samostatném bloku ``<ead:date>``.
Atribut ``localtype="DESCRIPTION_DATE"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Datum (data) popisu --> 
    <ead:date localtype="DESCRIPTION_DATE">leden - květen 2020</ead:date>
    ...
 </ead:publicationstmt>


.. _ead_faintro_fadate:

Stav archivní pomůckou zpřístupněných archiválií ke dni
------------------------------------------------------------

Datum, k němuž jsou archiválie popsány, je v samostatném bloku ``<ead:date>``.
Atribut ``localtype="FINDING_AID_DATE"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Datum zachyceného stavu --> 
    <ead:date localtype="FINDING_AID_DATE">1.4.2020</ead:date>
    ...
 </ead:publicationstmt>


.. _ead_faintro_faeditor:

Archivní pomůcku sestavil
---------------------------

Kdo archivní pomůcku sestavil, je uložen v samostatném bloku ``<ead:p>``
a vnořeném elementu ``<ead:name localtype="FINDING_AID_EDITOR">``.
Atribut ``localtype="FINDING_AID_EDITOR"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Povinné pro archivní pomůcku. Element ``<ead:name>`` není opakovatelný,
ani vnořený element ``<ead:part>``.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Sestavovatel/editor archivní pomůcky --> 
    <ead:p><ead:name localtype="FINDING_AID_EDITOR">
      <ead:part>Jan Novák</ead:part>
    </ead:name></ead:p>
    ...
 </ead:publicationstmt>


.. _ead_faintro_originator:

Původce archiválií
-------------------------

Původce je uložen v samostatném bloku ``<ead:p>``
a vnořeném elementu ``<ead:name localtype="ORIGINATOR">``.
Podrobněji viz :ref:`ead_ap`. Lze užít podřízené elementy 
``ead:persname``, ``ead:famname``, ``ead:corpname`` a ``ead:name``.

Atribut ``localtype="ORIGINATOR"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Celý blok ``<ead:p>`` je opakovatelný a uvede se samostatně pro každého původce.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Původce v úvodu archivní pomůcky -->
    <ead:p>
      <ead:persname localtype="ORIGINATOR">
        <ead:part><ead:ref target="ap7523">Neruda, Jan (1834-1891)</ead:ref></ead:part>
      </ead:persname>
    </ead:p>
    ...
 </ead:publicationstmt>


.. _ead_faintro_arranger:

Zpracovatel archiválií
-------------------------

Informace o zpracovateli se obvykle uvádí ve dvou formách.
Strukturovaně v rámci úvodu a sumárně v tiráži.

Strukturovaný popis zpracovatele je uložen v samostatném bloku ``<ead:p>``
a vnořeném elementu ``<ead:persname localtype="ARRANGER">``.
Podrobněji viz :ref:`ead_ap`.

Atribut ``localtype="ARRANGER"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Celý blok ``<ead:p>`` je opakovatelný a uvede se samostatně pro každého zpracovatele.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Zpracovatel v úvodu archivní pomůcky --> 
    <ead:p>
      <ead:persname localtype="ARRANGER">
        <ead:part>
          <ead:ref target="ap84921">Berger, Adolf (1813-1886)</ead:ref>
        </ead:part>
      </ead:persname>
    </ead:p>
    ...
 </ead:publicationstmt>


Stručná textová informace o zpracovateli se zpravidla uvádí v tiráži
archivní pomůcky. Nejedná se o referenci na přístupový bod. Element není 
opakovatelný.

Atribut ``localtype="ARRANGER_BRIEF"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Zpracovatel v tiráži archivní pomůcky -->
    <ead:p>
      <ead:name localtype="ARRANGER_BRIEF">
        <ead:part>... preferované označení ...</ead:part>
      </ead:name>
    </ead:p>
    ...
 </ead:publicationstmt>

Počet evidenčních jednotek
==============================

V samostatném prvku popisu :ref:`ead_archdesc_physdescstruct` se 
uvádí počet EJ. Prvek je uveden v kořenové jednotce popisu.


.. _ead_faintro_rozsah_arch:

Rozsah zpřístupněných archiválií
==================================

Rozsah slouží k zachycení rozsahu archiválií v běžných metrech a bytech.

Celkový rozsah se uvádí pouze na kořeni archivního popisu pro zápis množství 
archiválií popsaných archivní pomůckou.

Popisuje se pomocí elementu :ead-el:`physdescstructured` s hodnotou atributů:

 - ``physdescstructuredtype="spaceoccupied"``
 - ``coverage="whole"``


Povinně se uvádějí podřízené elementy:

 - :ead-el:`quantity` - obsahuje množství, musí být uvedeno číslo, jako oddělovač desetinných míst se používá tečka
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

Množství *byte* se uvádí jen jako celé číslo. *Běžné metry* se uvádí jako celé nebo desetinné číslo.


Příklad rozsahu (bm)
------------------------------

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="spaceoccupied" 
                           coverage="whole">
     <ead:quantity>15.3</ead:quantity>
     <ead:unittype>bm</ead:unittype>
   </ead:physdescstructured>


.. _ead_faintro_pocet_jp:

Počet jednotek popisu
=========================

Počet jednotek popisu, které lze na základě archivní pomůcky zpřístupnit,
se uvádí pomocí prvku popisu :ref:`ead_item_types_rozmery_structured_quantity`.
Prvek je uveden v kořenové jednotce popisu.
