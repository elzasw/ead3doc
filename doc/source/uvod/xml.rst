.. _ead_xml:

============
Podoba XML
============

Uložený a předaný XML dokument musí mít povinně uvedeny hlavičky včetně kódování. 
Kódová stránka musí být ``UTF-8``.

V rámci XML dokumentu jsou používána schémata standardu EAD a systému CAM. Pro obě 
schémata jsou pevně určené prefixy pro jednotlivé elementy.

======== ========= ============
Schéma   Prefix    URI
======== ========= ============
EAD      ``ead``   ``http://ead3.archivists.org/schema/``
CAM      ``cam``   ``http://cam.tacr.cz/2019``
======== ========= ============

**Příklad podoby XML:**

.. code-block:: xml

   <?xml version="1.0" encoding="UTF-8"?>
   <ead:ead xmlns:ead="http://ead3.archivists.org/schema/" xmlns:cam="http://cam.tacr.cz/2019">

      <ead:control>
        <ead:recordid>6c15de8d-cb3e-4275-92c4-77e9f3c3be5e</ead:recordid>
        .....
      </ead:control>
      <ead:archdesc>
        ....
      </ead:archdesc>
    </ead:ead>
