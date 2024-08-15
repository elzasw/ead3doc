.. _ead_item_types_odkazy:

===================================================================
Odkazy na příbuzné dokumenty, archiválie a pomůcky pro vyhledávání
===================================================================

Další popis viz:

 - ZP 4.5.2 Odkazy na příbuzné dokumenty, archiválie a pomůcky pro vyhledávání
 - ISAD(G) 3.5.3 Příbuzné jednotky popisu


Důležité odkazy na jiné dokumenty, archiválie nebo evidence, které s jednotkou popisu obsahově, 
formálně nebo fyzicky souvisejí se uvádějí v elementu `<relatedmaterial> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-relatedmaterial>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.


.. code-block:: xml
  :caption: Příklad zápisu odkazů na příbuzné dokumenty

  <ead:relatedmaterial>
    <ead:p>Eva ČAKRTOVÁ, Soupis matrik, 1584–1900. Soupis dokumentů, 1979, ev. č. 2.</ead:p>
  </ead:relatedmaterial>


.. _ead_item_types_odkazy_url:

Odkazy na vlastní související JP
===================================

Pokud má souvislost charakter odkazu na jinou jednotku popisu, která je 
také součástí daného EAD souboru, tak se odkaz na ni zapisuje vložením 
elementů :xml:`<archref>` a podřízeného elementu :xml:`<ref>`. 
Do atributu ``target`` se zapíše identifikátor odkazované úrovně.
Identifikátor odkazované JP musí mít charakter :ref:`ead_jp_ident_uuid`.


.. code-block:: xml
  :caption: Příklad odkazu na související JP

  <ead:relatedmaterial>
    <ead:ref target="uuid-ac73f202-a2a0-4309-9ce7-6c1e426be654"/>
  </ead:relatedmaterial>
