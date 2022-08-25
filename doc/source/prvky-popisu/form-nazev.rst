.. _ead_item_types_formnazev:

===============================
Formální název jednotky popisu
===============================

Další popis viz: ZP 4.2.4 Formální název jednotky popisu

Formální název jednotky popisu se uvádí v elementu `<title> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-title>`_
přímo umístěném v elementu `<unittitle> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-unittitle>`_
s uvedeným atributem ``localtype="FORMAL_TITLE"``. Zapisuje se jako prostý text.


Příklad:
===========

.. code-block:: xml

  <ead:unittitle localtype="FORMAL_TITLE">
    <ead:title>Bílá nemoc</ead:title>
  </ead:unittitle>


.. _ead_item_types_aut_dilo:

Autorské dílo
==================

Pokud je autorské dílo v archivním popisu zachyceno odkazem na archivní entitu, 
formální název jednotky popisu se neuvádí, ale použije se element 
`<relation> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relation>`_, 
resp. autorské dílo je speciální rolí entity 
viz: :ref:`ead_ap_relation_other`.


.. code-block:: xml

      <ead:relation relationtype="resourcerelation" 
                    linktitle="autorské dílo" 
                    linkrole="ARTWORK">
        <ead:relationentry>Bílá nemoc (Karel Čapek : divadelní hra)</ead:relationentry>
        <ead:descriptivenote>
          <ead:p>
            <ead:ref target="ap157" />
          <ead:p>
        </ead:descriptivenote>
      </ead:relation>

