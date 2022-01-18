.. _ead_ap_relation:

===================
Role entit
===================

Další popis viz: 
 - 5.3.1 Popisované role entit ve vztahu k listině
 - 5.4.1 Popisované role entit ve vztahu k úředním knihám, registraturním pomůckám a kartotékám
 - 5.5.1 Popisované role entit ve vztahu k rukopisům
 - 5.6.1 Popisované role entit ve vztahu k hudebninám
 - 5.7.6 Popisované role entit ve vztahu k typářům a jejich otiskům
 - 5.8.1 Popisované role entit ve vztahu ke spisům
 - 5.9.1 Popisované role entit ve vztahu k mapám a atlasům
 - 5.10.1 Popisované role entit ve vztahu k technickým výkresům
 - 5.11.2 Popisované role entit ve vztahu ke grafickým listům a kresbám
 - 5.12.1 Popisované role entit ve vztahu k fotografickým archiváliím
 - 5.13.2 Popisované role entit ve vztahu k záznamům
 - 5.14.2 Popisované role entit ve vztahu ke zvukovým archiváliím
 - 5.15.1 Popisované role entit ve vztahu k tiskům do roku 1800 a po roce 1800
 - 5.16.1 Popisované role entit ve vztahu k pohlednicím
 - 5.17.1 Popisované role entit ve vztahu k plakátům
 - 5.18.1 Popisované role entit ve vztahu k cenným papírům
 - 5.19.1 Popisované role entit ve vztahu ke štočkům
 - 5.20.1 Popisované role entit ve vztahu k digitálním archivním jednotkám
 - 5.21.1 Popisované role entit ve vztahu k numizmatickým předmětům
 - 5.22.1 Popisované role entit ve vztahu k faleristickým předmětům
 - 5.23.1 Popisované role entit ve vztahu k evidenční jednotce Jiné


Pro uložení rolí entit se použije element
`relation <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relation>`_.
V podřízeném elementu `relationentry <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relationentry>`_
se uvede preferované označení odkazované entity.
Identifikátor entity se ukládá do atributu `encodinganalog <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-encodinganalog>`_.
Role entity se ukládá do atributu `linkrole <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_. 
Tabulka rolí je uvedena níže v části: :ref:`ead_ap_relation_roles`.
Uživatelsky čitelné označení role se zapisuje do atributu `linktitle <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linktitle>`_.
Čitelné označení umožňuje uživatelům a publikačním systémům roli 
přímo interpretovat zatímco atribut `linkrole <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_
ji umožňuje interpretovat strojově, zajistit překlady.
V případě dílčí specializace role v předávajícím systému je v atributu 
`linktitle <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linktitle>`_ možné
tuto odlišnost zachytit.

Pokud je entita vedena v některé široce sdílené databázi(CAM apod.), 
je možné v atributu `href <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-href>`_ 
na ni uvést platný odkaz. Příklad: :code:`cam.nacr.cz/entities/532`. 
Odkaz musí mít podobu URI, tj. obsahuje kompletní informaci 
pro určení identifikátoru.


.. code-block:: xml

      <ead:relation relationtype="resourcerelation" 
                    encodinganalog="31b9d81a-e3dd-4053-a09f-5c4c911841ff"
                    href="cam.nacr.cz/entities/33608"
                    linktitle="autor" 
                    linkrole="AUTHOR">
        <ead:relationentry>Borovský, Karel Havlíček (1821-1856)</ead:relationentry>
      </ead:relation>


.. _ead_ap_relation_roles:

Definice rolí
==============

