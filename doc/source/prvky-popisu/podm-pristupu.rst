.. _ead_item_types_accessrestrict:

==================================================================
Podmínky přístupu, práva k jednotce popisu a její reprodukci
==================================================================

Další popis viz: ZP 4.4.1 Podmínky přístupu, práva k jednotce popisu a její reprodukci

Prvek popisu obsahuje textovou informaci a ukládá se do elementu 
elementu :ead-el:`accessrestrict` s vnořeným jedním elementem :ead-el:`p`.

Obsah elementu není určen pro strojové zpracování. Pro strojově interpretovaná 
omezení je nutné postupovat dle :ref:`ead_jp_omezeni_pristupu`.


.. code-block:: xml
  :caption: Příklad zápisu podmínek přístupu, práv k jednotce popisu a její reprodukci

  <ead:accessrestrict><ead:p>Evidence zemědělských pozemků</ead:p></ead:accessrestrict>
