.. _ead_archdesc_jp_bez_prvku:

=================================
Jednotky popisu bez prvků popisu
=================================

V některých případech může být jednotka popisu téměř bez prvků popisu. 
V takovém případě by povinně uváděný element zůstal prázdný, což není přípustné. 
Řešením je doplnit speciální prvek popisu bez dodatečného významu.

.. _ead_archdesc_jp_bez_prvku_prvek:

Bezvýznamový prvek popisu
===========================

Bezvýznamový prvek popisu umožňuje splnění schématu EAD přidáním speciálního prvku 
ve formě prvku :ref:`ead_item_types_jinaozn`. Prvek je tvořen elementem ``unitid`` 
obsahující identifikátor samotné jednotky popisu.
Povinně se uvedou atributy ``localtype="ID"`` a ``label="identifikátor jednotky popisu"``. 
Jako hodnota se uvede se :ref:`identifikace jednotky popisu <ead_jp_ident>` shodná 
s obsahem atributu ``id`` na celé jednotce popisu.

Příklad:

.. code-block:: xml

  <ead:unitid localtype="ID" label="identifikátor jednotky popisu">uuid-78a1b7ce-cb98-4d8e-b442-c750ba2acad3</ead:unitid>

