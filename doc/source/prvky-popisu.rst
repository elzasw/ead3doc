.. _ead_item_types:

===================================
Prvky popisu a jejich mapování
===================================

Tabulka prvků popisu a popis řešení. Prvky popisu
jsou v tabulce identifikovány kódem a názvem.
Pokud prvek popisu není v tabulce uveden, tak se nepřevádí do výstupu.

.. csv-table:: Prvky popisu
   :widths: auto
   :file: prvky-popisu/prvky-popisu.csv
   :header-rows: 1
   :delim: ,

.. _ead_item_types_container:

Ukládací jednotka
====================

Ukládací jednotka a její číslo se uloží v serializované podobě (jako jedna hodnota)
do elementu :token:`<container>`.

Další popis viz: ZP4.2.10 Ukládací jednotka a číslo

Příklad:

.. code-block:: xml

  <!-- Ukladaci jednotka -->
  <ead:container>102</ead:container>

.. _ead_item_types_unitid:

Referenční označení
=======================

Referenční označení se uloží do elementu :token:`unitid`
s uvedením atributu :token:`localtype`.

Další popis viz: ZP4.2.1 Referenční označení (pořadové číslo)

Příklad:

.. code-block:: xml

  <ead:unitid localtype="ReferencniOznaceni">1/4//1</ead:unitid>

.. _ead_item_types_unittitle:

Obsah, regest
=================

Další popis viz: ZP4.2.3 Obsah, regest

Příklad:

.. code-block:: xml

  <ead:unittitle>Evidence zemědělských pozemků</ead:unittitle>

.. _ead_item_types_unitdatestructured:

Datace vzniku jednotky popisu
==============================

Další popis viz: ZP4.2.5 Datace vzniku jednotky popisu - strojově čitelný


Pokud se jedná o odhad jsou hodnoty v atributech :token:`notbefore`, resp. 
:token:`notafter` a atribut :token:`standarddate` se nepoužije. Uvnitř 
elementů se uvádí textová reprezentace datace v čitelné podobě.

Příklad - interval 1734-1776:

.. code-block:: xml

    <ead:unitdatestructured>
    <ead:daterange>
        <ead:fromdate standarddate="1734-01-01T00:00:00">1734</ead:fromdate>
        <ead:todate standarddate="1776-12-31T23:59:59">1776</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>




.. _ead_item_types_custodhist:

Dějiny jednotky popisu
=========================

Další popis viz: ZP4.3.2 Dějiny jednotky popisu

.. code-block:: xml

  <ead:custodhist><ead:p>...dějiny...</ead:p></ead:custodhist>


.. _ead_item_types_arrangement:

Způsob uspořádání jednotky popisu
====================================

Další popis viz: ZP4.3.3 Způsob uspořádání jednotky popisu

.. code-block:: xml

   <ead:arrangement><ead:p>... způsob ...</ead:p></ead:arrangement>


.. _ead_item_types_acqinfo:

Přímý zdroj akvizice
========================

Další popis viz: ZP4.3.5 Přímý zdroj akvizice

.. code-block:: xml

  <ead:acqinfo><ead:p>... akvizice ...</ead:p></ead:acqinfo>


.. _ead_item_types_accruals:

Budoucí přírůstky
=====================

Další popis viz: ZP4.3.6 Budoucí přírůstky

.. code-block:: xml

  <ead:accruals><ead:p>...přírůstky...</ead:p></ead:accruals>


.. _ead_item_types_scopecontent:

Tematický popis jednotky popisu
==================================

Další popis viz: ZP4.3.4 Tematický popis jednotky popisu

.. code-block:: xml

  <ead:scopecontent><ead:p>... tematický popis...</ead:p></ead:scopecontent>


.. _ead_item_types_physdesc:

Fyzický stav jednotky popisu a technické požadavky
=========================================================

Další popis viz: ZP4.4.4 Fyzický stav jednotky popisu a technické požadavky


.. code-block:: xml

   <ead:physdesc>...stav...</ead:physdesc>


.. _ead_item_types_archdesc_physdescstruct:

Počet evidenčních jednotek zpřístupněných archivní pomůckou
=================================================================

Počet evidenčních jednotek zpřístupněných archivní pomůckou (uvádí se v tiráži)

Uvádí se pouze v elementu :token:`archdesc`.

.. code-block:: xml

  <!-- Evidencni jednotky -->
  <ead:physdescstructured physdescstructuredtype="materialtype">
    <ead:quantity>59</ead:quantity>
    <ead:unittype>kar</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="materialtype">
    <ead:quantity>1</ead:quantity>
    <ead:unittype>map</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="materialtype">
    <ead:quantity>7</ead:quantity>
    <ead:unittype>ppr</ead:unittype>
  </ead:physdescstructured>

.. _ead_item_types_langs:

Jazyk
=========

Další popis viz: ZP5.2.10 Jazyk

.. code-block:: xml

  <!-- Jazyky JP -->
  <ead:langmaterial>
      <ead:language langcode="ZP2015_LANGUAGE_43">čeština</ead:language>
      <ead:language langcode="ZP2015_LANGUAGE_32">latina</ead:language>
      <ead:language langcode="ZP2015_LANGUAGE_18">němčina</ead:language>
  </ead:langmaterial>
