.. _ead_item_types_rozmery:

===================================================
Rozměry, hmotnost, velikost, množství
===================================================

Další popis viz: 5.2.4 Rozměry, hmotnost, velikost, množství

Uvádí se v elementu `<dimensions> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dimensions>`_,
který je součástí :ref:`ead_jp_char`. Element je nutné uvést v kontextu souvisejících hodnot.

V elementu se uvádí textová hodnota nebo strukturovaná hodnota pomocí zanořeného elementu 
`<dimensions> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dimensions>`_.


.. _ead_item_types_rozmery_structured:

Strukturovaná podoba
======================

Strukturovaná hodnota se popisuje pomocí jednoho nebo více zanořených elementů
`<dimensions> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dimensions>`_.

Každý zanořený element musí obsahovat atributy:

 - druh informace - rozměr, hmotnost, velikost či množství: `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
 - jednotka: `unit <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-unit>`_


Uvnitř elementu se uvádí příslušná číselná hodnota ve formátu bez mezer a 
s tečkou pro oddělení desetinných míst.

Tabulka možný hodnot pro `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
a `unit <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-unit>`_:

.. list-table:: Tabulka hodnot pro localtype a unit
   :widths: 20 10 10
   :header-rows: 1

   * - Druh informace
     - ``localtype=``
     - ``unit=``
   * - šířka
     - :token:`WIDTH`
     - ``mm``
   * - výška
     - :token:`HEIGHT`
     - ``mm``
   * - hloubka
     - :token:`DEPTH`
     - ``mm``
   * - hmotnost
     - :token:`WEIGHT`
     - ``g``
   * - množství (byte)
     - :token:`AMOUNT`
     - ``byte``
   * - množství (kusy)
     - :token:`AMOUNT`
     - ``pieces``
   * - množství (strany)
     - :token:`AMOUNT`
     - ``pages``
   * - množství (listy)
     - :token:`AMOUNT`
     - ``sheets``
   * - trvání
     - :token:`DURATION`
     - ``s``


.. _ead_item_types_rozmery_duration:

Délka filmového a zvukového záznamu
======================================

Další popis viz: 

 - 5.13.1 Délka filmového záznamu
 - 5.14.1 Délka zvukového záznamu

Délka filmového a zvukového záznamu je zapsána formou 
:ref:`strukturovaného záznamu <ead_item_types_rozmery_structured>`.
Doba trvání se uvádí v sekundách s uvedením ``localtype="DURATION"``.



Příklady
===========

Neuvedený druh jednotlivosti s textově uvedenými rozměry: 10cm x 15cm:


.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:dimensions>10cm x 15cm</ead:dimensions>
   </ead:physdescstructured>


Neuvedený druh jednotlivosti se strukturovaně uvedenými rozměry: 100mm x 150mm:


.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:dimensions>
       <ead:dimensions localtype="WIDTH" unit="mm">100</ead:dimensions>
       <ead:dimensions localtype="HEIGHT" unit="mm">150</ead:dimensions>
     </ead:dimensions>
   </ead:physdescstructured>

