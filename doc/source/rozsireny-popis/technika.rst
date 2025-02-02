.. _ead_item_types_technika:

===================================================
Technika, adjustace, nosič a látka záznamu
===================================================

Další popis viz: ZP 5.2.8 Technika, adjustace, nosič a látka záznamu

Uvádí se v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s uvedením hodnoty ``localtype="TECHNIQUE"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot.

V elementu se uvádí textová hodnota, která může být víceřádková. Alternativou 
je uvedení hodnoty v :ref:`strukturované podobě <ead_item_types_technika_structured>`.
Obě podoby není možné použít současně.


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

Strukturovaná podoba prvku popisu je alternativou k textové podobě. 
Používá se v případě, kdy jsou jednotlivé informace o technice, adjustaci, nosiči, 
látce záznamu či barevnosti strukturované a je možné je rozdělit do samostatných
elementů. Každý element obsahuje přímo řetězec s hodnotou bez odřádkování. 
Strukturovanou podobu není možné kombinovat s textovou podobou.
Strukturovaná form se zapisuje pomocí samostatných elementů 
:ead-el:`physfacet` s různými hodnotami atributu ``localtype``.

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
   * - Barevnost
     - :token:`COLOUR`


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
     <ead:physfacet localType="COLOUR">modrý</ead:physfacet>
   </ead:physdescstructured>