.. list-table:: Mapování rolí entit
   :widths: 20 10 20 10
   :header-rows: 1

   * - Jméno role (linktitle)
     - Označení v EADu (linkrole)
     - Poznámka
     - kód Elza
   * - autor
     - ``AUTHOR``
     - zastaralé, používá se nyní již jen u technických výkresů, asi by mohlo být 
          přejmenováno na "autor výkresu"
     - ZP2015_ENTITY_ROLE_1
   * - autor dialogu
     - ``AUTHOR_DIALOGS``
     - 5.13.2, 5.14.2 pro kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_2
   * - autor doprovodného textu
     - ``AUTHOR_ACCOMP_TEXT``
     - 5.6.1, hudebniny
     - ZP2015_ENTITY_ROLE_3
   * - autor hudby/skladatel
     - ``COMPOSER``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_6
   * - autor choreografie/choreograf
     - ``CHOREOGRAPHER``
     - 5.13.2, kinematografické filmy
     - ZP2015_ENTITY_ROLE_7
   * - autor komentáře
     - ``AUTHOR_COMMENT``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_8
   * - autor námětu
     - ``AUTHOR_TOPIC``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_9
   * - autor textové složky/textař
     - ``LYRICIST``
     - 5.4.1, 5.5.1, 5.6.1, 5.9.1, 5.15.1, 5.17.1, 5.18.1 - úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, mapy (mapová díla, atlasy), tisky, plakáty, štočky
     - ZP2015_ENTITY_ROLE_11
   * - distributor
     - ``DISTRIBUTOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_20
   * - dramaturg
     - ``DRAMATURG``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_40
   * - držitel cenného papíru
     - ``HOLDER``
     - 5.19.1 - cenné papíry
     - ZP2015_ENTITY_ROLE_23
   * - editor
     - ``EDITOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_34
   * - fotograf
     - ``PHOTOGRAPHER``
     - 5.9.1, 5.12.1, 5.15.1, 5.16.1, 5.17.1, 5.18.1 - mapy (mapová díla, atlasy), fotografické archiválie, tisky, pohlednice, plakáty, štočky
     - ZP2015_ENTITY_ROLE_31, dříve ZP2015_ENTITY_ROLE_4
   * - interpret hudby
     - ``MUSIC_INTERPRETER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_30
   * - kameraman
     - ``CAMERAMAN``
     - 5.13.2 - kinematografické filmy
     - ZP2015_ENTITY_ROLE_29
   * - kartograf
     - ``CARTOGRAPHER``
     - 5.9.1, 5.15.1, 5.18.1 - mapy (mapová díla, atlasy), tisky, štočky
     - ZP2015_ENTITY_ROLE_33
   * - kreslič
     - ``DRAFTSMAN``
     - 5.9.1, 5.10.1 - mapy (mapová díla, atlasy), technické výkresy
     - ZP2015_ENTITY_ROLE_36
   * - lektor
     - ``LECTOR``
     - 5.15.1 - tisky
     - ZP2015_ENTITY_ROLE_45
   * - majitel typáře
     - `` ``
     - 5.7.6 - typáře (otisky, kopie otisků)
     - ZP2015_ENTITY_ROLE_37
   * - místo natáčení
     - ``LOCATION_SHOOTING``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_56
   * - místo vydání
     - ``LOCATION_PUBLISHING``
     - 5.3.1, 5.7.6, 5.15.1, 5.17.1, 5.16.1, 5.19.1 - listiny (před i po roce 1850), typáře (otisky, kopie otisků), tisky, plakáty, pohlednice, cenné papíry
     - ZP2015_ENTITY_ROLE_58
   * - místo vydání dokumentu
     - `` ``
     - 
     - 
   * - místo vydavatele
     - ``LOCATION_PUBLISHER``
     - 5.21.1, 5.22.1 - faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_57
   * - místo výroby jednotky popisu
     - ``PLACE_MANUFACTURE``
     - 5.13.2, 5.14.2, 5.21.1, 5.22.1 - kinematografické filmy, zvukové archiválie, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_59
   * - místo vzniku jednotky popisu
     - ``PLACE_ORIGIN``
     - 5.3.1, 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.10.1, 5.11.2, 5.12.1, 5.18.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), technické výkresy, grafické listy, fotografické archiválie, štočky
     - ZP2015_ENTITY_ROLE_61
   * - místo vzniku předlohy popisované kopie
     - ``PLACE_COPY_CREATION``
     - 5.3.1, 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.10.1, 5.11.2, 5.15.1, 5.16.1, 5.17.1, 5.18.1, 5.19.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), technické výkresy, grafické listy, tisky, pohlednice, plakáty, štočky, cenné papíry, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_62
   * - navrhovatel vyznamenání/ceny
     - `` ``
     - 
     - ZP2015_ENTITY_ROLE_75
   * - název vyznamenání/ceny
     - `` ``
     - 
     - 
   * - nositel vyznamenání/ceny
     - `` ``
     - 
     - ZP2015_ENTITY_ROLE_74
   * - objednavatel/příjemce
     - ``CLIENT``
     - 5.5.1, 5.6.1, 5.9.1, 5.13.2, 5.14.2 - rukopisy, hudebniny, mapy (mapová díla, atlasy), kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_19
   * - odesílatel
     - ``SENDER``
     - 5.12.1, 5.16.1 - fotografické archiválie, pohlednice
     - ZP2015_ENTITY_ROLE_24
   * - pečetitel
     - ``SEALER``
     - 5.3.1 - listiny (před i po roce 1850)
     - ZP2015_ENTITY_ROLE_17
   * - písař
     - ``SCRIBE``
     - 5.3.1, 5.4.1, 5.5.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy
     - ZP2015_ENTITY_ROLE_48
   * - produkční společnost/producent
     - ``PRODUCER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_18
   * - předávající vyznamenání/ceny
     - `` ``
     - 
     - ZP2015_ENTITY_ROLE_76
   * - překladatel
     - ``TRANSLATOR``
     - 5.5.1, 5.13.2, 5.14.2, 5.15.1 - rukopisy, kinematografické filmy, zvukové archiválie, tisky
     - ZP2015_ENTITY_ROLE_44
   * - příjemce
     - ``RECIPIENT``
     - 5.3.1, 5.11.2, 5.12.1, 5.15.1, 5.16.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), grafické listy, fotografické archiválie, tisky, pohlednice, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_21
   * - redaktor
     - ``REDACTOR``
     - 5.9.1, 5.15.1 - mapy (mapová díla, atlasy), tisky<
     - ZP2015_ENTITY_ROLE_32, dříve ZP2015_ENTITY_ROLE_35
   * - režisér
     - ``DIRECTOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_27
   * - ručitel (rukojmě)
     - ``GUARANTOR``
     - 5.3.1 - (před i po roce 1850)
     - ZP2015_ENTITY_ROLE_47
   * - scénárista
     - ``SCRIPTWRITER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_28
   * - schvalovatel technického výkresu
     - ``APPROVER``
     - 5.10.1 - technické výkresy
     - ZP2015_ENTITY_ROLE_25
   * - související entita
     - `` ``
     - 
     - 
   * - stavitel
     - ``BUILDER``
     - 5.10.1 - technické výkresy
     - ZP2015_ENTITY_ROLE_26
   * - střih/střihač
     - ``CUTTER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_41
   * - svědek
     - ``WITNESS``
     - 5.3.1 - listiny (před i po roce 1850)
     - ZP2015_ENTITY_ROLE_46
   * - tiskárna/tiskař
     - ``PRINTER``
     - 5.6.1, 5.9.1, 5.11.2, 5.15.1, 5.16.1, 5.17.1, , 5.19.1 - hudebniny, mapy (mapová díla, atlasy), grafické listy, tisky, pohlednice, plakáty, , cenné papíry
     - ZP2015_ENTITY_ROLE_52, dříve ZP2015_ENTITY_ROLE_51
   * - tvůrce technického zpracování
     - `` ``
     - 5.11.2 - grafické listy
     - ZP2015_ENTITY_ROLE_38
   * - tvůrce výtvarné stránky
     - `` ``
     - 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.11.2, 5.13.2, , 5.14.2, 5.15.1, 5.16.1, 5.18.1, 5.19.1, 5.21.1, 5.22.1 - úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), grafické listy, kinematografické filmy, zvukové archiválie, tisky, pohlednice, štočky, cenné papíry, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_39, 
       dříve ZP2015_ENTITY_ROLE_13 - autor výtvarné a obrazové stránky,
       dříve ZP2015_ENTITY_ROLE_14 - autor výtvarné stránky
   * - typové označení a název výrobku a typové stavby
     - `` ``
     - 5.10.1 - technické výkresy
     - ZP2015_ENTITY_ROLE_63
   * - účinkující
     - ``PERFORMER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_43
   * - vydavatel
     - ``PUBLISHER_OWNER``
     - 5.3.1, 5.19.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), cenné papíry, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_15
   * - vydavatel/nakladatel
     - ``PUBLISHER``
     - 5.6.1, 5.9.1, 5.11.2, 5.16.1, 5.17.1, 5.18.1 - hudebniny, mapy (mapová díla, atlasy), grafické listy, pohlednice, plakáty, štočky
     - ZP2015_ENTITY_ROLE_16
   * - výrobce
     - ``MANUFACTURER``
     - 5.4.1, 5.7.6, 5.10.1, 5.21.1, 5.22.1 - úřední knihy (registraturní pomůcky, kartotéky), typáře (otisky, kopie otisků), technické výkresy, faleristické předměty, numizmatické předměty
     - ZP2015_ENTITY_ROLE_53, dříve ZP2015_ENTITY_ROLE_54, dříve ZP2015_ENTITY_ROLE_55
   * - výrobce nosiče záznamu
     - ``MANUFACTURER_CARRIER``
     - 5.12.1, 5.13.2, 5.9.1, 5.14.2, 5.15.1 - fotografické archiválie, kinematografické filmy, mapy (mapová díla, atlasy), zvukové archiválie, tisky
     - ZP2015_ENTITY_ROLE_50
   * - zpracovatel nosiče záznamu
     - ``PROCESSOR_CARRIER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_49
   * - zvuk/zvukař
     - ``SOUND``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
     - ZP2015_ENTITY_ROLE_42
   * - žadatel
     - ``APPLICANT``
     - 5.3.1 - listiny (před i po roce 1850)
     - ZP2015_ENTITY_ROLE_22




