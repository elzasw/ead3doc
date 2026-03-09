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
:ead-el:`objectxmlwrap`
v části ``<control>/<sources>/<source>``.
Element :ead-el:`source` 
povinně obsahuje atribut ``id="...."`` umožňující
jeho odkazování v rámci XML dokumentu.

CAM umožňuje předávání archivních entit v XML dle schématu verze 1 a verze 2.
Archivní entity předávané dle aktuálního profilu EAD musí být uloženy 
ve schématu verze 2, viz https://stands.nacr.cz/cam/current/api/v2/schema.html.


Identifikátor entity (schéma verze 1)
========================================

Primárním identifikátorem entity je její UUID uložené v elementu ``<cam:ent>`` v atributu ``euid="..."``.
Identifikátor uložený v atributu ``eid="..."`` je určen pro vnitřní užití exportujícího systému a neplní 
funkci párovacího znaku.


Identifikátor entity (schéma verze 2)
========================================

Primárním identifikátorem entity je její UUID uložené v elementu ``<cam:entity>`` v atributu ``entityUuid="..."``.
Identifikátor uložený v atributu ``entityId="..."`` je určen pro vnitřní užití exportujícího systému a neplní 
funkci párovacího znaku.


Identifikátor entity v CAMu
============================

Pokud je entita uložena v systému CAM, je její identifikátor předán v části jiné identifikátory 
se specifikací: ``CAM_REAL_ID``. Současně UUID entity musí být shodné s UUID ze systému CAM.


Zajištění čitelnosti entity
=============================

Každá část exportované entity musí také obsahovat lidsky čitelnou podobu. 
Účelem je zajištění dlouhodobé ochrany takto uložených dat a jistá míra 
jejich samonosnosti. Pro uložení této hodnoty se využívá samostatný rozšiřující prvek 
popisu s typem `<cam:si t="DISPLAY_NAME">`. Hodnotou prvku je čitelná podoba
metodicky odpovídající podobě entity v systému CAM.

Výjimkou je část s uložením hodnot identifikátorů, kde je uvádění čitelné 
podoby volitelné.


.. code-block:: xml
   :caption: Příklad exportu entity včetně identifikátoru CAM

    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    <entity entityId="83404" entityType="ARTWORK_ARTWORK" entityUuid="a1ae089d-581b-48b4-97e7-5debb2c42794" state="ERS_APPROVED" xmlns="http://cam.tacr.cz/2025">
        <revision>
            <rev>2f1c11bb-8747-4127-b719-f666630caf09</rev>
            <metadataRev>2f1c11bb-8747-4127-b719-f666630caf09</metadataRev>
            <prevRev>7a59abad-e99a-4b87-80c4-3b8ca4dfa04e</prevRev>
            <user>
                <id>NA: Kunt Miroslav</id>
                <uuid>fdcbcc2c-e0db-4302-b224-50eab11351da</uuid>
                <name>NA: Kunt Miroslav</name>
            </user>
            <createdAt>2024-10-11T10:56:35.959372</createdAt>
        </revision>
        <parts>
            <part partUuid="a8a0fdbc-7d86-428d-a40e-c7bab5f34e57" type="PT_BODY">
                <items>
                    <string type="BRIEF_DESC" uuid="810ba6ec-e8c2-4bf5-8628-2253f6480415">celovečerní film</string>
                </items>
            </part>
            <part partUuid="f3e82038-0da2-4ee3-8c1e-fcc79ed66c5d" type="PT_CRE">
                <items>
                    <enum spec="CRC_RISE" type="CRE_CLASS" uuid="dfa1e5f7-24f2-4721-8abf-88bf74360a05"/>
                    <unitDate type="CRE_DATE" uuid="db34af99-f97f-4c0a-8357-44f378535253" format="Y" from="1939-01-01T00:00:00 " fromEstimate="false" to="1939-12-31T23:59:59 " toEstimate="false"/>
                </items>
            </part>
            <part partUuid="9e1375dc-48e6-4032-b2a4-de11f5bf13b7" type="PT_NAME">
                <items>
                    <string type="NM_MAIN" uuid="2d3fc128-81b5-41e4-863c-5687c9a4118f">Ohnivé léto</string>
                    <string type="NM_SUP_GEN" uuid="2dd2f66f-ace8-4e92-80a8-583eb75555f7">film</string>
                    <enum spec="LNG_cze" type="NM_LANG" uuid="6e7a05a0-b3d0-4126-81ac-cdf3517fccd5"/>
                    <string type="NM_SUP_CHRO" uuid="4b9d1a7b-e1af-4ac9-90eb-798afb0734bf">1939-</string>
                </items>
            </part>
            <part partUuid="6cc4b71d-8c87-4e5c-bae2-fdcbea44ebd2" type="PT_NAME">
                <items>
                    <string type="NM_MAIN" uuid="31b69fdf-3967-4338-9d37-005a9f73afd3">Fiery Summer</string>
                    <enum spec="LNG_eng" type="NM_LANG" uuid="d2aae660-1b4c-4e9a-95ff-b854b06715a6"/>
                </items>
            </part>
            <part partUuid="7aca042c-2282-450f-8ca4-518a1a41f307" type="PT_NAME">
                <items>
                    <string type="NM_MAIN" uuid="4e0483ec-c883-45fa-a3c0-68190b979169">Lodernder Sommer</string>
                    <enum spec="LNG_ger" type="NM_LANG" uuid="beaeff9b-6f15-414d-9747-b9d85a2f0ff3"/>
                </items>
            </part>
            <part partUuid="4f4f7b28-65b4-4c6a-9a1d-ca07bf085a9a" type="PT_REL">
                <items>
                    <entityRef spec="RT_THEME" type="REL_ENTITY" uuid="4f2cdf2b-eaa2-402e-bd63-b2c06fbd333a">
                        <entityRef entityId="46480" entityUuid="5bce9af4-e5c6-47ae-9cb7-efea72058ab3"/>
                    </entityRef>
                </items>
            </part>
            <part parent="f3e82038-0da2-4ee3-8c1e-fcc79ed66c5d" partUuid="59beb87d-6c15-4722-b133-531bf5cb3dd9" type="PT_REL">
                <items>
                    <entityRef spec="RT_AUTHOR" type="REL_ENTITY" uuid="b4f3e762-539d-4585-b40d-963bdfb9adce">
                        <entityRef entityId="83403" entityUuid="9136df8d-76fd-4ebc-b63e-e49c57a6f547"/>
                    </entityRef>
                </items>
            </part>
            <part parent="f3e82038-0da2-4ee3-8c1e-fcc79ed66c5d" partUuid="33750396-ee1f-487c-8ba0-f65c7207eb94" type="PT_REL">
                <items>
                    <entityRef spec="RT_AUTHOR" type="REL_ENTITY" uuid="6f4322e5-fa0f-44f3-a9cb-efc58d949744">
                        <entityRef entityId="83402" entityUuid="bd3699c0-d077-4300-979b-5b9c1d078e00"/>
                    </entityRef>
                </items>
            </part>
        </parts>
    </entity>

