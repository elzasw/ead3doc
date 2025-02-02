.. _ead_item_types_formnazev:

===============================
Formální název jednotky popisu
===============================

Další popis viz: ZP 4.2.4 Formální název jednotky popisu

Formální název jednotky popisu se uvádí v elementu :ead-el:`title`
přímo umístěném v elementu :ead-el:`unittitle`
s uvedeným atributem ``localtype="FORMAL_TITLE"``. Zapisuje se jako prostý text.


.. code-block:: xml
  :caption: Příklad - Formální název jednotky popisu jako prostý text

  <ead:unittitle localtype="FORMAL_TITLE">
    <ead:title>Bílá nemoc</ead:title>
  </ead:unittitle>


.. _ead_item_types_aut_dilo:

Autorské dílo
==================

Pokud je autorské dílo v archivním popisu zachyceno odkazem na archivní entitu, 
formální název jednotky popisu se neuvádí, ale použije se element :ead-el:`relation`, 
resp. autorské dílo je speciální rolí entity 
viz: :ref:`ead_ap_relation_other`.


.. code-block:: xml
  :caption: Příklad - Formální název jednotky popisu jako odkaz do rejstříku

      <ead:relation relationtype="resourcerelation" 
                    linktitle="autorské dílo" 
                    linkrole="ARTWORK">
        <ead:relationentry>Bílá nemoc (Karel Čapek : divadelní hra)</ead:relationentry>
        <ead:descriptivenote>
          <ead:p>
            <ead:ref target="ap157" />
          </ead:p>
        </ead:descriptivenote>
      </ead:relation>

