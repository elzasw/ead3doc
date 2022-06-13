.. _ead_item_types_druharch:

=======================
Druh archiválie
=======================

Další popis viz: ZP4.2.8 Evidenční jednotka – druh, ZP5.2.12 Druh archiválie

Druh archiválie vychází z evidenčních jednotek definovaných v Základních pravidlech.
Uvádí se v elementu `<unittype> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittype>`_.
Element je součástí :ref:`charakteristiky jednotky popisu <ead_jp_char>`. 
Hodnota se uvádí v kontextu souvisejících hodnot.

V případě, kdy není možné určit druh archiválie, uvádí 
se speciální hodnota, které odpovídá úrovni popisu uváděné v :ref:`ead_archdesc_hierarchy`.

.. _ead_item_types_druharch_list:

Přehled druhů archiválií
=========================

.. list-table:: Přehled druhů archiválií
   :widths: 20 5
   :header-rows: 1

   * - Druh archiválie
     - Hodnota
   * - Listiny do roku 1850
     - :token:`lio`
   * - Listiny po roce 1850
     - :token:`lip`
   * - Úřední knihy
     - :token:`ukn`
   * - Rukopisy
     - :token:`rkp`
   * - Podací protokoly
     - :token:`ppr`
   * - Indexy
     - :token:`ind`
   * - Elenchy
     - :token:`ele`
   * - Repertáře
     - :token:`rep`
   * - Kartotéky
     - :token:`ktt`
   * - Pečetidla
     - :token:`pec`
   * - Razítka
     - :token:`raz`
   * - Samostatné pečetě, odlitky pečetí a otisky typářů
     - :token:`otd`
   * - Mapy
     - :token:`map`
   * - Atlasy
     - :token:`atl`
   * - Technické výkresy
     - :token:`tvy`
   * - Grafické listy
     - :token:`gli`
   * - Kresby
     - :token:`kre`
   * - Fotografie na papírové podložce
     - :token:`fsn`
   * - Fotografické desky
     - :token:`fsd`
   * - Listové filmy
     - :token:`lfi`
   * - Svitkové filmy
     - :token:`sfi`
   * - Kinofilmy
     - :token:`kin`
   * - Mikrofilmy
     - :token:`mf`
   * - Mikrofiše
     - :token:`mfis`
   * - Fotoalba
     - :token:`fal`
   * - Digitální fotografie
     - :token:`dfo`
   * - Kinematografické záznamy (díla) v analogové i digitální podobě
     - :token:`kza`
   * - Zvukové záznamy (díla) v analogové i digitální podobě
     - :token:`zza`
   * - Tisky do roku 1800
     - :token:`tio`
   * - Tisky po roce 1800
     - :token:`tip`
   * - Pohlednice
     - :token:`poh`
   * - Plakáty
     - :token:`pkt`
   * - Cenné papíry
     - :token:`cpa`
   * - Štočky
     - :token:`sto`
   * - Předměty numizmatické povahy
     - :token:`pnp`
   * - Předměty faleristické povahy
     - :token:`pfp`
   * - Jiné
     - :token:`jin`


.. _ead_item_types_druharch_spec:

Speciální hodnoty druhů
=========================

.. list-table:: Speciální hodnoty
   :widths: 20 5
   :header-rows: 1

   * - Druh archiválie
     - Hodnota
   * - Složka
     - :token:`file`
   * - Jednotlivost
     - :token:`item`
   * - Část jednotlivosti
     - :token:`itempart`


.. _ead_item_types_druharch_sample:

Příklady
=========

Jedna listina

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>lio</ead:unittype>
   </ead:physdescstructured>



Pět předmětů faleristické povahy

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>5</ead:quantity>
     <ead:unittype>pfp</ead:unittype>
   </ead:physdescstructured>


Jedna neevidovaná jednotlivost

.. code-block:: xml

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
   </ead:physdescstructured>


