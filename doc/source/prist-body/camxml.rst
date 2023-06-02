.. _ead_ap_cam:

================================
Entita dle standardu CAM
================================

Systém CAM je určen pro výměnu a dlouhodobé uchování entit.
Za tímto účelem je vytvořen `výměnný formát CAM <https://cam.nacr.cz/doc>`_.
Ten je určen pro popis archivních entit všech tříd. Pro
uložení detailního popisu entity využívané v rámci archivního 
popisu je možné využít právě `výměnný formát CAM <https://cam.nacr.cz/doc>`_.

Strukturovaně popsaná entita je uložena v elementu 
`<objectxmlwrap> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-objectxmlwrap>`_
v části `<control>/<sources>/<source> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_.
Element `<source> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_ 
povinně obsahuje atribut ``id="...."`` umožňující
jeho odkazování v rámci XML dokumentu.


Identifikátor entity
========================

Primárním identifikátorem entity je její UUID uložené v elementu ``<cam:ent>`` v atributu ``euid="..."``.
Identifikátor uložený v atributu ``eid="..."`` je určen pro vnitřní užití exportujícího systému a neplní 
funkci párovacího znaku.


Identifikátor entity v CAMu
============================

Pokud je entita uložena v systému CAM je její identifikátor předán v části jiné identifikátory 
se specifikací: ``CAM_REAL_ID``. Současně UUID entity musí být shodné s UUID ze systému CAM.


Zajištění čitelnosti entity
=============================

Každá část exportované entity musí také obsahovat lidsky čitelnou podobě. 
Účelem je zajištění dlouhodobé ochrany takto uložených dat a jistá míra 
jejich samonosnosti. Pro uložení této hodnoty se využívá samostatný rozšiřující prvek 
popisu s typem `<cam:si t="DISPLAY_NAME">`. Hodnotou prvku je čitelná podoba
metodicky odpovídající podobě entity v systému CAM.

Výjimkou je část s uložením hodnot identifikátorů, kde je uvádění čitelné 
podoby volitelné.


.. code-block:: xml
   :caption: Příklad exportu entity včetně identifikátoru CAM

   <cam:ent eid="90273" ens="ERS_APPROVED" ent="ARTWORK_ARTWORK" euid="a1ae089d-581b-48b4-97e7-5debb2c42794">
     <cam:revi>
       <cam:rid>fd742012-83db-4b60-afef-670ba9406352</cam:rid>
       <cam:usr>system</cam:usr>
       <cam:modt>2022-07-17T06:46:33.461473</cam:modt>
     </cam:revi>
     <cam:prts>
       <cam:p pid="8e6b73ce-dfca-47a1-86a9-0e1ac6e239d9" t="PT_NAME">
         <cam:itms>
           <cam:si t="NM_MAIN" uuid="22bfc088-33df-4d3f-8d92-79b17acfd720">Ohnivé léto</cam:si>
           <cam:si t="NM_SUP_GEN" uuid="939c6753-12c9-4fc3-9390-d2e03cd956dd">film</cam:si>
           <cam:si t="NM_SUP_CHRO" uuid="36498a91-8993-422a-b7e0-881ae0437e64">1939</cam:si>
           <cam:si t="NM_AUTH" uuid="5bcd6a75-e01d-4feb-bcbe-5f002a22ad4b">František Čáp a Václav Krška</cam:si>
           <cam:ei s="LNG_cze" t="NM_LANG" uuid="bad32995-9927-433c-8c69-744078aeb79e"/>
         </cam:itms>
         <cam:eits>
           <cam:si t="DISPLAY_NAME">Ohnivé léto (František Čáp a Václav Krška : film : 1939)</cam:si>
         </cam:eits>
       </cam:p>
       <cam:p pid="3c7b8571-157e-40f3-a6ec-947889df6db9" t="PT_BODY">
         <cam:itms>
           <cam:si t="BRIEF_DESC" uuid="0121a0e0-264b-4dd2-b549-ae319ca85501">celovečerní film</cam:si>
         </cam:itms>
         <cam:eits>
           <cam:si t="DISPLAY_NAME">celovečerní film</cam:si>
         </cam:eits>
       </cam:p>
       <cam:p pid="6629b495-6e1e-4fed-969a-7d2b3e7979fd" t="PT_CRE">
         <cam:itms>
           <cam:ei s="CRC_RISE" t="CRE_CLASS" uuid="f8cdfb30-4122-460b-ae4e-7ecd4f1d1614"/>
           <cam:di f="1939-01-01T00:00:00" fe="false" fmt="Y" t="CRE_DATE" to="1939-12-31T23:59:59" toe="false" uuid="9cd9012f-41d6-4697-af3c-8307422617b9"/>
         </cam:itms>
         <cam:eits>
           <cam:si t="DISPLAY_NAME">vznik, 1939 (autor/tvůrce: Krška, Václav (1900-1969), autor/tvůrce: Čáp, František (1913-1972))</cam:si>
         </cam:eits>
       </cam:p>
       <cam:p pid="d2989cd6-d914-4f22-804c-7f5728e1c1a4" t="PT_NAME">
         <cam:itms>
           <cam:si t="NM_MAIN" uuid="100e9f74-723d-449d-ac2e-72d57b3e0508">Fiery Summer</cam:si>
           <cam:ei s="LNG_eng" t="NM_LANG" uuid="88c229e8-4a08-423d-ab28-ee773179b762"/>
         </cam:itms>
         <cam:eits>
           <cam:si t="DISPLAY_NAME">Fiery Summer</cam:si>
         </cam:eits>
       </cam:p>
       <cam:p pid="849d3585-281b-4278-9bf8-62ef318a8e6a" t="PT_NAME">
         <cam:itms>
           <cam:si t="NM_MAIN" uuid="d59f3a3e-aafd-46b7-a8ac-201ad628aff4">Lodernder Sommer</cam:si>
           <cam:ei s="LNG_ger" t="NM_LANG" uuid="33095e32-1589-474d-9c53-e795873e3bc9"/>
         </cam:itms>
         <cam:eits>
           <cam:si t="DISPLAY_NAME">Lodernder Sommer</cam:si>
         </cam:eits>
       </cam:p>
       <cam:p pid="73d6caae-bc1f-40a8-9195-d2fc1044f99f" t="PT_IDENT">
         <cam:itms>
           <cam:ei s="CAM_REAL_ID" t="IDN_TYPE" uuid="49880ce8-bc76-42cd-9239-6e8c69ea3217"/>
           <cam:si t="IDN_VALUE" uuid="de710610-209a-47de-b07b-425489d0d0ff">83404</cam:si>
         </cam:itms>
       </cam:p>
     </cam:prts>
   </cam:ent>
  

