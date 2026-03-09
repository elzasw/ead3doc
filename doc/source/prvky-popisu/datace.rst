.. _ead_item_types_unitdatestructured:

==============================
Datace vzniku jednotky popisu
==============================

Další popis viz:

 - ZP 4.2.5 Datace vzniku jednotky popisu - strojově čitelný
 - ISAD(G) 3.1.3 Datace


Datace vzniku jednotky popisu se zapisuje pomocí elementu 
:ead-el:`unitdatestructured`, resp. vnořeného elementu: :ead-el:`daterange`.

Datace se zapisuje vždy jako interval pomocí dílčích elementů
:ead-el:`fromdate` a :ead-el:`todate`.
V atributu :ead-attr:`standarddate`
se uvede strojově zpracovatelná podoba datace.
Pokud se jedná o odhad, jsou hodnoty v atributech 
:ead-attr:`notbefore`, resp. :ead-attr:`notafter`
a atribut :ead-attr:`standarddate` se nepoužije. Uvnitř 
elementů se uvádí textová reprezentace datace v čitelné podobě.

Na úrovni elementů :ead-el:`fromdate` a :ead-el:`todate` se uvádí povinně 
atribut :ead-attr:`altrender` s konstantou uvádějící formát datace. 

Možné hodnoty formátu:

	- století: C
	- rok: Y
	- rok/měsíc: YM
	- datum (rok/měsíc/den): D
	- datum a čas: DT

Uplatnění :ref:`dědičnosti <ead_item_types_inheritance>` je zaznamenáno pomocí 
atributu `altrender="inherited"` na úrovni elementu :ead-el:`daterange`.


.. code-block:: xml
  :caption: Příklad - interval 1734-1776

    <ead:unitdatestructured>
    <ead:daterange>
        <ead:fromdate altrender="Y" standarddate="1734-01-01T00:00:00">1734</ead:fromdate>
        <ead:todate altrender="Y" standarddate="1776-12-31T23:59:59">1776</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>


Příklad - rok 1958 (datováno konkrétním rokem), zděděno z vyšší úrovně:

.. code-block:: xml

    <ead:unitdatestructured>
    <ead:daterange altrender="inherited">
       <ead:fromdate altrender="Y" standarddate="1958-01-01T00:00:00">1958</ead:fromdate>
       <ead:todate altrender="Y" standarddate="1958-12-31T23:59:59">1958</ead:todate>
    </ead:daterange>
    </ead:unitdatestructured>


.. _ead_item_types_unitdatestructured_multi:

Uvádění více datací
=====================

Jednotka popisu může být datována svým vznikem, ale také 
pomocí jiných datací viz: :ref:`ead_item_types_jinadatace`.
Pokud je na jedné úrovni uvedeno více druhů datací (časových intervalů),
jsou tyto zabaleny v elementu: :ead-el:`dateset`.


.. code-block:: xml
  :caption: Příklad - vznik mapy 2001 s datací obsahu k 31.12.1980

    <ead:unitdatestructured>
    <ead:dateset>
      <ead:daterange>
        <ead:fromdate altrender="D" standarddate="2001-10-01T00:00:00">1. října 2001</ead:fromdate>
        <ead:todate altrender="D" standarddate="2001-10-01T23:59:59">1. října 2001</ead:todate>
      </ead:daterange>
      <ead:daterange localtype="CONTENT">
        <ead:fromdate altrender="D" standarddate="1980-12-31T00:00:00">31. prosince 1980</ead:fromdate>
        <ead:todate altrender="D" standarddate="1980-12-31T23:59:59">31. prosince 1980</ead:todate>
      </ead:daterange>
    </ead:dateset>
    </ead:unitdatestructured>




.. _ead_item_types_unitdatestructured_text:

Textový způsob zápisu datace
==============================

Další popis viz: ZP 4.2.5 Datace vzniku jednotky popisu - strojově čitelný

Textový způsob zápisu datace se použije v případě, kdy u starší 
pomůcky není k dispozici odpovídající strojová podoba, 
případně pro reprezentaci jiné formy datace, nežli je strojová podoba 
(jiný kalendář apod.).

Textová datace se zapisuje do elementu :ead-el:`unitdate`.

.. code-block:: xml
  :caption: Příklad textového způsobu zápisu

    <ead:unitdate>1730-1830, s.d.</ead:unitdate>
