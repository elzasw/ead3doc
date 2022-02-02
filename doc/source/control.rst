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

Příklad - archivní pomůcka číslo 157:

.. code-block:: xml

  <ead:control>
    <ead:recordid>9dfd1217-2e59-46d8-9a59-0791d32fb31a</ead:recordid>
    <ead:otherrecordid localtype="PEvA">157</ead:otherrecordid>
    ...
  </ead:control>


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
