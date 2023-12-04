.. _ead_otherfindaid:

----------------------------------------
Pomůcky k části archivního souboru
----------------------------------------

Archivní pomůcka může popisovat celý archivní soubor nebo
jen jeho část. Pokud je popisována jen část archivního souboru 
(jeho vybrané části), tak na nadřazených úrovních se musí 
tato skutečnost vyznačit. Nekompletně popsané 
úrovně popisu jsou označeny pomocí elementu 
`<otherfindaid> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-otherfindaid>`_.
Element neobsahuje odkaz na konkrétní jinou pomůcku, ale je 
informací o tom, že tato pomůcka může existovat nebo bude 
v budoucnu vytvořena.


Příklad - zachycuje nekompletně popsanou úroveň *s3*,
informace o možných dalších pomůckách je na úrovni kořene 
i úrovně *s3*:

.. code-block:: xml

  <ead:archdesc level="fonds">
    <ead:otherfindaid localtype="MightExist">
      <ead:p>Pro úroveň popisu existují nebo vzniknou další archivní pomůcky.</ead:p>
    </ead:otherfindaid>
    <ead:dsc>
      <ead:c level="series">
        <ead:did>
          <ead:unittitle>s3</ead:unittitle>
        </ead:did>
        <ead:otherfindaid localtype="MightExist">
          <ead:p>Pro úroveň popisu existují nebo vzniknou další archivní pomůcky.</ead:p>
        </ead:otherfindaid>
        <ead:c level="series">
          <ead:did>
            <ead:unittitle>s3.1</ead:unittitle>
            ...
          </ead:did>
        </ead:c>
      </ead:c>
    </ead:dsc>
  </ead:archdesc>

