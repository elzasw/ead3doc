.. _ead_item_types_physdesc:

=========================================================
Způsob a forma dochování
=========================================================

Další popis viz:

 - ZP 5.2.3 Způsob a forma dochování
 - ISAD(G) 3.1.5

Způsob a forma dochování se uvádí v elementu 
`<physdesc> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physdesc>`_. 
Fyzický stav se zapisuje jako prostý text.


.. code-block:: xml
   :caption: Příklad zápisu způsobu a formy dochování

   <ead:physdesc>originální vyhotovení</ead:physdesc>


.. _ead_item_types_physdesc_expart:

Existence analogové či digitální části
----------------------------------------

.. tags::
   aip-inherent

Pokud existují další součásti archiválie, uvede se toto v rámci prvků :ref:`ead_jp_char`
v elementu `<physfacet> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-physfacet>`_
s atributem ``localtype="EXTRA_PART"``.
Typickým případem je u digitální archiválie existence její analogové (fyzické) části.
Obsahem elementu je typ části a může nabývat hodnot:

 - ``ANALOG`` - pro analogové (fyzické) části
 - ``DIGITAL`` - pro digitální části



.. code-block:: xml
   :caption: Příklad digitální archiválie s fyzickou částí

   <ead:physdescstructured physdescstructuredtype="materialtype" 
                           coverage="whole">
     <ead:quantity>1</ead:quantity>
     <ead:unittype>item</ead:unittype>
     <ead:physfacet localType="EXTRA_PART">ANALOG</ead:physfacet>
   </ead:physdescstructured>

