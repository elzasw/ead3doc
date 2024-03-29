.. _ead_item_types_container:

Ukládací jednotka
====================

Ukládací jednotka a její číslo se uloží v serializované podobě (jako jedna hodnota)
do elementu `container <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-container>`_. 
Hodnota není dále strukturována, tj. jedná se o jednu textovou hodnotu.

Další popis viz: ZP 4.2.10 Ukládací jednotka a číslo

Uplatnění :ref:`dědičnosti <ead_item_types_inheritance>` je zaznamenáno pomocí 
atributu `altrender="inherited"` na úrovni elementu `container <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-container>`_.


Příklad:

.. code-block:: xml

  <!-- Ukladaci jednotka -->
  <ead:container>z102</ead:container>



Příklad s ukládací jednotkou přenesenou z vyšší úrovně (:ref:`dědičnost <ead_item_types_inheritance>`):

.. code-block:: xml

  <ead:container altrender="inherited">z102</ead:container>

