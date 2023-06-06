.. _ead_ap_originator:

===================
Odkaz na původce
===================

Další popis viz: ZP 4.3.1 Odkaz na původce

Pro uložení odkazu na původce se použije element
`origination <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_ a podřízený element (elementy) podle následující tabulky. 
Tento podřízený elment obsahuje povinně atribut `localtype="ORIGINATOR"`. 
Uvnitř elementu je povinně vloženým elementem 
`ref <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ref>`_ 
s odkazem na strukturovaný popis původce v elementu 
`source <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_
dle definice: :ref:`ead_ap_eac_cpf`. Uvnitř elementu je uveden název původce v textové podobě.


=====================  ==============
Třída                  Element
=====================  ==============
 osoba / bytost        `persname <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-persname>`_
 rod / rodina          `famname <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-famname>`_
 korporace             `corpname <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-corpname>`_
 událost               `name <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-name>`_
=====================  ==============


Uplatnění :ref:`dědičnosti <ead_item_types_inheritance>` je zaznamenáno pomocí 
atributu `altrender="inherited"` na úrovni elementu `origination <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_.


Příklad
===========

Odkaz na původce :ref:`Neruda, Jan (1834-1891) <ead_ap_eac_cpf_priklad>` 
s ID uvnitř XML ``ap154``:

.. code-block:: xml

    <!-- Odkaz na původce archivalii -->
    <ead:did>
      <ead:origination altrender="inherited">
        <ead:persname localtype="ORIGINATOR">
          <ead:part>
            <ead:ref target="ap154">Neruda, Jan (1834-1891)</ead:ref>
          </ead:part>
        </ead:persname>
      </ead:origination>
    </ead:did>

