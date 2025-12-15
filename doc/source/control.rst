.. _ead_control:

==============
Řídící část
==============

Řídící část, element :ead-el:`control` 
slouží k popisu metadat o archivní pomůcce, informací o času vytvoření a 
aplikaci, v níž byl export vytvořen, zachycení částí úvodu a tiráže.

.. _ead_control_recordid:

control/recordid
---------------------

Povinný identifikátor datového souboru. Pečující archiv je garantem 
jedinečnosti identifikátoru datového souboru. Jako identifikátor výstupu
se uvede pro něj vytvořené UUID.


.. _ead_control_otherrecordid:

control/otherrecordid
------------------------

Pokud se EAD používá pro uložení finální pomůcky použije se povinně element 
:ead-el:`otherrecordid` pro 
uložení jejího čísla ze základní evidence Národního archivního dědictví. 
V atributu `localtype <https://www.loc.gov/ead/EAD3taglib/#attr-localtype>`_
se uvádí ``CZ_MVCR_FINDING_AID_ID`` a jako hodnota se uvede číslo pomůcky.

Příklad - archivní pomůcka číslo 426:

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <ead:otherrecordid localtype="CZ_MVCR_FINDING_AID_ID">426</ead:otherrecordid>
    ...
  </ead:control>


Volitelně je možné přidat interní kód výstupu (např. kód revize pomůcky) umožňující blíže identifikovat výstup.
Pro uložení interního kódu se uvádí v atributu `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
hodnota ``INTERNAL_REV_ID``.
Element <ead:otherrecordid localtype="INTERNAL_REV_ID"> není opakovatelný.

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <ead:otherrecordid localtype="CZ_MVCR_FINDING_AID_ID">426</ead:otherrecordid>
    <ead:otherrecordid localtype="INTERNAL_REV_ID">REV_XY</ead:otherrecordid>
    ...
  </ead:control>


.. _ead_control_filedesc:

control/filedesc
---------------------

Element :ead-el:`filedesc` obsahuje základní převážně bibliografické informace 
o archivní pomůcce v souboru uložené. Povinně obsahuje podřízený element :ead-el:`titlestmt`,
kde je uvedeno jméno archivního souboru (element :ead-el:`titleproper`).
Pokud se jedná o předání dokončené archivní pomůcky uvede se její název povinně pomocí 
elementu :ead-el:`subtitle`. 
V ostatních případech se element :ead-el:`subtitle`
uvádí volitelně a obsahuje uživatelské pojmenování zapsaného archivního popisu.

Atribut `encodinganalog <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-encodinganalog>`_
povinně obsahuje číslo archivního souboru ze základní evidence Národního archivního dědictví.

Část je dále určena pro uložení informací nacházejících se na titulním listu,
v úvodu a tiráži archivní pomůcky. Podrobněji viz :ref:`ead_faintro`.


.. _ead_control_maintenancestatus:

control/maintenancestatus
-----------------------------

Povinný element :ead-el:`maintenancestatus` 
obsahuje informaci o stavu publikace archivní pomůcky. Pro archivní popis
vzniklý exportem z pořádacích aplikací se uvede atribut ``value="derived"``.


.. _ead_control_maintenanceagency:

control/maintenanceagency
-----------------------------

Element :ead-el:`maintenanceagency`  
je určen k zápisu instituce, která pečuje o archiválie popsané pomůckou.
Uvádí se identifikátor archivu z registru institucí (archivů) národního portálu 
(hodnota externího identifikátoru číslo archivu ze systému CAM) 
a jméno archivu. Jméno archivu se uvádí primárně v podobě shodné s označením 
v registru archivů v nezkrácené podobě.

Na úrovni elementu :ead-el:`maintenanceagency`  
se uvádí povinně atribut ``countrycode="CZ"``.

Element :ead-el:`agencycode` obsahuje kód archivu
a atribut `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
s hodnotou ``CZ_MVCR_INSTITUTION_ID``.

Příklad:

.. code-block:: xml

  <ead:maintenanceagency countrycode="CZ">
    <!-- Identifikátor z číselníku archivů -->
    <ead:agencycode localtype="CZ_MVCR_INSTITUTION_ID">225101010</ead:agencycode>
    <!-- Jméno archivu -->
    <ead:agencyname>Státní okresní archiv Hradec Králové</ead:agencyname>
  </ead:maintenanceagency>


.. _ead_control_localcontrol:

control/localcontrol
----------------------

Druh archivní pomůcky se uvádí v elementu :ead-el:`localcontrol`
s uvedením atributu :token:`localtype="FINDING_AID_TYPE"`, vlastní hodnota se 
zapisuje do elementu :ead-el:`term`
doplněným o atribut :token:`identifier=` s konstantou určující typ pomůcky.

Pokud se nejedná o uložení dat pomůcky, element se neuvede.

Druhy pomůcek a uváděné hodnoty:

