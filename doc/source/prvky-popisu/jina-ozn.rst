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

Pro jiné identifikátory se použije konstanta ``JINE`` a v popisu se uvede jeho význam.

Příklad:

.. code-block:: xml

  <ead:unitid localtype="CISLO_JEDNACI" 
     label="číslo jednací">2022/34-2</ead:unitid>



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
     - ``referenční označení``
   * - :ref:`ead_item_types_unitid_porc`
     - ``PORADOVE_CISLO``
     - ``pořadové číslo``
   * - :ref:`ead_item_types_inv_cislo`
     - ``INV_CISLO``
     - ``inventární číslo``
   * - Signatura přidělená původcem
     - ``SIGNATURA_PUVODNI``
     - ``signatura přidělená původcem``
   * - Signatura přidělená při zpracování archiválie
     - ``SIGNATURA_ZPRACOVANI``
     - ``signatura přidělená při zpracování archiválie``
   * - Ukládací znak / spisový znak
     - ``UKLADACI_ZNAK``
     - ``ukládací znak / spisový znak``
   * - Číslo jednací
     - ``CISLO_JEDNACI``
     - ``číslo jednací``
   * - Spisová značka
     - ``SPISOVA_ZNACKA``
     - ``spisová značka``
   * - Číslo vložky úřední knihy
     - ``CISLO_VLOZKY``
     - ``číslo vložky úřední knihy``
   * - Přírůstkové číslo
     - ``CISLO_PRIRUSTKOVE``
     - ``přírůstkové číslo``
   * - Neplatné pořadové číslo manipulačního seznamu
     - ``NEPL_PORADOVE_CISLO``
     - ``neplatné pořadové číslo manipulačního seznamu``
   * - Neplatné inventární číslo
     - ``NEPL_INV_CISLO``
     - ``neplatné inventární číslo``
   * - Signatura přidělená při předchozím zpracování
     - ``NEPL_SIGNATURA_ZPRACOVANI``
     - ``signatura přidělená při předchozím zpracování``
   * - Neplatné referenční označení
     - ``NEPL_REFERENCNI_OZNACENI``
     - ``neplatné referenční označení``
   * - Číslo pohlednice nakladatelství Orbis
     - ``NAKL_CISLO``
     - ``číslo pohlednice nakladatelství Orbis``
   * - Číslo negativu
     - ``CISLO_NEGATIVU``
     - ``číslo negativu``
   * - Číslo produkce CD
     - ``CISLO_PRODUKCE``
     - ``číslo produkce CD``
   * - Kód ISBN
     - ``KOD_ISBN``
     - ``kód ISBN``
   * - Kód ISSN
     - ``KOD_ISSN``
     - ``kód ISSN``
   * - Kód ISMN
     - ``KOD_ISMN``
     - ``kód ISMN``
   * - Matriční číslo (propůjčeného vyznamenání)
     - ``MATRICNI_CISLO``
     - ``matriční číslo (propůjčeného vyznamenání)``
   * - Jiný identifikátor
     - ``JINE``
     - ``jiné``
