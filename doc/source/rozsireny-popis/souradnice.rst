.. _ead_item_types_souradnice:

===================================================
Souřadnice
===================================================

Další popis viz: ZP 5.2.6 Souřadnice

Souřadnice se uvádí pomocí elementu :ead-el:`relation`
s atributy ``relationtype = "otherrelationtype"`` a ``otherrelationtype="COORDINATES"``.

Níže jsou uvedeny podřízené elementy:

 - :ead-el:`part` s hodnotou :token:`5.2.6 Souřadnice`
 - :ead-el:`geographiccoordinates`
   obsahující vlastní souřadnice dle definice :ref:`ead_item_types_souradnice_kodovani`


.. _ead_item_types_souradnice_kodovani:

Kódování souřadnic
=====================
Souřadnice se uvádí v elementu :ead-el:`geographiccoordinates`
ve formátu WKB (ISO/IEC 13249-3:2016) převedeném do BASE64, varianta little-endian. 
Souřadný systém pro souřadnice je WGS84 — SRID 4326, uvádí se 
v atributu ``coordinatesystem="WGS84"``.


Příklad
===========

Uvedení souřadnic 50.0624561N, 14.4289919E v podobě WKB (kódováno v Base64): 


.. code-block:: xml

   <ead:relations>
     <ead:relation relationtype = "otherrelationtype"  otherrelationtype="COORDINATES">
       <ead:geogname>
          <ead:part>5.2.6 Souřadnice</ead:part>
          <ead:geographiccoordinates 
               coordinatesystem="WGS84">AQEAAABwf4nTpNssQMV3vY/+B0lA</ead:geographiccoordinates>
       </ead:geogname>
     </ead:relation>
   </ead:relations>
