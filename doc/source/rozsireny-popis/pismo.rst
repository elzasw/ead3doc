.. _ead_item_types_writting:

===================================================
Písmo
===================================================

Písmo se uvádí v elementu :ead-el:`physfacet`
s uvedením hodnoty ``localtype="WRITTING"``. 
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot. Jedná se o textovou hodnotu. 

Další popis viz: ZP 5.2.10 Jazyk, písmo

Prvek popisu `Jazyk, písmo` se rozepisuje do dvou elementů:
 * Písmo se uvádí v tomto elementu
 * Jazyk v elementu :ref:`ead_item_types_langs`

.. code-block:: xml
  :caption: Příklad: neuvedený druh jednotlivosti napsaný v těsnopisu

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localType="WRITTING">těsnopis</ead:physfacet>
   </ead:physdescstructured>
