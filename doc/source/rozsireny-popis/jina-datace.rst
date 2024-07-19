.. _ead_item_types_jinadatace:

====================================================================
Jiné datace jednotky popisu než datace vzniku jednotky popisu
====================================================================

Další popis viz: ZP 5.2.1 Jiné datace jednotky popisu než datace vzniku jednotky popisu

Jiná datace jednotky popisu se zapisuje pomocí elementu 
`<unitdatestructured> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitdatestructured>`_,
resp. vnořeného elementu:
`<daterange> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-daterange>`_.
Jiná datace má shodnou podobu jako zápis prvku popisu :ref:`ead_item_types_unitdatestructured`.
V případě výskytu více druhů datací (včetně :ref:`ead_item_types_unitdatestructured`)
se zapíší dle: :ref:`ead_item_types_unitdatestructured_multi`.

Každá jiná datace jednotky popisu musí mít na úrovni elementu 
`<daterange> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-daterange>`_
povinně uveden atribut `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_
s konstantou uvádějící typ datace dle tabulky :ref:`ead_item_types_jinadatace_typy`.


Příklad:

.. code-block:: xml

    <ead:unitdatestructured>
      <ead:daterange localtype="CONTENT">
        <ead:fromdate standarddate="1980-12-31T00:00:00">31. prosince 1980</ead:fromdate>
        <ead:todate standarddate="1980-12-31T23:59:59">31. prosince 1980</ead:todate>
      </ead:daterange>
    </ead:unitdatestructured>


.. _ead_item_types_jinadatace_typy:

Typy jiné datace jednotek popisu
========================================

.. list-table:: Tabulka typů jiné datace
   :widths: 20 10
   :header-rows: 1

   * - Typ označení
     - ``localtype=``
   * - datace obsahu jednotky popisu
     - ``CONTENT``
   * - datace, k níž se jednotka popisu hlásí
     - ``DECLARED``
   * - datace vzniku předlohy, pokud je popisována kopie, která nenahrazuje předlohu
     - ``ORIGIN``
   * - datace vzniku kopie, která nahrazuje zničenou archiválii
     - ``COPY``
   * - datace zpečetění jednotky popisu
     - ``SEALING``
   * - datace vydání listiny
     - ``ACT_PUBLISHING``
   * - datace insertu/transumptu
     - ``INSERT``
   * - datace vzniku matrice, z níž byla jednotka popisu zhotovena
     - ``MOLD_CREATION``
   * - doba užívání typáře
     - ``USAGE``
   * - datace vydání dokumentu, k němuž byl popisovaný otisk připojen
     - ``PUBLISHING``
   * - datace reambulace (aktualizace) mapy
     - ``MAP_UPDATE``
   * - datace pořízení obrazového záznamu
     - ``CAPTURING``
   * - datace pořízení filmového / zvukového záznamu
     - ``RECORDING``
   * - datace udělení / propůjčení faleristického předmětu
     - ``AWARDING``
   * - datace předání faleristického předmětu
     - ``AWARD_CER``
   * - datace odnětí / vrácení faleristického předmětu
     - ``WITHDRAWAL``
   * - datace nabytí právní účinnosti
     - ``LEGALLY_EFFECTIVE_FROM``
   * - datace nabytí právní platnosti
     - ``VALID_FROM``
   * - datace pozbytí právní účinnosti
     - ``LEGALLY_EFFECTIVE_TO``
   * - datace pozbytí právní platnosti
     - ``VALID_TO``

Návrh typů jiných datací jednotek popisu
========================================

Bude projednáno 16. 8. 2024

Elektronické systémy spisových služeb pracují s různými typy datací,
které není možné namapovat na specifikace prvku existující v Elza dle Základních pravidel.

Kromě využití některých datací pro vytváření Datace vzniku je vhodné interpretovat vybrané specifikace
také v inherentním popisu, a to v původním významu.

Viz Národní standard pro elektronické systémy spisové služby, 2023 (Příloha č. 8).
Srov. `5.6. NSESSS, příloha 2 — Dokumentace pro NAČR Portál a NDA IS 0.0 <https://frnk.lightcomp.cz/download/nacr/ndais/doc/specifikace/nsesss.html#datace>`_

.. list-table:: Tabulka typů jiné datace (doplnění)
   :widths: 20 10
   :header-rows: 1

   * - Typ označení
     - ``localtype=``
   * - datace odeslání
     - ``DISPATCH``
   * - datace doručení
     - ``DELIVERY``
   * - datace vyřízení
     - ``SETTLEMENT / PROCESSING``
   * - datace uzavření
     - ``CLOSING``