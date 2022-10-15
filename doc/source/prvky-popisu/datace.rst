.. _ead_item_types_unitdatestructured:

==============================
Datace vzniku jednotky popisu
==============================

Další popis viz:

 - ZP 4.2.5 Datace vzniku jednotky popisu - strojově čitelný
 - ISAD(G) 3.1.3 Datace


Datace vzniku jednotky popisu se zapisuje pomocí elementu 
`<unitdatestructured> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitdatestructured>`_,
resp. vnořeného elementu:
`<daterange> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-daterange>`_.

Datace se zapisuje vždy jako interval pomocí dílčích elementů
`<fromdate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-fromdate>`_
a `<todate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-todate>`_.
V atributu `standarddate <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-standarddate>`_
se uvede strojově zpracovatelná podoba datace.
Pokud se jedná o odhad, jsou hodnoty v atributech 
`notbefore <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-notbefore>`_,
resp. 
`notafter <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-notafter>`_
a atribut 
`standarddate <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-standarddate>`_ se nepoužije. Uvnitř 
elementů se uvádí textová reprezentace datace v čitelné podobě.

Na úrovni elementu `<daterange> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-daterange>`_ 
se uvede povinně atribut `altrender <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-altrender>`_ 
obsahující formát datace. Možnosti hodnot formátu:

	- století: C
	- rok: Y
	- rok/měsíc: YM
	- datum (rok/měsíc/den): D
	- datum a čas: DT

Formát datace může být zadán:

	- jako jedna hodnota (např. Y)
	- jako interval (např. Y-Y)


.. code-block:: xml
  :caption: Příklad - interval 1734-1776

    <ead:unitdatestructured>
    <ead:daterange altrender="Y-Y">
        <ead:fromdate standarddate="1734-01-01T00:00:00">1734</ead:fromdate>
        <ead:todate standarddate="1776-12-31T23:59:59">1776</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>


Příklad - rok 1958 (datováno konkrétním rokem):

.. code-block:: xml

    <ead:unitdatestructured>
    <ead:daterange>
       <ead:fromdate standarddate="1958-01-01T00:00:00">1958</ead:fromdate>
       <ead:todate standarddate="1958-12-31T23:59:59">1958</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>


.. _ead_item_types_unitdatestructured_multi:

Uvádění více datací
=====================

Jednotka popisu může být datována svým vznikem, ale také 
pomocí jiných datací viz: :ref:`ead_item_types_jinadatace`.
Pokud je na jedné úrovni uvedeno více druhů datací (časových intervalů),
jsou tyto zabaleny v elementu:
`<dateset> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dateset>`_.


.. code-block:: xml
  :caption: Příklad - vznik mapy 2001 s datací obsahu k 31.12.1980

    <ead:unitdatestructured>
    <ead:dateset>
      <ead:daterange>
        <ead:fromdate standarddate="2001-10-01T00:00:00">1. října 2001</ead:fromdate>
        <ead:todate standarddate="2001-10-01T23:59:59">1. října 2001</ead:todate>
      </ead:daterange>
      <ead:daterange localtype="CONTENT">
        <ead:fromdate standarddate="1980-12-31T00:00:00">31. prosince 1980</ead:fromdate>
        <ead:todate standarddate="1980-12-31T23:59:59">31. prosince 1980</ead:todate>
      </ead:daterange>
    <ead:dateset>
    </ead:unitdatestructured>




.. _ead_item_types_unitdatestructured_text:

Textový způsob zápisu datace
==============================

Další popis viz: ZP 4.2.5 Datace vzniku jednotky popisu - strojově čitelný

Textový způsob zápisu datace se použije v případě, kdy u starší 
pomůcky není k dispozici odpovídající strojová podoba, 
případně pro reprezentaci jiné formy datace, než-li je strojová podoba 
(jiný kalendář apod.).

Textová datace se zapisuje do elementu 
`<unitdate> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unitdate>`_.

.. code-block:: xml
  :caption: Příklad textového způsobu zápisu

    <ead:unitdate>1730-1830, s.d.</ead:unitdate>
