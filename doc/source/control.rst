.. _ead_control:

==============
Řídící část
==============

Řídící část, element `<control> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-control>`_ 
slouží k popisu metadat o archivní pomůcce, informací o času vytvoření a 
aplikaci v níž byl export vytvořen, zachycení částí úvodu a tiráže.

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
`<otherrecordid> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-otherrecordid>`_ pro 
uložení jejího čísla. V atributu `localtype <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
se uvádí ``PEvA`` a jako hodnota se uvede číslo pomůcky.

Příklad - archivní pomůcka číslo 426:

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <ead:otherrecordid localtype="PEvA">426</ead:otherrecordid>
    ...
  </ead:control>


.. _ead_control_filedesc:

control/filedesc
---------------------

Element `control/filedesc <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-filedesc>`_ obsahuje základní převážně bibliografické informace 
o archivní pomůcce v souboru uložené. Povinně obsahuje podřízený element `titlestmt <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-titlestmt>`_,
kde je uvedeno jméno archivního souboru (element `<titleproper> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-titleproper>`_) a
jméno archivní pomůcky (element `<subtitle> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-subtitle>`_).

Atribut :token:`encodinganalog` povinně obsahuje číslo archivního souboru.

Druh archivní pomůcky se uvádí v elementu `<localcontrol> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-localcontrol>`_
s uvedením atributu :token:`localtype="FINDING_AID_TYPE"`, vlastní hodnota se 
zapisuje do elementu `<term> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-term>`_
doplněným o atribut :token:`identifier=` s konstantou určující typ pomůcky.

Druhy pomůcek a uváděné hodnoty:

============================= ==============
Druh pomůcky                  Atribut :token:`identifier`
============================= ==============
prozatimní inventární seznam  ``PROZ_INV_SEZNAM``
manipulační seznam            ``MANIP_SEZNAM``
inventář                      ``INVENTAR``
katalog                       ``KATALOG``
============================= ==============


Část je dále určena pro uložení informací nacházejících se na titulním listu,
v úvodu a tiráži archivní pomůcky. Podrobněji viz :ref:`ead_faintro`.

Příklad - jméno, číslo a druh archivní pomůcky:

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <ead:otherrecordid localtype="PEvA">426</ead:otherrecordid>
    <ead:filedesc encodinganalog="1612">
      <ead:titlestmt>A. Schramm, Praha, závod Poštorná</ead:titlestmt>
      <ead:titleproper>A. Schramm, Praha, závod Poštorná 1833-1945</ead:titleproper>
    </ead:filedesc>
    <ead:localcontrol localtype="FINDING_AID_TYPE">
      <ead:term identifier="PROZ_INV_SEZNAM">prozatimní inventární seznam</ead:term>
    </ead:localcontrol>
    ...
  </ead:control>


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
