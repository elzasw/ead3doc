.. _ead_item_types_unitdatestructured:

Datace vzniku jednotky popisu
==============================

Další popis viz: ZP4.2.5 Datace vzniku jednotky popisu - strojově čitelný

Datace vzniku jednotky popisu se zapisuje pomocí elementu 
`<unitdatestructured> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitdatestructured>`_.
Datace se zapisuje vždy jako interval pomocí dílčích elementů
`<fromdate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-fromdate>`_
a `<todate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-todate>`_.

V atributu `standarddate <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-standarddate>`_
se uvede strojově zpracovatelná podova datace.
Pokud se jedná o odhad jsou hodnoty v atributech 
`notbefore <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-notbefore>`_
resp. 
`notafter <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-notafter>`_
a atribut 
`standarddate <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-standarddate>`_ se nepoužije. Uvnitř 
elementů se uvádí textová reprezentace datace v čitelné podobě.

Příklad - interval 1734-1776:

.. code-block:: xml

    <ead:unitdatestructured>
    <ead:daterange>
        <ead:fromdate standarddate="1734-01-01T00:00:00">1734</ead:fromdate>
        <ead:todate standarddate="1776-12-31T23:59:59">1776</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>


.. _ead_item_types_unitdatestructured_text:

Textový způsob zápisu datace
==============================

Textový způsob zápisu datace se použije v případě, kdy u starší 
pomůcky není k dispozici odpovídající strojová podoba, 
případně pro reprezentaci jiné formy datace, než-li je strojová podoba 
(jiný kalendář apod.).

Textová datace se zapisuje do elementu 
`<unitdate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitdate>`_.

Příklad:

.. code-block:: xml

    <ead:unitdate>1730-1830, sd.</ead:unitdate>
