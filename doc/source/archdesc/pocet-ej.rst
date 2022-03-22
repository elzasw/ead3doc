.. _ead_archdesc_physdescstruct:

Počet evidenčních jednotek zpřístupněných archivní pomůckou
=================================================================

Počet evidenčních jednotek zpřístupněných archivní pomůckou. U tištěné pomůcky se uvádí se v tiráži.

V elektronickém exportu pomůcky se uvádí pouze v kořenovém elementu :token:`archdesc`.
Každý druh zpřístupněné evidenční jednotky je zapsán v samostatném elementu 
`<physdescstructured> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physdescstructured>`_. 
Podřízený element `<unittype> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittype>`_ obsahuje 
zkratu (dílčí) evidenční jednotky podle Základních pravidel 2021,  
část 2.9 (tabulka “Seznam zkratek používaných pro evidenční jednotky”).


.. code-block:: xml

  <!-- Evidencni jednotky -->
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE">
    <ead:quantity>59</ead:quantity>
    <ead:unittype>kar</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE">
    <ead:quantity>1</ead:quantity>
    <ead:unittype>map</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE">
    <ead:quantity>7</ead:quantity>
    <ead:unittype>ppr</ead:unittype>
  </ead:physdescstructured>
