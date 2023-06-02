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
`<archcdesc> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-archcdesc>`_.
do elementu `<index> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-index>`_. 
V rámci tohoto elementu jsou definovány samostatně rejstříky 
pro jednotlivé třídy entit pomocí podřízeného 
elementu `<index> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-index>`_
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
elementu `<indexentry> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-indexentry>`_
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
identifikátor použije se přímo element `<ref> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ref>`_.
V případě více identifikátorů u entity jsou tyto uvedeny 
samostatně ve společném elementu `<ptrgrp> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ptrgrp>`_.

Druh identifikátoru je povinně uveden v atributu `linkrole <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_.


Identifikátor entity
===============================

Identifikátor entity je uložen v elementu `<ref> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ref>`_
s uvedením ``linkrole="LOCAL_IDENTIFIER"``. Jedná se o trvalý lokální identifikátor 
entity v rámci daného archivu. Hodnota identifikátoru se uvede uvnitř elementu.

*Příklad*:

.. code-block:: xml

  <ead:ref linkrole="LOCAL_IDENTIFIER">dfcd0632-c91e-4d27-8a8d-afcf214aafbe</ead:ref>



Odkaz do CAM
==============

Pokud je entita vedena v některé široce sdílené databázi(CAM apod.)
uvádí se tento odkaz v elementu `<ref> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ref>`_.
s uvedením ``linkrole="CAM"``. Jako hodnota elementu se uvede 
identifikátor entity v CAMu.

*Příklad*:

.. code-block:: xml

  <ead:ref linkrole="CAM">33537</ead:ref>


Označení entity
===================

Preferované označení entity se povinně uvádí v elementu `<title> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-title>`_
a podřízeném elementu `<part> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-part>`_.
Strukturovaná podoba preferovaného označení a i variantních označení se uvádí v dílčích 
elementech `<name> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-name>`_,
resp. `<geogname>`_
pro geografické entity. 
Pokud má entita více označení uvedou se všechna známá označení seskupená
pomocí elementu `<namegrp> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-namegrp>`_.
Preferované označení se uvede jako první.


Jazyk označení
---------------

Jazyk v němž je označení uvedeno se zapisuje do atributu `lang <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#attr-lang>`_
na úrovni příslušného elementu `<name> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-name>`_,
resp. `<geogname> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-geogname>`_.
Kód jazyku se uvádí dle definice v :ref:`ead_item_types_langs`.

*Příklad*:

.. code-block:: xml

   <ead:geogname>
     <ead:part localtype="MAIN" lang="ger">Teplitz</ead:part>
   </ead:geogname>



Stručná charakteristika
===========================

Stručná charakteristika entity se uvede v elementu `<subject> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-subject>`_
a podřízeném elementu `<part> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-part>`_.
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
pomocí elementu `<geogname> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-geogname>`_. 

Preferované označení geografické entity je vždy strukturovaně zaznamenáno v elementech
`<part> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-part>`_ s uvedením
typu části označení:

 - Hlavní část jména: :token:`MAIN`
 - Geografický doplněk: :token:`SUP_GEO`
 - Chronologický doplněk: :token:`SUP_CHRO`


Souřadnice geografické entity (pokud jsou známy) jsou uvedeny 
v elementu `<geographiccoordinates> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-geographiccoordinates>`_ 
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


.. _<geogname>: https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-geogname