.. _ead_jp_omezeni_pristupu:

=========================================
Omezení přístupu a podmínky zveřejnění
=========================================

Základní pravidla pro zpracování archiválií definují prvky 
popisu určující přístupnost archiválíi, archivního popisu,
kopií a replik (digitalizátů a digitálních archiválií).

V rámci předávaných dat je možné pomocí textového prvku 
popisu předat informaci o případných zvláštních podmínkách 
přístupu a omezeních. Tato textová informace není nijak automatizovaně 
interpretována a nemá přímý dopad na vlastní 
zveřejnění příslušné jednotky popisu. Viz: :ref:`ead_item_types_accessrestrict`.


.. _ead_jp_omezeni_pristupu_jp:

Možnosti zveřejnění jednotky popisu
=====================================

Další popis viz: ZP 4.4.2 Možnost zveřejnění informací o jednotce popisu

Informace o možnosti zveřejnění, resp. omezení, se volitelně přidává na úroveň 
celé :ref:`jednotky popisu <ead_archdesc_hierarchy>` nebo 
případně na úroveň jednotlivých :ref:`prvků popisu <ead_item_types>`.
Pokud není tato informace uvedena, je daná úroveň popisu nebo prvek popisu 
zveřejnitelný. Pokud není celá jednotka popisu zveřejněna, uplatní se toto 
omezení automaticky i na všechny jí podřízené jednotky popisu.

Omezení zveřejnění jednotky popisu se zapisuje pomocí atributu 
`audience <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-audience>`_.

Hodnoty atributu a jejich význam:

 * ``audience="internal"`` - jednotka popisu nebo prvek popisu, který nelze zveřejnit
 * ``audience="external"`` - nepoužívá se, bez uvedení `audience <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-audience>`_ je zveřejněno

Pokud má prvek popisu zveřejnitelnou i nezveřejnitelnou podoba 
(například Obsah regest s osobními údaji a po jejich odstranění) je možné 
do exportu uložit obě hodnoty. V takovém případě bude u jednoho prvku popisu uvedena hodnota
``audience="internal"`` a druhý prvek popisu bude uveden bez dalšího upřesnění. 
Všechny ostatní atributy prvků popisu musí být shodné.

Informaci o zveřejnitelnosti / nezveřejnitelnosti lze uvádět u těchto prvků popisu:

 * :ref:`ead_item_types_unittitle`
 * :ref:`ead_item_types_scopecontent`
 * :ref:`ead_ap_relation`
 * :ref:`ead_item_types_accruals`
 * :ref:`ead_item_types_poznamka_sluzebni` (vždy nezveřejněna)


**Příklad neveřejné jednotky popisu**

.. code-block:: xml

   <ead:c level="series" audience="internal" 
        base="http://archdesc.nacr.cz/dids/b0f4a6e4-7b3b-4ce1-85e0-c746904ce126">
   ...
   </ead:c>


**Příklad neveřejného prvku popisu Obsah/regest**

.. code-block:: xml

   <ead:c level="series" 
        base="http://archdesc.nacr.cz/dids/534a33bd-e79c-4201-a77a-b22a48ee8c92">
     <ead:unittitle audience="internal">Zdravotní dokumentace</ead:unittitle>
   </ead:c>


**Příklad neveřejné a anonymizované varianty obsahu**

.. code-block:: xml

   <ead:c level="series" 
        base="http://archdesc.nacr.cz/dids/534a33bd-e79c-4201-a77a-b22a48ee8c92">
     <ead:unittitle>Zdravotní dokumentace</ead:unittitle>
     <ead:unittitle audience="internal">Zdravotní dokumentace pohlavní choroby - Jan Šalda</ead:unittitle>
   </ead:c>

.. _ead_jp_omezeni_pristupu_dao:

Možnosti zveřejnění reprodukce jednotky popisu
=================================================

Další popis viz: ZP 4.4.3 Možnost zveřejnění reprodukce jednotky popisu

Pro :ref:`digitalizáty a digitální archiválie <ead_dao>` připojené k jednotce
popisu je možné určit, že nejsou zveřejněny. Standardně jsou napojené digitální 
objekty považovány za zveřejnitelné. Na úrovni
příslušného elementu `<dao> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-dao>`_
se uvede informace o nepřístupnosti/nezveřejnění pomocí atributu ``audience="internal"``.



**Příklad neveřejného digitalizátu**

.. code-block:: xml

   <ead:did>
     <ead:unittitle>Kronika Velké Lhoty</ead:unittitle>
     <ead:dao daotype="derived"
              audience="internal" 
              identifier="edbbb43e-b574-4a8e-9311-5bbc1c5d85fc">
     </ead:dao>
   </ead:did>
