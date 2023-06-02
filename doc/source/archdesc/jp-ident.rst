.. _ead_jp_uri:

--------------------------------
Identifikace jednotky popisu
--------------------------------

Každá jednotka popisu uložená v EADu musí obsahovat svůj jednoznačný identifikátor.
Tento jednoznačný identifikátor slouží pro její přesné určení a identifikaci.
Identifikátor má podobu URI a ukládá se do atributu
`base <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-base>`_.
Identifikátor musí odpovídat standardu LinkedData. Pro archivy v ČR jsou možné dva přístupy 
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
   </ead:archdesc>
