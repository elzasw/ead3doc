.. _ead_item_types_langs:

Jazyk
=========

Jazyk popisovaného materiálu. Uvádí se název jazyku a kód jazyku. 
Kód jazyku odpovídá rozšířené podobě tří písmenného ISO kódu dle Základních
pravidel, případně viz dokumentace CAM: https://cam.nacr.cz/doc/ontology/itemtypes/name/nm_lang.html
Kód se uvádí vždy malými písmeny.


Další popis viz: ZP5.2.10 Jazyk

.. code-block:: xml

  <!-- Jazyky JP -->
  <ead:langmaterial>
      <ead:language langcode="cze">čeština</ead:language>
      <ead:language langcode="lat">latina</ead:language>
      <ead:language langcode="ger">němčina</ead:language>
  </ead:langmaterial>