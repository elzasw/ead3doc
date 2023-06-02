.. _ead_archdesc_physdescstruct:

Počet evidenčních jednotek zpřístupněných archivní pomůckou
=================================================================

Počet evidenčních jednotek zpřístupněných archivní pomůckou. U tištěné pomůcky se uvádí v tiráži.

V elektronickém exportu pomůcky se uvádí pouze v nejvyšším elementu archivního popisu, 
tj. v `<archdesc> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archdesc>`_.
Každý druh zpřístupněné evidenční jednotky je zapsán v samostatném elementu 
`<physdescstructured> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physdescstructured>`_,
s uvedením povinných atributů:

 - ``coverage="part"``
 - ``physdescstructuredtype="otherphysdescstructuredtype"``
 - ``otherphysdescstructuredtype="UNIT_TYPE"``


Podřízený element `<unittype> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittype>`_ obsahuje 
zkratu (dílčí) evidenční jednotky podle Základních pravidel 2021,  
část 2.9 (tabulka “Seznam zkratek používaných pro evidenční jednotky”).




.. code-block:: xml

  <!-- Evidencni jednotky -->
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE"
                          coverage="part">
    <ead:quantity>59</ead:quantity>
    <ead:unittype>kar</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE"
                          coverage="part">
    <ead:quantity>1</ead:quantity>
    <ead:unittype>map</ead:unittype>
  </ead:physdescstructured>
  <ead:physdescstructured physdescstructuredtype="otherphysdescstructuredtype" 
                          otherphysdescstructuredtype="UNIT_TYPE"
                          coverage="part">
    <ead:quantity>7</ead:quantity>
    <ead:unittype>ppr</ead:unittype>
  </ead:physdescstructured>
