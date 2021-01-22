.. _ead_ap:

============================================
Přístupové body
============================================

Přístupové body umožňují odkazovat jednotným způsobem
na entity související s archivním popisem. Přístupovým
bodem jsou také původci archiválií.

Přístupové body a původci se popisují pomocí elementů
`relation <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relation>`_, resp. 
`origination <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_.

Součástí přístupového bodu je vždy jeho prefereované
označení a identifikátor původce platný v rámci archivu.

.. _ead_ap_relation:

Role entit
===================

Východisko: ZP5.3-5.6 Role entit (specifikace + hodnota)

Pro uložení rolí entit se použije element
`relation <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relation>`_.
V podřízeném elementu `relationentry <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relationentry>`_
se uvede preferované označení odkazované entity.
Identifikátor entity se ukládá do atributu `encodinganalog <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-encodinganalog>`_.

Pokud je entita vedena v některé široce sdílené databázi(CAM apod.), 
je možné v atributu `href <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-href>`_ 
na ni uvést platný odkaz. Příklad: :code:`cam.nacr.cz/entities/532`. 
Odkaz musí mít podobu URI, tj. obsahuje kompletní informaci 
pro určení identifikátoru.

.. _ead_ap_originator:

Odkaz na původce
===================

Východisko: ZP4.3.1 Odkaz na původce

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

Element obsahuje atribut `relator="originator"`. Identifikátor 
entity je uložen v atributu `identifier <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-identifier>`_.

Atribut :token:`encodinganalog` umožňuje předat informaci (URL) pokud
je původce definován také v externím systému CAM.

