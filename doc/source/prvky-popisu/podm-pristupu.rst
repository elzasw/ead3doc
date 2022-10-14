.. _ead_item_types_accessrestrict:

==================================================================
Podmínky přístupu, práva k jednotce popisu a její reprodukci
==================================================================

Další popis viz: ZP4.4.1 Podmínky přístupu, práva k jednotce popisu a její reprodukci

Prvek popisu obsahuje textovou informaci a ukládá se do elementu 
elementu `<accessrestrict> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-accessrestrict>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.

Obsah elementu není určen pro strojové zpracování. Pro strojově interpretovaná 
omezení je nutné postupovat dle :ref:`ead_jp_omezeni_pristupu`.


.. code-block:: xml
  :caption: Příklad zápisu podmínek přístupu, práv k jednotce popisu a její reprodukci

  <ead:accessrestrict><ead:p>Evidence zemědělských pozemků</ead:p></ead:accessrestrict>
