.. _ead_item_types_unitid:

Referenční označení
=======================

Další popis viz: 

 - ZP 4.2.1 Referenční označení (Pořadové číslo pro manipulační seznam)


Referenční označení se uloží do elementu `<unitid> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitid>`_.
Způsob uložení je shodný se způsobem uložení prvku :ref:`ead_item_types_jinaozn`.
Povinně se uvádí atributy `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_ 
s hodnotou ``REFERENCNI_OZNACENI`` a atribut `label <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-label>`_ 
s hodnotou ``referenční označení``.


Příklad:

.. code-block:: xml

  <ead:unitid localtype="REFERENCNI_OZNACENI" 
              label="referenční označení">1/4//1</ead:unitid>


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
s hodnotou ``inv. č.``.

Příklad:

.. code-block:: xml

  <ead:unitid localtype="INV_CISLO" label="inv. č.">25</ead:unitid>

