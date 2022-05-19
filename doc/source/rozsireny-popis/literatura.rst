.. _ead_item_types_bibref:

===================================================================
Edice a literatura
===================================================================

Další popis viz:

 - ZP 5.2.11 Edice a literatura
 - ISAD(G) 3.5.4


Citace zásadních zdrojů informací odborně pojednávajících o jednotce popisu (nikoli zdroj 
informace jednotku popisu citující) a případná charakteristika typu zdroje (literatura, edice, tiskem publikovaný 
inventář, atlas, katalog dokumentů, katalog výstavy, CD ROM, webová stránka apod.)
se uvádějí v elementu `<bibliography> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-bibliography>`_
s vnořeným jedním elementem 
`<p> <https://loc.gov/ead/EAD3taglib/EAD3-TL-eng.html#elem-p>`_.


Příklad
=============


.. code-block:: xml

  <ead:bibliography>
    <ead:p>Bellegarde, Dantes. Dessalines a parle. Port-au-Prince, 1948.Chap. IV: pp. 47-54.</ead:p>
  </ead:bibliography>

