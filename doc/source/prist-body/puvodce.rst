.. _ead_ap_originator:

===================
Odkaz na původce
===================

Další popis viz: ZP4.3.1 Odkaz na původce

Pro uložení odkazu na původce se použije element
`origination <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_.
Element obsahuje povinně atribut `localtype="ORIGINATOR"`. 
Uvnitř elementu je povinně vloženým elementem 
`ref <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ref>`_ 
s odkazem na strukturovaný popis původce v elementu 
`source <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_
dle definice: :ref:`ead_ap_eac_cpf`.


=====================  ==============
Třída                  Element
=====================  ==============
 osoba / bytost        `persname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-persname>`_
 rod / rodina          `famname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-famname>`_
 korporace             `corpname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-corpname>`_
 událost               `name <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-name>`_
=====================  ==============


Příklad
===========

Odkaz na původce :ref:`Neruda, Jan (1834-1891) <ead_ap_eac_cpf_priklad>` 
s ID uvnitř XML ``ap154``:

.. code-block:: xml

    <!-- Odkaz na původce archivalii -->
    <ead:did>
      <ead:origination>
        <ead:persname localtype="ORIGINATOR">
          <ead:part>
            <ead:ref target="ap154" />
          </ead:part>
        </ead:persname>
      </ead:origination>
    </ead:did>

