.. _ead_archdesc_hierarchy:

===============================
Hierarchie jednotek popisu
===============================

Jednotky popisu jsou uloženy v kořenovém elementu
`<archdesc> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archdesc>`_
and sadě podřízených elementů `<c> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-c>`_.
Každý z těchto elementů musí mít vždy pevně uveden druh úrovně 
v atributu `level= <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-level>`_.

Způsob uložení jednotlivých úrovní jednotek popisu je v následující tabulce:

=================================== =============
Úroveň popisu                       `Atribut level <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-level>`_
=================================== =============
:ref:`soubor <ead_archdesc_fonds>`  ``<ead:archdesc level="fonds">``
dílčí list                          ``<ead:c level="subfonds">``
série                               ``<ead:c level="series">``
složka                              ``<ead:c level="file">``
jednotlivost                        ``<ead:c level="item">``
část jednotlivosti                  ``<ead:c level="otherlevel" otherlevel="itempart">``
=================================== =============


.. _ead_archdesc_fonds:

Úroveň soubor
==================

Úroveň archivního souboru je v kořenovém elementu
`<archdesc> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archdesc>`_.
Součástí popisu archivního souboru jsou i některé prvky popisu obsahující
informace z úvodu archivní pomůcky. Konkrétně se jedná o:

 * :ref:`ead_archdesc_physdescstruct`
 * :ref:`ead_archdesc_odd`