============================= ==============
Druh pomůcky                  Atribut :token:`identifier`
============================= ==============
prozatímní inventární seznam  ``PROZ_INV_SEZNAM``
manipulační seznam            ``MANIP_SEZNAM``
inventář                      ``INVENTAR``
katalog                       ``KATALOG``
============================= ==============


.. _ead_control_localcontrol_rules:

Pravidla tvorby archivního popisu
=====================================

Pomocí shodného elementu se také uvádí informace o použitých pravidlech 
pro zpracování archivního popisu s uvedením atributu :token:`localtype="RULES"`.
Vlastní hodnota se zapisuje do elementu :ead-el:`term`
doplněným o atribut :token:`identifier=` s konstantou určující konkrétní 
pravidla.

Tabulka povolených hodnot pro uvedení pravidel archivního popisu:

================================ ==============
Pravidla                         Atribut :token:`identifier`
================================ ==============
základní pravidla z roku 1958    ``CZ_ZP1958``
základní pravidla od roku 2013   ``CZ_ZP2013``
================================ ==============

Druh pomůcky musí odpovídat uvedeným pravidlům dle nichž byl 
popis vytvořen a která jsou deklarována. Například 
prozatímní inventární seznam se vytvářel dle pravidel 
z roku 1958.


Příklad - jméno, číslo a druh archivní pomůcky:

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <!-- 426 - číslo archivní pomůcky -->
    <ead:otherrecordid localtype="CZ_MVCR_FINDING_AID_ID">426</ead:otherrecordid>
    <!-- 1612 - číslo listu NAD -->
    <ead:filedesc encodinganalog="1612">
      <ead:titlestmt>
        <!-- Jméno archivního souboru -->
        <ead:titleproper>A. Schramm, Praha, závod Poštorná</ead:titleproper>
        <!-- Název archivní pomůcky -->
        <ead:subtitle>A. Schramm, Praha, závod Poštorná 1833-1945</ead:subtitle>
      </ead:titlestmt>
    </ead:filedesc>
    ...
    <!-- Druh pomůcky -->
    <ead:localcontrol localtype="FINDING_AID_TYPE">
      <ead:term identifier="INVENTAR">inventář</ead:term>
    </ead:localcontrol>
    <ead:localcontrol localtype="RULES">
      <ead:term identifier="CZ_ZP2013">základní pravidla od roku 2013</ead:term>
    </ead:localcontrol>
    <ead:localcontrol localtype="CZ_FINDING_AID_EAD_PROFILE">
      <ead:term identifier="CZ_EAD3_PROFILE_20230601">profil platný od června 2023</ead:term>
    </ead:localcontrol>
    ...
  </ead:control>



.. _ead_control_localcontrol_ead3ver:

Verze profilu EAD
=============================

Export do formátu EAD musí odpovídat konkrétní revizi těchto pravidel.
Uplatněná revize se zapisuje pomocí  elementu :ead-el:`localcontrol`
s uvedením atributu :token:`localtype="CZ_FINDING_AID_EAD_PROFILE"`.
Každý export dle tohoto profilu musí mít uvedenu verzi profilu.

Vlastní hodnota se zapisuje do elementu :ead-el:`term`
doplněným o atribut :token:`identifier=` s konstantou určující konkrétní 
verzi profilu.

Tabulka povolených hodnot pro verzi profilu

============================================ ==============
Pravidla                                     Atribut :token:`identifier`
============================================ ==============
profil platný od června 2023 do února 2024   ``CZ_EAD3_PROFILE_20230601``
profil platný od března 2024 do února 2025   ``CZ_EAD3_PROFILE_20240301``
profil platný od března 2025                 ``CZ_EAD3_PROFILE_20250301``
============================================ ==============





.. _ead_control_maintenancehistory:

control/maintenancehistory
-----------------------------

Povinná část je určena pro zaznamenání informací o historii instance 
dat. Povinně se uvádí elementy:

 * :ead-el:`eventtype` s hodnotou atributu value: ``created``
 * :ead-el:`eventdatetime` s časem vytvoření
 * :ead-el:`agenttype` s hodnotou atributu value: ``machine``
 * :ead-el:`agent` obsahuje jméno zdrojového systému a jeho verzi


.. code-block:: xml

  <ead:maintenancehistory>
    <ead:maintenanceevent>
      <ead:eventtype value="created"></ead:eventtype>
      <ead:eventdatetime standarddatetime="2022-02-07T01:31:59.835+01:00">2022-02-07T01:31:59.835+01:00</ead:eventdatetime>
      <!-- Typ vytvoření popisu machine -->
      <ead:agenttype value="machine"></ead:agenttype>
      <!-- Jméno agenta -->
      <ead:agent>ELZA 2.3.9</ead:agent>
    </ead:maintenanceevent>
  </ead:maintenancehistory>  

Element ead:maintenanceevent není opakovatelný.
