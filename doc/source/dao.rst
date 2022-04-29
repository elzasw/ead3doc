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
uvede v elementu `<descriptivenote> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-descriptivenote>`_
s jedním vnořeným elementem `<p> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-p>`_.

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

**Příklad jednoho digitalizátu:**

.. code-block:: xml

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
     </ead:dao>
   </ead:did>


Více digitálních objektů u jedné jednotky popisu
===================================================

Pokud je k digitálnímu objektu připojeno více samostatných
digitalizátů, tyto se uvedou jako samostatné elementy typu 
`<dao> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dao>`_.


**Příklad více digitalizátů s popisem:**

.. code-block:: xml

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
        <ead:descriptivenote><ead:p>Přední desky<ead:p></ead:descriptivenote>
     </ead:dao>
     <ead:dao daotype="derived" 
              identifier="d52bc6ec-9161-4452-8db9-a4c9879b9e2c">
        <ead:descriptivenote><ead:p>Strana 1<ead:p></ead:descriptivenote>
     </ead:dao>
     <ead:dao daotype="derived" 
              identifier="7d222613-eab1-4212-af1f-b29e71d0ec3a">
        <ead:descriptivenote><ead:p>Strana 2<ead:p></ead:descriptivenote>
     </ead:dao>
   </ead:did>
