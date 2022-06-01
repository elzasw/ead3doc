.. _ead_archdesc_multilang:

==============================
Vícejazyčný archivní popis
==============================

Vybrané prvky popisu mohou být zapsány ve více jazycích. Tímto 
způsobem je možné vytvářet paralelní archivní popis.
Více jazykových verzí se vytváří pomocí atributu 
`lang <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-lang>`_
připojenému k příslušnému hlavnímu elementu daného prvku popisu.
Hodnota atributu (druh jazyku) u vícejazyčného popisu se uvádí 
shodným způsobem jako u prvku :ref:`ead_item_types_langs`.

Pokud není jazyk uveden, jedná se o archivní popis v českém jazyce.

Prvky popisu umožňující vícejazyčný popis:

 - :ref:`ead_item_types_unittitle`
 - :ref:`ead_item_types_scopecontent`


Příklad
=========

.. code-block:: xml

  <ead:unittitle>Evidence zemědělských pozemků</ead:unittitle>
  <ead:unittitle lang="ger">Aufzeichnungen über landwirtschaftliche Flächen</ead:unittitle>
