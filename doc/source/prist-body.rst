.. _ead_ap:

============================================
Přístupové body
============================================

Přístupové body umožňují odkazovat 
na entity související s archivním popisem. Přístupovým
bodem jsou původci archiválií, archivní entity 
odkazované z jednotek popisu.

Přístupové body a původci se popisují pomocí elementů:

 - :ref:`odkaz na původce <ead_ap_originator>`: `origination <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-origination>`_
 - :ref:`role entit <ead_ap_relation>`: `relation <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relation>`_

Součástí přístupového bodu je vždy jeho preferované
označení a identifikátor původce platný v rámci archivu.

Přístupové body třídy osoba/bytost, rod/rodina, korporace a událost 
jsou strukturovaně popsány pomocí standardu `EAC CPF <https://eac.staatsbibliothek-berlin.de/>`_, 
resp. dle definice užití: :ref:`ead_ap_eac_cpf`. Přístupové 
body tříd geografická entita, dílo/výtvor a obecný pojem 
jsou uloženy formou :ref:`rejstříku <ead_ap_rejstrik>`.


.. toctree::
  :includehidden:
  
  prist-body/puvodce.rst
  prist-body/role-entit.rst  
  prist-body/eac-cpf.rst
  prist-body/rejstrik.rst

