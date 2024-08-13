.. _ead_dao:

========================================
Digitalizáty a digitální archiválie
========================================

Digitalizáty a digitální objekty se popisují pomocí elementu
`<dao> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dao>`_.
Tento element se uvádí u jednotky popisu k níž je digitální objekt připojen. Tento objekt se tedy 
nemůže vyskytovat v části :ref:`archdesc <ead_archdesc>`.

Druh digitálního objektu se uvede v atributu `daotype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-daotype>`_.
Přípustné hodnoty jsou:

  - :token:`derived` - digitalizát
  - :token:`borndigital` - digitální archiválie

Pokud k digitálnímu objektu existuje samostatný popis
odlišný od popisu jednotky popisu, tento se 
uvede v elementu `<descriptivenote> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-descriptivenote>`_
s jedním vnořeným elementem `<p> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-p>`_.

Případné omezení přístupnosti digitalizátu, resp. informace o jeho 
nezveřejnění viz :ref:`ead_jp_omezeni_pristupu_dao`.


.. _ead_dao_extid:

Odkaz na digitální objekt
===============================

Identifikátor digitálního objektu se uvádí v atributu
:token:`identifier`. Jedná se o identifikátor objektu 
platný v rámci archivu. Identifikátor slouží pro vazbu
mezi archivním popisem a uloženým digitálním objektem
v úložišti.


.. code-block:: xml
   :caption: Příklad jednoho digitalizátu

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
     </ead:dao>
   </ead:did>


.. _ead_dao_extid_aip:

Identifikátory v digitálním archivu
-------------------------------------

.. tags::
   aip-inherent, aip-kontext

Identifikátory digitálních balíčků se obvykle neuvádějí v archivním popisu 
uloženém uvnitř těchto balíčků. Obvykle je uložen uvnitř balíčku jen odkaz 
na :ref:`popisovanou část <ead_dao_part>`, tj. :token:`identifier` se neuvádí.

V případě odkazu na celý balíček z archivního popisu uloženého uvnitř 
samotného balíčku se uvede :token:`identifier` se speciální hodnotou 
odkazující na samotný balíček a to v souladu s pravidly příslušného digitálního 
archivu.


.. _ead_dao_part:

Odkaz na část digitálního objektu
===================================

V rámci archivního popisu je monžné odkazovat na celý digitální objekt nebo jen jeho 
vybranou část. Odkazování na část se obvykle používá u archiválií a jejich kopií 
uložených formou balíčků v digitálním archivu. Je možné odkázat například 
na konkrétní komponentu uloženou v balíčku. Při odkazování na část 
uvnitř balíčku se vždy uvádí dva atributy: ``entityref`` a ``coverage``

V atributu ``entityref`` se uvede identifikátor odkazované entity, která 
je součástí daného digitálního objektu / archivního balíčku.

V atributu ``coverage`` se uvede, zda archivní popis pokrývá celou odkazovanou 
část nebo jen uvedenou vybranou část. V případě pokrytí celé části se tím 
obvykle rozumí i pokrytí komponent na nižší úrovní, případných budoucích 
formátových migrací apod.


.. code-block:: xml
   :caption: Příklad odkazu na spis v AIPu

   <ead:did>
     <ead:unittitle>Spis XY</ead:unittitle>
     <ead:dao daotype="borndigital" 
              entityref="uuid-bc660752-fbac-40f4-b683-51bab6d31826"
              coverage="whole">
     </ead:dao>
   </ead:did>



Více digitálních objektů u jedné jednotky popisu
===================================================

Pokud je k digitálnímu objektu připojeno více samostatných
digitalizátů, tyto se uvedou jako samostatné elementy typu 
`<dao> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dao>`_.


.. code-block:: xml
   :caption: Příklad více digitalizátů s popisem

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
        <ead:descriptivenote><ead:p>Přední desky</ead:p></ead:descriptivenote>
     </ead:dao>
     <ead:dao daotype="derived" 
              identifier="d52bc6ec-9161-4452-8db9-a4c9879b9e2c">
        <ead:descriptivenote><ead:p>Strana 1</ead:p></ead:descriptivenote>
     </ead:dao>
     <ead:dao daotype="derived" 
              identifier="7d222613-eab1-4212-af1f-b29e71d0ec3a">
        <ead:descriptivenote><ead:p>Strana 2</ead:p></ead:descriptivenote>
     </ead:dao>
   </ead:did>
