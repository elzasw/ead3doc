.. _ead_item_types_poznamka_sluzebni:

===================================================
Služební poznámka
===================================================

Další popis viz: ZP 4.6.1 Služební poznámka

Služební poznámka se uvádí v elementu 
:ead-el:`didnote`
s uvedeným atributem ``localtype="INTERNAL"``. 

Služební poznámka je vždy považována za nezveřejněnou, 
povinně se uvádí atribut ``audience="internal"``, viz :ref:`ead_jp_omezeni_pristupu_jp`.


Příklad
===========

Uvedení veřejné poznámky


.. code-block:: xml

   <ead:did>
      <ead:didnote localtype="INTERNAL" audience="internal">uloženo společně s druhým dílem</ead:didnote>
   </ead:did>
