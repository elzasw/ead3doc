.. _ead_archdesc_hierarchy:

===============================
Hierarchie jednotek popisu
===============================

.. role:: xpath(code)
   :language: xquery

.. role:: xml(code)
   :language: xml


Archivní popis je tvořen hierarchicky
uspořádanou strukturou jednotek popisu.
Jednotky popisu jsou uloženy pomocí elementu
`<archdesc> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archdesc>`_
a sady podřízených elementů `<c> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-c>`_.
Každý z těchto elementů musí mít vždy pevně uveden druh úrovně 
v atributu `level= <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-level>`_.

Způsob uložení jednotlivých úrovní jednotek popisu je v následující tabulce:

=================================== =============
Úroveň popisu                       `Atribut level <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-level>`_
=================================== =============
:ref:`soubor <ead_archdesc_fonds>`  :xml:`<ead:archdesc level="fonds">`
dílčí list                          :xml:`<ead:c level="subfonds">`
série                               :xml:`<ead:c level="series">`
složka                              :xml:`<ead:c level="file">`
jednotlivost                        :xml:`<ead:c level="item">`
část jednotlivosti                  :xml:`<ead:c level="otherlevel" otherlevel="itempart">`
=================================== =============


.. _ead_archdesc_fonds:

Úroveň soubor
==================

Úroveň archivního souboru je uložena přímo v elementu
`<archdesc> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archdesc>`_.
Součástí popisu archivního souboru jsou i některé prvky popisu obsahující
informace z úvodu archivní pomůcky. Konkrétně se jedná o:

 * :ref:`ead_archdesc_physdescstruct`
 * :ref:`ead_archdesc_odd`


.. _ead_archdesc_hierarchy_other:

Jiné typy úrovní
=================

.. tags::
   aip-inherent

V případě nezpracovaných archiválií mohou být vytvářeny úrovně jiného 
typu. Příkladem jsou věcné skupiny, či úroveň spisu ze systémů
dle Národního standardu pro elektronické spisové služby.
Význam těchto jiných úrovní záleží na zdrojovém systému a konkrétní
specifikaci typů úrovní. Tyto typy ůrovní je možné zachytit v 
elementu :xml:`<ead:c level="otherlevel" otherlevel="...typ úrovně...">`
uvedením typu úrovně v atributu ``otherlevel``. Vždy se jedná 
o hodnotu z řízeného číselníku pro daný typ nezpracovaných archiválií.


.. _ead_archdesc_hierarchy_fileplan:

Spisový plán
================

.. tags::
   aip-inherent

Formalizované schéma podle nějž byly jednotlivé archiválie uspořádány u původce 
se obvykle nazývá *Spisový plán*. Informace o využití spisového plánu 
a příslušnost archiválií do něj se zachycuje v elementu :xml:`ead:fileplan`.
Informace se primárně v této podobě uvádí v inherentním popisu archiválií.
Při dalším zpracování se obvykle informace pokud je významná převede do jiných 
prvků popisu.

U spisového plánu je možné zachytit:

 - identifikátor spisového plánu
 - název spisového plánu
 - platnost spisového plánu
 - poznámku / komentář

Identifikátor spisového plánu ze zdrojového systému se uvádí v atributu ``encodinganalog``.
Informace o platnosti spisového plánu se zaznamenávají do elementu :xml:`<chronlist>` 
s jednou podřízenou položkou :xml:`<chronitem>` a vní uložený časový rozsah pomocí 
:xml:`<daterange>`. Časový rozsah může být omezený jen zhora, jen zdola nebo být plně určený. 
Součástí elementu :xml:`<chronitem>` je také informace o události v podobě: 
:xml:`<ead:event>Platnost spisového plánu</ead:event>`.

Pojmenování spisového plánu se uvede do elementu :xml:`<head>`. Případný doplňující 
komentář lze uvést do samostatného následujícího elementu :xml:`<p>`.


.. code-block:: xml

   <ead:fileplan encodinganalog="PLAN1">
     <ead:head>Spisový plán nemocnice XY</ead:head>
     <ead:p>Doplňující informace k spis. plánu.</ead:p>
     <ead:chronlist>
       <ead:chronitem>
         <ead:daterange>
           <ead:fromdate standarddate="1971-06-01" />
           <ead:todate standarddate="1974-04-30" />
         </ead:daterange>
         <ead:event>Platnost spisového plánu</ead:event>
       </ead:chronitem>
     </ead:chronlist>
   </ead:fileplan>
