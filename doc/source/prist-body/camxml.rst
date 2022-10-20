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
`<objectxmlwrap> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-objectxmlwrap>`_
v části `<control>/<sources>/<source> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_.
Element `<source> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_ 
povinně obsahuje atribut ``id="...."`` umožňující
jeho odkazování v rámci XML dokumentu.


Identifikátor entity
========================

Primárním identifikátorem entity je její UUID uložené v elementu ``<cam:ent>`` v atributu ``euid="..."``.


Identifikátor entity v CAMu
============================

Pokud je entita uložena v systému CAM je její identifikátor předán v části jiné identifikátory 
se specifikací: ``CAM_REAL_ID``. Současně UUID entity musí být shodné s UUID ze systému CAM.

.. code-block:: xml

    <cam:ent eid="90273" ens="ERS_APPROVED" ent="ARTWORK_ARTWORK" euid="a1ae089d-581b-48b4-97e7-5debb2c42794">
      <cam:revi>
        <cam:rid>37bdedf7-699a-4f56-a090-ceb70874429d</cam:rid>
        <cam:usr>system</cam:usr>
        <cam:modt>2022-07-17T06:46:33.461473</cam:modt>
      </cam:revi>
      <cam:prts>
        <cam:p pid="0daaa843-532c-477e-b899-117d7888a618" t="PT_NAME">
          <cam:itms>
            <cam:si t="NM_MAIN" uuid="35120288-db0b-4b1a-bce7-eed8b8544748">Ohnivé léto</cam:si>
            <cam:si t="NM_SUP_GEN" uuid="05df8716-5a48-40a3-90e5-d23584ee5d1d">film</cam:si>
            <cam:si t="NM_SUP_CHRO" uuid="dc26546c-2f5e-493c-a76a-adf88c315e05">1939</cam:si>
            <cam:si t="NM_AUTH" uuid="01cd66c8-9623-459b-af56-d1450ad92711">František Čáp a Václav Krška</cam:si>
            <cam:ei s="LNG_cze" t="NM_LANG" uuid="292f04c8-088f-4b11-9875-db29aeb16fc5"/>
          </cam:itms>
        </cam:p>
        <cam:p pid="ed126b0f-59a8-4488-9a2f-4fd4fce18e9e" t="PT_BODY">
          <cam:itms>
            <cam:si t="BRIEF_DESC" uuid="8f0798fc-55f3-4117-b37c-4bffed3ed204">celovečerní film</cam:si>
          </cam:itms>
        </cam:p>
        <cam:p pid="288f5fcf-bdfe-4f43-81f9-69b0ebbfb3d6" t="PT_CRE">
          <cam:itms>
            <cam:ei s="CRC_RISE" t="CRE_CLASS" uuid="6008990e-8fa8-462b-b16a-87b9277019cf"/>
            <cam:di f="1939-01-01T00:00:00" fe="false" fmt="Y" t="CRE_DATE" to="1939-12-31T23:59:59" toe="false" uuid="a0616b03-971d-4b77-9da3-11bea2bef5ca"/>
          </cam:itms>
        </cam:p>
        <cam:p pid="0abb859b-c9c8-4ae2-8b59-2aeb1972b219" t="PT_NAME">
          <cam:itms>
            <cam:si t="NM_MAIN" uuid="09504ac3-3bf6-4e26-9a73-9d31975436b5">Fiery Summer</cam:si>
            <cam:ei s="LNG_eng" t="NM_LANG" uuid="c044c201-07b3-4b0a-b7e9-58f89caf11d9"/>
          </cam:itms>
        </cam:p>
        <cam:p pid="29875548-ad31-4cf7-90a5-e322c24627c5" t="PT_NAME">
          <cam:itms>
            <cam:si t="NM_MAIN" uuid="6b9e09da-505a-4f91-add3-df84114b3f62">Lodernder Sommer</cam:si>
            <cam:ei s="LNG_ger" t="NM_LANG" uuid="5c56ad95-b088-4859-8a0a-2ad946b26fb9"/>
          </cam:itms>
        </cam:p>
        <cam:p pid="9f421793-e134-4541-8722-32e2adbe2baf" t="PT_IDENT">
          <cam:itms>
            <cam:ei s="CAM_REAL_ID" t="IDN_TYPE" uuid="de18f907-a0a8-4eca-b332-af3c48ae7383"/>
            <cam:si t="IDN_VALUE" uuid="fa5463c3-737b-4ed0-946c-57ce9a409b1f">83404</cam:si>
          </cam:itms>
        </cam:p>
      </cam:prts>
    </cam:ent>









