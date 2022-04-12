.. _ead_item_types_jinaozn:

Jiná označení
=======================

Další popis viz: 4.2.2 Jiná označení

Jiná označení se uloží do elementu `<unitid> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitid>`_.
Povinně se uvádí atributy `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_ 
s konstantou uvádějící typ označení a atribut `label <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_ 
s uvedením uživatelsky čitelného popisu. Přípustné 
hodnoty jsou uvedeny v tabulce :ref:`ead_item_types_jinaozn_tab`.

Shodně s jiným označením se ukládají prvky popisu:

 - :ref:`ead_item_types_unitid`
 - :ref:`ead_item_types_unitid_porc`
 - :ref:`ead_item_types_inv_cislo`

Příklad:

.. code-block:: xml

  <ead:unitid localtype="CISLO_JEDNACI">2022/34-2</ead:unitid>



.. _ead_item_types_jinaozn_tab:

Typy označení
------------------

.. list-table:: Tabulka typů označení
   :widths: 20 10 10
   :header-rows: 1

   * - Typ označení
     - ``localtype=``
     - ``label=``
   * - :ref:`ead_item_types_unitid`
     - ``REFERENCNI_OZNACENI``
     - ``ref. ozn.``
   * - :ref:`ead_item_types_unitid_porc`
     - ``PORADOVE_CISLO``
     - ``poř. č.``
   * - :ref:`ead_item_types_inv_cislo`
     - ``INV_CISLO``
     - ``inv. č.``
   * - Signatura přidělená původcem
     - ``SIGNATURA_PUVODNI``
     - ``sign. pův.``
   * - Signatura přidělená při zpracování archiválie
     - ``SIGNATURA_ZPRACOVANI``
     - ``sign.``
   * - Ukládací znak
     - ``UKLADACI_ZNAK``
     - ``ukl. znak``
   * - Číslo jednací
     - ``CISLO_JEDNACI``
     - ``čj.``
   * - Spisová značka
     - ``SPISOVA_ZNACKA``
     - ``sp. zn.``
   * - Číslo vložky úřední knihy
     - ``CISLO_VLOZKY``
     - ``č. vl.``
   * - Přírůstkové číslo
     - ``CISLO_PRIRUSTKOVE``
     - ``č. př.``
   * - Neplatné pořadové číslo manipulačního seznamu
     - ``NEPL_PORADOVE_CISLO``
     - ``nepl. poř. č.``
   * - Neplatné inventární číslo
     - ``NEPL_INV_CISLO``
     - ``nepl. inv. č.``
   * - Signatura přidělená při předchozím zpracování
     - ``NEPL_SIGNATURA_ZPRACOVANI``
     - ``nepl. sign.``
   * - Neplatné referenční označení
     - ``NEPL_REFERENCNI_OZNACENI``
     - ``nepl. ref. ozn.``
   * - Číslo negativu
     - ``CISLO_NEGATIVU``
     - ``č. neg.``
   * - Číslo produkce CD
     - ``CISLO_PRODUKCE``
     - ``č. prod.``
   * - Kód ISBN
     - ``KOD_ISBN``
     - ``ISBN``
   * - Kód ISSN
     - ``KOD_ISSN``
     - ``ISSN``
   * - Kód ISMN
     - ``KOD_ISMN``
     - ``ISMN``
   * - Matriční číslo (propůjčeného vyznamenání)
     - ``MATRICNI_CISLO``
     - ``matr. č.``
