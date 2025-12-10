.. _ead_item_types_langs:

Jazyk
=========

Jazyk popisovaného materiálu. Uvádí se název jazyku a kód jazyku. 
Kód jazyku odpovídá rozšířené podobě tří písmenného ISO kódu dle Základních
pravidel, případně viz dokumentace CAM: https://cam.nacr.cz/doc/ontology/itemtypes/name/nm_lang.html
Kód se uvádí vždy malými písmeny. Na úrovni jednotky popisu 
lze uvést jeden nebo více jazyků a to vždy v rámci  
nadřazeného elementu :ead-el:`langmaterial`.


Další popis viz: ZP 5.2.10 Jazyk, písmo

Prvek popisu `Jazyk, písmo` se rozepisuje do dvou elementů:
 * Jazyk se uvádí v tomto elementu
 * Písmo v elementu :ref:`ead_item_types_writting`

Na úrovni každého jednotlivého uvedeného jazyka je možné uvést, zda se jedná o zděděnou 
nebo přímo nastavenou hodnotu pomocí atributu ``altrender="inherited"`` na úrovni elementu
:ead-el:`language`.


.. code-block:: xml

  <!-- Jazyky JP -->
  <ead:langmaterial>
      <ead:language langcode="cze" altrender="inherited">čeština</ead:language>
      <ead:language langcode="lat">latina</ead:language>
      <ead:language langcode="ger">němčina</ead:language>
  </ead:langmaterial>


.. _ead_item_types_langs_majority:

Převažující jazyk
----------------------

Zvláštním případem uvádění jazyku je jeho uvedení převážně 
z evidenčních důvodů na úrovni kořene archivního souboru, resp. v rámci 
úvodu pomůcky, kde má charakter převažujícího jazyka/-ků archiválií.

Převažující jazyk archiválií se uvádí obdobným způsobem 
jako prvek popisu jazyk, je však doplněn o atribut 
`altrender="majority"` na úrovni elementu :ead-el:`langmaterial`. 
Takto zapsaný jazyk přímo necharakterizuje
každou jednotlivou archiválii na nižších úrovních. Pro určení
konkrétního jazyku archiválií se využijte samotný 
prvek popisu jazyk, viz výše.


.. code-block:: xml

  <!-- Převažující jazyky -->
  <ead:langmaterial altrender="majority">
      <ead:language langcode="cze">čeština</ead:language>
      <ead:language langcode="ger">němčina</ead:language>
  </ead:langmaterial>
