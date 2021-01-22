.. _ead_dao:

========================================
Digitalizáty a digitální archiválie
========================================

Digitalizáty a digitální objekty se popisují pomocí elementu
:token:`dao`. Tento element se uvádí u jednotky popisu
k níž je digitální objekt připojen. Tento objekt se tedy 
nemůže vyskytovat v části :ref:`archdesc <ead_archdesc>`.

Pokud k digitálnímu objektu existuje samostatný popis
odlišný od popisu jednotky popisu, tak se tento 
uvede v elementu :token:`descriptivenote`.

.. _ead_dao_extid:

Odkaz na digitální objekt
===============================

Identifikátor digitálního objektu se uvádí v atributu
:token:`identifier`. Jedná se o identifikátor objektu 
platný v rámci archivu. Identifikátor slouží pro vazbu
mezi archivním popisem a uloženým digitálním objektem
v úložišti.
