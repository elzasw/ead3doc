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
