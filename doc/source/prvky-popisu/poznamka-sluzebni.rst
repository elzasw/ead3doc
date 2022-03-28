.. _ead_item_types_poznamka_sluzebni:

===================================================
Služební poznámka
===================================================

Další popis viz: ZP4.6.1 Služební poznámka

Služební poznámka se uvádí v elementu 
`<didnote> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-didnote>`_
s uvedeným atributem ``localtype="INTERNAL"``. 

Příklad
===========

Uvedení veřejné poznámky


.. code-block:: xml

   <ead:did>
      <ead:didnote localtype="INTERNAL">uloženo společně s druhým dílem</ead:didnote>
   </ead:did>
