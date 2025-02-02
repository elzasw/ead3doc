.. _ead_item_types_unitid:

Označení jednotky popisu
==========================

Další popis viz: 

 - ZP 4.2.1 Referenční označení (Pořadové číslo pro manipulační seznam)


Referenční označení
--------------------

Referenční označení se uloží do elementu :ead-el:`unitid`.
Způsob uložení je shodný se způsobem uložení prvku :ref:`ead_item_types_jinaozn`.
Povinně se uvádí atributy `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_ 
s hodnotou ``REFERENCNI_OZNACENI`` a atribut `label <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_ 
s hodnotou ``referenční označení``. 
Uvádí se úplné referenční označení včetně prefixu CZ, identifikace archivu a čísla archivního souboru.


Příklad:

.. code-block:: xml

  <ead:unitid localtype="REFERENCNI_OZNACENI" 
              label="referenční označení">CZ620100//153//1/4//1</ead:unitid>


.. _ead_item_types_unitid_porc:

Pořadové číslo
------------------

Pořadové číslo lze uvádět pro všechny typy pomůcek. Uvádí se shodným
způsobem jako prvek popisu :ref:`ead_item_types_jinaozn`.
Povinně se uvádí atributy `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_ 
s hodnotou ``PORADOVE_CISLO`` a atribut `label <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_ 
s hodnotou ``pořadové číslo``.

Příklad:

.. code-block:: xml

  <ead:unitid localtype="PORADOVE_CISLO" 
              label="pořadové číslo">63</ead:unitid>


.. _ead_item_types_inv_cislo:

Inventární číslo
----------------------

Pro starší typy pomůcek se uvádí inventární číslo.
Uvádí se shodným
způsobem jako prvek popisu :ref:`ead_item_types_jinaozn`.
Povinně se uvádí atributy `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_ 
s hodnotou ``INV_CISLO`` a atribut `label <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_ 
s hodnotou ``inventární číslo``.

Příklad:

.. code-block:: xml

  <ead:unitid localtype="INV_CISLO" label="inventární číslo">25</ead:unitid>

