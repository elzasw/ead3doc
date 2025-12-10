.. _ead_faintro:

========================================
Uložení úvodu a prvků popisu tiráže
========================================

Úvod, úvodní list a tiráž archivní pomůcky jsou tvořeny
prvky popisu. Jejich hodnoty jsou primárně zachyceny v části
:ref:`ead_control`. Primárně se uvádí v případě, že je v souvoru uložena archivní pomůcka.

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
a vnořeném elementu `<ead:name localtype="FINDING_AID_APPROVED_BY">`.
Atribut ``localtype="FINDING_AID_APPROVED_BY"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
     <!-- Schválil archivni pomucku -->
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
    <!-- Datum a misto vydani  --> 
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

Datum k němuž jsou archiválie popsány je v samostatném bloku ``<ead:date>``.
Atribut ``localtype="FINDING_AID_DATE"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Datum zachyceneho stavu --> 
    <ead:date localtype="FINDING_AID_DATE">1.4.2020</ead:date>
    ...
 </ead:publicationstmt>


.. _ead_faintro_faeditor:

Archivní pomůcku sestavil
---------------------------

Kdo archivní pomůcku sestavil je uložen v samostatném bloku ``<ead:p>``
a vnořeném elementu `<ead:name localtype="FINDING_AID_EDITOR">`.
Atribut ``localtype="FINDING_AID_EDITOR"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Sestavovatel/editor archivni pomucky --> 
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
Podrobněji viz :ref:`ead_ap`.

Atribut ``localtype="ORIGINATOR"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Celý blok ``<ead:p>`` je opakovatelný a uvede se samostatně pro každého původce.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Puvodce v uvodu archivni pomucky -->
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
a vnořeném elementu ``<ead:name localtype="ARRANGER">``.
Podrobněji viz :ref:`ead_ap`.

Atribut ``localtype="ARRANGER"`` se uvádí povinně a slouží 
pro odlišení od dalších hodnot.

Celý blok ``<ead:p>`` je opakovatelný a uvede se samostatně pro každého zpracovatele.

.. code-block:: xml

 <ead:publicationstmt>
    ...
    <!-- Zpracovatel v uvodu archivni pomucky --> 
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
    <!-- Zpracovatel v tirazi archivni pomucky -->
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

Rozsah zpřístupněných archiválií pomůckou se zapisuje ve strukturované
podobě pomocí prvku popisu :ref:`ead_item_types_rozsah`. Prvek je
uveden v kořenové jednotce popisu. Pro vykazování rozsahu analogových 
archiválií se jako jednotka uvádí běžné metry (``bm``), u digitálních
archiválií se jako jednotka uvádí ``byte``.


.. _ead_faintro_pocet_jp:

Počet jednotek popisu
=========================

Počet jednotek popisu, které lze na základě archivní pomůcky zpřístupnit,
se uvádí pomocí prvku popisu :ref:`ead_item_types_rozsah`.
Prvek je uveden v kořenové jednotce popisu.
