.. _ead_ap_originator:

===================
Odkaz na původce
===================

Další popis viz: ZP 4.3.1 Odkaz na původce

Pro uložení odkazu na původce se použije element
:ead-el:`origination` a podřízený element (elementy) podle následující tabulky. 
Tento podřízený elment obsahuje povinně atribut `localtype="ORIGINATOR"`. 
Uvnitř elementu je povinně vloženým elementem 
:ead-el:`ref` 
s odkazem na strukturovaný popis původce v elementu 
:ead-el:`source`
dle definice: :ref:`ead_ap_eac_cpf`. Uvnitř elementu je uveden název původce v textové podobě.


=====================  ==============
Třída                  Element
=====================  ==============
 osoba / bytost        :ead-el:`persname`
 rod / rodina          :ead-el:`famname`
 korporace             :ead-el:`corpname`
 událost               :ead-el:`name`
=====================  ==============


Uplatnění :ref:`dědičnosti <ead_item_types_inheritance>` je zaznamenáno pomocí 
atributu `altrender="inherited"` na úrovni elementu :ead-el:`origination`.


Příklad
===========

Odkaz na původce :ref:`Neruda, Jan (1834-1891) <ead_ap_eac_cpf_priklad>` 
s ID uvnitř XML ``ap154``:

.. code-block:: xml

    <!-- Odkaz na původce archivalií -->
    <ead:did>
      <ead:origination altrender="inherited">
        <ead:persname localtype="ORIGINATOR">
          <ead:part>
            <ead:ref target="ap154">Neruda, Jan (1834-1891)</ead:ref>
          </ead:part>
        </ead:persname>
      </ead:origination>
    </ead:did>

