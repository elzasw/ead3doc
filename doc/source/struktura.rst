.. _ead_struct:

===================
Struktura souboru
===================

Export pomůcky má tři logické části:

 - řídící část v EADu (:ref:`ead_control`)
 - prvky popisu tvořící archivní pomůcku a prvky popisu definované v úvodu archivní pomůcky (:ref:`ead_archdesc`)

Entity popisované v archivní pomůcce jsou také obvykle napojeny a odkazují se 
na další související objekty. Konkrétně se jedná o:
 
 - :ref:`přístupové body <ead_ap>`
 - :ref:`digitalizáty či digitální archiválie <ead_dao>`

V obrazu pomůcky ve formátu EAD je samostatně uložen strukturovaný 
úvod pomůcky, viz: :ref:`Uložení úvodu a prvků popisu tiráže <ead_faintro>`.

.. _ead_control:

Část control
============

Řídící část slouží k popisu dat v archivní pomůcce, informací 
o času vytvoření a aplikaci v níž byl export vytvořen, zachycení
částí úvodu a tiráže.

.. _ead_control_recordid:

control/recordid
---------------------

Povinný identifikátor datového souboru. Pečující archiv je garantem 
jedinečnosti identifikátoru datového souboru. Tento identifikátor zpravidla odpovídá
číslu archivní pomůcky.

.. compound:: 
   **Implementační poznámka k Elza**: Jako identifikátor se uloží interní označení výstupu, 
   při jeho nedostupnosti se použije jméno výstupu.


.. _ead_control_filedesc:

control/filedesc
---------------------

Element `control/filedesc <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-filedesc>`_ obsahuje základní převážně bibliografické informace 
o archivní pomůcce v souboru uložené. Povinně obsahuje podřízený element `titlestmt <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-titlestmt>`_,
kde je uvedeno jméno archivního souboru (element :token:`titleproper`) a
jméno archivní pomůcky (element :token:`subtitle`).

Atribut :token:`encodinganalog` obsahuje číslo archivního souboru.

Část je dále určena pro uložení informací nacházejících se na titulním listu,
v úvodu a tiráži archivní pomůcky.

Podrobněji viz :ref:`ead_faintro`.


control/maintenanceagency
-----------------------------

Část umožňuje definovat instituci, která archivní pomůcku vytvořila. Uvádí
se identifikátor archivu z číselníku PEvA a jméno archivu.

Příklad:

.. code-block:: xml

  <ead:maintenanceagency>
    <!-- Identifikátor z číselníku archivů -->
    <ead:agencycode localtype="PEvA">225101010</ead:agencycode>
    <!-- Jméno archivu -->
    <ead:agencyname>Státní okresní archiv Hradec Králové</ead:agencyname>
  </ead:maintenanceagency>


.. _ead_archdesc:

Část jednotek popisu
=======================

Část je tvořena jednotkami popisu archivní pomůcky a začíná vždy na úrovni
archivní soubor. V každé úrovni jsou zachyceny příslušné prvky popisu. 
Způsob uložení prvků popisu je v části :ref:`ead_item_types`.

Struktura úrovní jednotek popisu je v následující tabulce:

======================== =============
Úroveň popisu            `Atribut level <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-level>`_
======================== =============
soubor                   ``<ead:archdesc level="fonds">``
dílčí list               ``<ead:c level="subfonds">``
série                    ``<ead:c level="series">``
složka                   ``<ead:c level="subseries">``
jednotlivost             ``<ead:c level="item">``
část jednotlivosti       ``<ead:c level="otherlevel" otherlevel="itempart">``
======================== =============

.. _ead_jp_uri:

Identifikace jednotky popisu
--------------------------------

Každá jednotka popisu uložená v EADu by měla obsahovat svůj jednoznačný identifikátor.
Tento jednoznačný identifikátor slouží pro její přesné určení a identifikaci.
Identifikátor má podobu URI a ukládá se do atributu
`base <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-base>`_.
Identifikátor musí odpovídat standardu LinkedData. Pro archivy v ČR jsou možné dva přístupy 
ke konstrukci tohoto identifikátoru:

Archiv je garantem online dostupnosti archivního popisu
   V URI se použije adresa archivu, např: :code:`http://<archiv>/dids/<ID>`. Archiv je v tomto
   případě garantem trvalé dostupnosti a platnosti identifikátorů.

Varianta s jednotnými URI v rámci ČR
  Předpokladem je, že každá jednotka popisu je identifikována pomocí UUID. Všechny jednotky 
  popisu mají jednotnou podobu URI.

  URI má podobu:  :code:`http://archdesc.nacr.cz/dids/<ID>`

Doporučená je varianta s jednotným URI v rámci ČR, tj.: :code:`http://archdesc.nacr.cz/dids/<ID>`.

Příklad:

.. code-block:: xml

   <ead:c level="series"  base="http://archdesc.nacr.cz/dids/b0f4a6e4-7b3b-4ce1-85e0-c746904ce126" >
   ...
   </ead:c>




.. _ead_otherfindaid:

Pomůcky k části archivního souboru
----------------------------------------

Archivní pomůcka může popisovat celý archivní soubor nebo
jen jeho část. Pokud je popisována jen část archivního souboru 
(jeho vybrané části), tak na nadřazených úrovních se musí 
tato skutečnost vyznačit. Nekompletně popsané popsané 
úrovně popisu jsou označeny pomocí elementu 
`<otherfindaid> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-otherfindaid>`_.
Element neobsahuje odkaz na konkrétní jinou pomůcku, ale je 
informací o tom, že tato pomůcka může existovat nebo bude 
v budoucnu vytvořena.


Příklad - zachycuje nekompletně popsanou úroveň s3:

.. code-block:: xml

  <ead:c level="series">
    <ead:did>
      <ead:unittitle>s3</ead:unittitle>
    </ead:did>
    <ead:otherfindaid localtype="MightExist">
      <ead:p>Pro úroveň popisu existují nebo vzniknou další archivní pomůcky.</ead:p>
    </ead:otherfindaid>
    <ead:c level="series">
      <ead:did>
        <ead:unittitle>s3.1</ead:unittitle>
        ...
      </ead:did>
    </ead:c>
  </ead:c>

