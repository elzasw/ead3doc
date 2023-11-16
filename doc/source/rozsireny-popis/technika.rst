.. _ead_item_types_technika:

===================================================
Technika, adjustace, nosič a látka záznamu
===================================================

Další popis viz: ZP 5.2.8 Technika, adjustace, nosič a látka záznamu

Uvádí se v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="TECHNIQUE"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot.

V elementu se uvádí jen textová hodnota.


.. code-block:: xml
  :caption: Příklad: neuvedený druh jednotlivosti napsaný na stroji (strojopis)

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localType="TECHNIQUE">strojopis</ead:physfacet>
   </ead:physdescstructured>


.. _ead_item_types_technika_structured:

Strukturovaná podoba
======================

Strukturovaná podoba prvku popisu se zapisuje jako čtyři samostatné elementy 
`<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s různými hodnotami atributu ``localtype``.

.. list-table:: Tabulka hodnot pro localtype a význam
   :widths: 40 40
   :header-rows: 1

   * - Druh informace
     - ``localtype=``
   * - Technika záznamu
     - :token:`TECHNIQUE_DETAIL`
   * - Adjustace nosiče záznamu
     - :token:`MEDIUM_ADJUSTMENT`
   * - Nosič záznamu
     - :token:`MEDIUM`
   * - Látka záznamu
     - :token:`MATERIAL`


.. code-block:: xml
  :caption: Příklad: strukturovaná podoba prvku ZP 5.2.8 Technika, adjustace, nosič a látka záznamu

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localType="TECHNIQUE_DETAIL">rukopis</ead:physfacet>
     <ead:physfacet localType="MEDIUM_ADJUSTMENT">opatřeno paspartou</ead:physfacet>
     <ead:physfacet localType="MEDIUM">papír</ead:physfacet>
     <ead:physfacet localType="MATERIAL">inkoust</ead:physfacet>
   </ead:physdescstructured>

