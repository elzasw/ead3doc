.. _ead_item_types_unitdatestructured:

Datace vzniku jednotky popisu
==============================

Další popis viz: ZP4.2.5 Datace vzniku jednotky popisu - strojově čitelný


Pokud se jedná o odhad jsou hodnoty v atributech :token:`notbefore`, resp. 
:token:`notafter` a atribut :token:`standarddate` se nepoužije. Uvnitř 
elementů se uvádí textová reprezentace datace v čitelné podobě.

Příklad - interval 1734-1776:

.. code-block:: xml

    <ead:unitdatestructured>
    <ead:daterange>
        <ead:fromdate standarddate="1734-01-01T00:00:00">1734</ead:fromdate>
        <ead:todate standarddate="1776-12-31T23:59:59">1776</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>

