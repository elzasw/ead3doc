.. _ead_ap_originator:

===================
Odkaz na původce
===================

Další popis viz: ZP4.3.1 Odkaz na původce

Pro uložení odkazu na původce se použije element
`origination <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_.
V závislosti na třídě původce se použije příslušný podřízený element.

=====================  ==============
Třída                  Element
=====================  ==============
 osoba / bytost        `persname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-persname>`_
 rod / rodina          `famname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-famname>`_
 korporace             `corpname <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-corpname>`_
 událost               `name <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-name>`_
=====================  ==============

Element obsahuje atribut `localtype="ORIGINATOR"`. Identifikátor 
entity je uložen v atributu `identifier <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-identifier>`_.

Atribut :token:`encodinganalog` umožňuje předat informaci (URL) pokud
je původce definován také v externím systému CAM.


.. code-block:: xml

    <!-- Odkaz na původce archivalii -->
    <ead:did>
      <ead:origination>
        <ead:persname localtype="ORIGINATOR" 
                      identifier="3e18c0df-6c48-4ef1-ae43-daf53d846077">
          <ead:part>... jméno osoby ...</ead:part>
        </ead:persname>
      </ead:origination>
    </ead:did>

