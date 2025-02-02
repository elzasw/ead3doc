.. _ead_ap_rejstrik:

==============================
Zastaralé - Ostatní entity
==============================

Entity tříd *geografická entita*, 
*dílo/výtvor* nebo *obecný pojem* se ukládají formou
rejstříků. Rejstříky slouží jako centrální místo pro uložení 
archivních entit s možností se na 
ně odkazovat z jiných prvků popisu, zejména z prvků:

 - :ref:`ead_ap_relation`


Ostatní entity se ukládají vždy na úrovni elementu 
:ead-el:`archcdesc`.
do elementu :ead-el:`index`. 
V rámci tohoto elementu jsou definovány samostatně rejstříky 
pro jednotlivé třídy entit pomocí podřízeného 
elementu :ead-el:`index`
s povinně uvedeným typem pomocí atributu `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_.

.. list-table:: Druhy rejstříků
   :widths: 20 10
   :header-rows: 1

   * - Druh rejstříku
     - ``localtype=``
   * - geografické objekty
     - ``GEO``
   * - díla / výtvory
     - ``ARTWORK``
   * - obecné pojmy
     - ``TERM``


Jednotlivé záznamy v rejstříku se ukládají pomocí 
elementu :ead-el:`indexentry`
s uvedením atributu `id <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
pro odkazování uvnitř XML dokumentu. Rejstříkový záznam je 
takto odkazován z prvků popisu.

*Příklad*:

.. code-block:: xml

  <ead:archdesc>
    ...
    <ead:index>
      <ead:index localtype="GEO">
        <ead:indexentry id="ap157">
          ...definice archivní entity...
        </ead:indexentry>
      </ead:index>
    </ead:index>
    ...
  </ead:archdesc>



Identifikátory
=================

U každé entity se uvádí alespoň jeden nebo více identifikátorů.
Povinně se uvádí identifikátor entity ve vnitřním systému a pokud je 
k dispozici tak i identifikátor CAM. Pokud se uvádí jen jeden 
identifikátor použije se přímo element :ead-el:`ref`.
V případě více identifikátorů u entity jsou tyto uvedeny 
samostatně ve společném elementu :ead-el:`ptrgrp=`.

Druh identifikátoru je povinně uveden v atributu `linkrole <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_.


Identifikátor entity
===============================

Identifikátor entity je uložen v elementu :ead-el:`ref`
s uvedením ``linkrole="LOCAL_IDENTIFIER"``. Jedná se o trvalý lokální identifikátor 
entity v rámci daného archivu. Hodnota identifikátoru se uvede uvnitř elementu.

*Příklad*:

.. code-block:: xml

  <ead:ref linkrole="LOCAL_IDENTIFIER">dfcd0632-c91e-4d27-8a8d-afcf214aafbe</ead:ref>



Odkaz do CAM
==============

Pokud je entita vedena v některé široce sdílené databázi(CAM apod.)
uvádí se tento odkaz v elementu :ead-el:`ref`.
s uvedením ``linkrole="CAM"``. Jako hodnota elementu se uvede 
identifikátor entity v CAMu.

*Příklad*:

.. code-block:: xml

  <ead:ref linkrole="CAM">33537</ead:ref>


Označení entity
===================

Preferované označení entity se povinně uvádí v elementu :ead-el:`title`
a podřízeném elementu :ead-el:`part`.
Strukturovaná podoba preferovaného označení a i variantních označení se uvádí v dílčích 
elementech :ead-el:`name`, resp. :ead-el:`geogname` pro geografické entity. 
Pokud má entita více označení uvedou se všechna známá označení seskupená
pomocí elementu :ead-el:`namegrp`.
Preferované označení se uvede jako první.


Jazyk označení
---------------

Jazyk v němž je označení uvedeno se zapisuje do atributu `lang <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-lang>`_
na úrovni příslušného elementu :ead-el:`name`,
resp. :ead-el:`geogname`.
Kód jazyku se uvádí dle definice v :ref:`ead_item_types_langs`.

*Příklad*:

.. code-block:: xml

   <ead:geogname>
     <ead:part localtype="MAIN" lang="ger">Teplitz</ead:part>
   </ead:geogname>



Stručná charakteristika
===========================

Stručná charakteristika entity se uvede v elementu :ead-el:`subject`
a podřízeném elementu :ead-el:`part`.
U podřízeného elementu se uvede atribut `localtype <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
s hodnotou ``BRIEF_DESC``.


*Příklad*:

.. code-block:: xml

  <ead:subject>
    <ead:part localtype="BRIEF_DESC">statutární město ve stejnojmenném okrese</ead:part>
  </ead:subject>



Geografické entity
=====================

Pokud je odkazovaná entita z třídy: *geografická entita* je tato zachycena
pomocí elementu :ead-el:`geogname`. 

Preferované označení geografické entity je vždy strukturovaně zaznamenáno v elementech
:ead-el:`part` s uvedením typu části označení:

 - Hlavní část jména: :token:`MAIN`
 - Geografický doplněk: :token:`SUP_GEO`
 - Chronologický doplněk: :token:`SUP_CHRO`


Souřadnice geografické entity (pokud jsou známy) jsou uvedeny 
v elementu :ead-el:`geographiccoordinates`
a to se shodným kódováním jako je uvedeno v :ref:`ead_item_types_souradnice_kodovani`.
Souřadnice jsou opakovatelné a mohou vyjadřovat buď bod 
nebo hranice příslušné entity. Souřadnice se uvádí jen u 
preferovaného označení.


*Příklad*:


.. code-block:: xml

   <ead:indexentry id="ap358">
     <ead:title>
       <ead:part>Teplice (Teplice, Česko)</ead:part>
     </ead:title>
     <ead:ptrgrp>
       <ead:ref linkrole="LOCAL_IDENTIFIER">dfcd0632-c91e-4d27-8a8d-afcf214aafbe</ead:ref>
       <ead:ref linkrole="CAM">3916</ead:ref>
     </ead:ptrgrp>
     <ead:namegrp>
       <ead:geogname>
          <ead:part localtype="MAIN">Teplice</ead:part>
          <ead:part localtype="SUP_GEO">Teplice, Česko</ead:part>
          <ead:geographiccoordinates
               coordinatesystem="WGS84">AQEAAABwf4nTpNssQMV3vY/+B0lA</ead:geographiccoordinates>
       </ead:geogname>
       <ead:geogname>
         <ead:part localtype="MAIN" lang="ger">Teplitz</ead:part>
       </ead:geogname>
     </ead:namegrp>
     <ead:subject>
       <ead:part localtype="BRIEF_DESC">statutární město ve stejnojmenném okrese</ead:part>
     </ead:subject>
   </ead:indexentry>

