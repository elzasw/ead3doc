.. _ead_jp_ident:

=================================
Identifikace jednotky popisu
=================================

.. role:: xpath(code)
   :language: xquery

.. role:: xml(code)
   :language: xml


Každá jednotka popisu uložená v EADu musí obsahovat svůj jednoznačný identifikátor.
Tento jednoznačný identifikátor slouží pro její přesné určení a identifikaci. 
V závislosti na účelu výměnného formátu jsou k dispozici dva způsoby připojování identifikátorů:

 - :ref:`bezvýznamové identifikátory ve formě UUID <ead_jp_ident_uuid>`
 - :ref:`identifikátory ve formě URI <ead_jp_ident_uri>`


.. _ead_jp_ident_uuid:

Bezvýznamové identifikátory ve formě UUID
===========================================

.. tags::
    aip-inherent, aip-kontext, popis, pomucka

Bezvýznamové identifikátory se zapisují pomocí atributu ``id`` na úrovni 
hlavního elementu jednotky popisu, tj. :xml:`<c>`, resp. :xml:`<archdesc>`.
Tyto identifikátory se používají vždy pro archivní popis uložený v AIPu 
v digitálním archivu. Lze je použít i v rámci vyměnného formátu, či na úrovni 
archivní pomůcky.

Identifikátor se skládá ze dvou částí:

 - prefix: ``uuid``
 - vlastní UUID jednotky popisu dle :rfc:`4122`, verze 4.


.. code-block:: xml

   <c level="otherlevel" otherlevel="vecnaskp" id="uuid-ac73f202-a2a0-4309-9ce7-6c1e426be654">
      <did>...</did>
   </c>


.. _ead_jp_ident_uri:

Identifikátory ve formě URI
==============================

.. tags::
    pomucka

.. note::

   U nových pomůcek je vhodné namísto formy URI používat 
   :ref:`bezvýznamové identifikátory ve formě UUID <ead_jp_ident_uuid>`.


Identifikátor má podobu URI a ukládá se do atributu
`base <https://www.loc.gov/ead/EAD3taglib/#attr-base>`_. Tento identifikátor 
je vhodné používat v případech, kdy je vázán na zpracované archiválie, má trvalou podobu 
a slouží ke zpřístupnění archiválií ve vztahu k badatelům. Identifikátor musí odpovídat 
standardu LinkedData. Pro archivy v ČR jsou možné dva přístupy 
ke konstrukci tohoto identifikátoru:

Archiv je garantem online dostupnosti archivního popisu
   V URI se použije adresa archivu, např: :code:`http://<archiv>/dids/<ID>`. Archiv je v tomto
   případě garantem trvalé dostupnosti a platnosti identifikátorů.

Varianta s jednotnými URI v rámci ČR
  Předpokladem je, že každá jednotka popisu je identifikována pomocí UUID. Všechny jednotky 
  popisu mají jednotnou podobu URI.

  URI má podobu:  :code:`http://archdesc.nacr.cz/dids/<ID>`

Doporučená je varianta s jednotným URI v rámci ČR, tj.: :code:`http://archdesc.nacr.cz/dids/<ID>`.

Příklad:

.. code-block:: xml

   <ead:archdesc level="fonds"  base="https://archdesc.nacr.cz/dids/c7f5a32b-6b27-4fb6-b960-4d8eb94a16c1" >
      ...
      <ead:c level="series"  base="http://archdesc.nacr.cz/dids/b0f4a6e4-7b3b-4ce1-85e0-c746904ce126" >
         ...
      </ead:c>
      ...
   </ead:archdesc>
