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