K zapracování z Elza
=========================


.. code-block:: xml

    <item-spec code="ZP2015_ENTITY_ROLE_12">
        <name>autor triků a speciálních efektů</name>
        <description>5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PARTY_GROUP"/>
            <item-aptype register-type="PERSON"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_73">
        <name>vyznamenání/cena</name>
        <description>vyznamenání nebo cena</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="ARTWORK"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <!-- zastaralé, bude nahrazeno místem vydání -->
    <item-spec code="ZP2015_ENTITY_ROLE_59">
        <name>místo vydání dokumentů</name>
        <description>zastaralé, bude nahrazeno místem vydání</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="GEO"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_66">
        <name>osoba/bytost zachycená jednotkou popisu</name>
        <description>všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PERSON"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_67">
        <name>rod/rodina zachycený/á jednotkou popisu</name>
        <description>všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="DYNASTY"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_68">
        <name>korporace zachycená jednotkou popisu</name>
        <description>všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PARTY_GROUP"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_69">
        <name>událost zachycená jednotkou popisu</name>
        <description>všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="EVENT"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_70">
        <name>dílo/výtvor zachycené/ý jednotkou popisu</name>
        <description>platné pro všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="ARTWORK"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_71">
        <name>geografický objekt zachycený jednotkou popisu</name>
        <description>platné pro všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="GEO"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_72">
        <name>obecný pojem vztahující se k jednotce popisu</name>
        <description>platné pro všechny typy a podtypy archiválií</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="TERM"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_77">
        <name>osoba jmenovaná / ustanovená do funkce</name>
        <description>osoba jmenovaná / ustanovená do funkce</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PERSON"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_78">
        <name>funkce</name>
        <description>funkce</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="TERM"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_79">
        <name>korporace výkonu funkce</name>
        <description>korporace výkonu funkce</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PARTY_GROUP"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_80">
        <name>místo výkonu funkce</name>
        <description>místo výkonu funkce</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="GEO"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <!-- Rozdíl mezi rolí 5 a 6? -->
    <item-spec code="ZP2015_ENTITY_ROLE_5">
        <name>skladatel</name>
        <description>5.6.1 - hudebniny (dříve i autor hudební složky)</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PARTY_GROUP"/>
            <item-aptype register-type="PERSON"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_82">
        <name>matriční místo</name>
        <description>matriční místo, platné pro podtyp matiky</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="GEO"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_83">
        <name>sekundární klasifikace</name>
        <description>sekundární klasifikace pro dotazy na web</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="TERM_GENERAL"/>
            <item-aptype register-type="TERM_TAXONOMY"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>
    <item-spec code="ZP2015_ENTITY_ROLE_81">
        <name>katalogizační záznam</name>
        <description>záznam v katalogu</description>
        <shortcut></shortcut>
        <item-aptypes>
            <item-aptype register-type="PERSON"/>
            <item-aptype register-type="PARTY_GROUP"/>
            <item-aptype register-type="EVENT"/>
            <item-aptype register-type="DYNASTY"/>
        </item-aptypes>
        <item-type-assign code="ZP2015_ENTITY_ROLE"/>
    </item-spec>