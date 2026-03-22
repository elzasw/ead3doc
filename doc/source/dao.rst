.. _ead_dao:

========================================
Digitalizáty a digitální archiválie
========================================

Digitalizáty a digitální objekty se popisují pomocí elementu
:ead-el:`dao`.
Tento element se uvádí u jednotky popisu, k níž je digitální objekt připojen. Tento element se tedy 
nemůže vyskytovat v části :ref:`archdesc <ead_archdesc>`.

Druh digitálního objektu se uvede v atributu `daotype <https://www.loc.gov/ead/EAD3taglib/#attr-daotype>`_.
Přípustné hodnoty jsou:

  - :token:`derived` - digitalizát
  - :token:`borndigital` - digitální archiválie

Pokud k digitálnímu objektu existuje samostatný popis
odlišný od popisu jednotky popisu, tento se 
uvede v elementu :ead-el:`descriptivenote`
s jedním vnořeným elementem :ead-el:`p`.

Případné omezení přístupnosti digitalizátu, resp. informace o jeho 
nezveřejnění viz :ref:`ead_jp_omezeni_pristupu_dao`.


.. _ead_dao_extid:

Odkaz na digitální objekt
===============================

Digitální objekty a odkazy na ně se využívají v několika
situacích s různým významem daného odkazu.

 - archivní pomůcka obsahující odkaz na digitalizát, či jeho část
 - archivní pomůcka obsahující odkaz na digitální archiválii, 
   či její část
 - inherentní či kontextuální archivní popis odkazující 
   na konkrétní část uloženou v archivním balíčku

Odkaz na digitální objekt je možné uvést více způsoby z důvodu 
odlišného způsobu využívání výsledného souboru. Primárně jsou 
využívány atributy :ead-attr:`href` a :ead-attr:`identifier`,
případně jejich kombinace.

V základní podobě se identifikátor digitálního objektu uvádí 
přímo v atributu :token:`identifier`. Jedná se o jednoznačný 
identifikátor objektu platný v rámci daného kontextu užití.
Tato možnost se uplatní vždy u inherentního a kontextuálního 
popisu uloženého v balíčku a odkazujícího do tohoto balíčku,
viz :ref:`ead_dao_part`.

V případě odkazování z archivní pomůcky nebo archivního popisu
na digitální objekt (digitální archiválii nebo digitalizát)
se využije atribut :ead-attr:`href`. Při odkazování
na archivní balíček se jako základ URI uvede prefix :token:`aip:`
následovaný identifikátorem příslušného AIP balíčku.
Pokud archivní pomůcka odkazuje na digitalizáty uložené 
v lokálním úložišti archivu (ne jako součást AIP balíčků),
uvádí se tento odkaz jen v atributu :token:`identifier`.


.. code-block:: xml
   :caption: Příklad jednoho digitalizátu v archivní pomůcce

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
     </ead:dao>
   </ead:did>


.. code-block:: xml
   :caption: Příklad odkazu na AIP v archivní pomůcce

   <ead:did>
     <ead:unittitle>Spis k výběrovému řízení</ead:unittitle>
     <ead:dao daotype="borndigital" 
              href="aip:f1ec01cb-b0e9-4373-8427-d286bbdac890">
     </ead:dao>
   </ead:did>


.. code-block:: xml
   :caption: Příklad odkazu na část AIPu v archivní pomůcce

   <ead:did>
     <ead:unittitle>Spis k výběrovému řízení</ead:unittitle>
     <ead:dao daotype="borndigital" 
              href="aip:f1ec01cb-b0e9-4373-8427-d286bbdac890"
              identifier="uuid-59cd8797-cc9e-42e3-9720-d5c2d97dde46"
              coverage="whole">
     </ead:dao>
   </ead:did>


.. _ead_dao_extid_aip:

Identifikátory v digitálním archivu
-------------------------------------

.. tags::
   aip-inherent, aip-kontext

Identifikátory digitálních balíčků se neuvádějí v archivním popisu 
uloženém uvnitř těchto balíčků. Obvykle je uložen uvnitř balíčku jen odkaz 
na :ref:`popisovanou část <ead_dao_part>`.

V případě odkazu na celý balíček z archivního popisu uloženého uvnitř 
samotného balíčku se uvede :token:`identifier` se speciální hodnotou 
odkazující na samotný balíček, a to v souladu s pravidly příslušného digitálního 
archivu.


.. _ead_dao_part:

Odkaz na část digitálního objektu
===================================

V rámci archivního popisu je možné odkazovat na celý digitální objekt nebo jen jeho
vybranou část. Odkazování na část se obvykle používá u archiválií a jejich kopií 
uložených formou balíčků v digitálním archivu. Je možné odkázat například 
na konkrétní komponentu uloženou v balíčku. Při odkazování na část 
uvnitř balíčku se vždy uvádí dva atributy: :ead-attr:`identifier` a :ead-attr:`coverage`.
Odkazovat na část digitálního objektu je možné i z archivní pomůcky. V takovém
případě se uvádí i atribut :ead-attr:`href` v souladu s částí :ref:`ead_dao_extid`.

V atributu ``identifier`` se uvede identifikátor odkazované entity, která 
je součástí daného digitálního objektu / archivního balíčku.

V atributu ``coverage`` se uvede, zda archivní popis pokrývá celou odkazovanou 
část nebo jen uvedenou vybranou část. V případě pokrytí celé části se tím 
obvykle rozumí i pokrytí komponent na nižší úrovni, případných budoucích
formátových migrací apod.


.. code-block:: xml
   :caption: Příklad odkazu na spis v AIPu

   <ead:did>
     <ead:unittitle>Spis XY</ead:unittitle>
     <ead:dao daotype="borndigital" 
              identifier="uuid-bc660752-fbac-40f4-b683-51bab6d31826"
              coverage="whole">
     </ead:dao>
   </ead:did>



Více digitálních objektů u jedné jednotky popisu
===================================================

Pokud je k jednotce popisu připojeno více samostatných
digitalizátů, tyto se uvedou jako samostatné elementy typu 
:ead-el:`dao`.


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
