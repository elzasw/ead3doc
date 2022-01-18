.. _ead_dao:

========================================
Digitalizáty a digitální archiválie
========================================

Digitalizáty a digitální objekty se popisují pomocí elementu
`<dao> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dao>`_.
Tento element se uvádí u jednotky popisu k níž je digitální objekt připojen. Tento objekt se tedy 
nemůže vyskytovat v části :ref:`archdesc <ead_archdesc>`.

Druh digitálního objektu se uvede v atributu `daotype <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-daotype>`_.
Přípustné hodnoty jsou:

  - :token:`derived` - digitalizát
  - :token:`borndigital` - digitální archiválie

Pokud k digitálnímu objektu existuje samostatný popis
odlišný od popisu jednotky popisu, tento se 
uvede v elementu `<descriptivenote> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-descriptivenote>`_.

.. _ead_dao_extid:

Odkaz na digitální objekt
===============================

Identifikátor digitálního objektu se uvádí v atributu
:token:`identifier`. Jedná se o identifikátor objektu 
platný v rámci archivu. Identifikátor slouží pro vazbu
mezi archivním popisem a uloženým digitálním objektem
v úložišti.


.. code-block:: xml

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
     </ead:dao>
   </ead:did>



.. _ead_dao_daoset:

Jednotka popisu s více digitálními objekty
=============================================

Pokud je k jedné jednotce popisu připojeno více digitálních objektů
jsou tyto zapouzdřeny v elementu `<daoset> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-daoset>`_.
