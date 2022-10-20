.. _ead_ap_relation:

===================
Role entit
===================

Další popis viz ZP: 
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
Role entity se ukládá do atributu `linkrole <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_. 
Tabulka rolí je uvedena níže v části: :ref:`ead_ap_relation_roles`.
Uživatelsky čitelné označení role se zapisuje do atributu `linktitle <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linktitle>`_.
Čitelné označení umožňuje uživatelům a publikačním systémům roli 
přímo interpretovat zatímco atribut `linkrole <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linkrole>`_
ji umožňuje interpretovat strojově, zajistit překlady.
V případě dílčí specializace role v předávajícím systému je v atributu 
`linktitle <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-linktitle>`_ možné
tuto odlišnost zachytit.


Entita z třídy CPF
======================

Pokud je odkazovaná entita z třídy: *osoba/bytost*, *rod/rodina*, *korporace*
či *událost* je tato zachycena dle definice v části :ref:`ead_ap_eac_cpf`. 
Současně je povinně uveden atribut ``relationtype="cpfrelation"``.
Odkaz na takovouto entitu je realizován pomocí elementu
`<descriptivenote> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-descriptivenote>`_
obsahující jeden element `<p> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-p>`_
s odkazem `<ptr> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ptr>`_ na entitu.

Preferované označení odkazované entity je vždy zaznamenáno v elementu 
`<relationentry> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relationentry>`_.


Příklad
------------

.. code-block:: xml

      <ead:relation relationtype="cpfrelation" 
                    linktitle="autor" 
                    linkrole="AUTHOR">
        <ead:relationentry>Neruda, Jan (1834-1891)</ead:relationentry>
        <ead:descriptivenote>
          <ead:p>
            <ead:ptr target="ap154" />
          </ead:p>
        </ead:descriptivenote>
      </ead:relation>

.. _ead_ap_relation_other:


Ostatní entity
=================================

Ostatní entity jsou ze tříd *geografická entita*, 
*dílo/výtvor* nebo *obecný pojem*. Tyto entity se uvádí vždy
v :ref:`rejstříku entit <ead_ap_rejstrik>`.

Současně je povinně uveden atribut ``relationtype="resourcerelation"``.
Odkaz na takovouto entitu je realizován pomocí elementu
`<descriptivenote> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-descriptivenote>`_
obsahující jeden element `<p> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-p>`_
s odkazem `<ptr> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-ptr>`_ na entitu.

Preferované označení odkazované entity je vždy zaznamenáno v elementu 
`<relationentry> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-relationentry>`_.


.. code-block:: xml

      <ead:relation relationtype="resourcerelation" 
                    linktitle="autorské dílo" 
                    linkrole="ARTWORK">
        <ead:relationentry>Babička s dětmi (Otto Gutfreund : Ratibořice, Česká Skalice, Náchod, Česko : sousoší)</ead:relationentry>
        <ead:descriptivenote>
          <ead:p>
            <ead:ref target="ap157" />
          </ead:p>
        </ead:descriptivenote>
      </ead:relation>


.. _ead_ap_relation_roles:

Definice rolí
==============

.. list-table:: Mapování rolí entit
   :widths: 20 10 20
   :header-rows: 1

   * - Jméno role (linktitle)
     - Označení v EADu (linkrole)
     - Poznámka
   * - autor
     - ``AUTHOR``
     - autor výkresu
   * - autor dialogu
     - ``AUTHOR_DIALOGS``
     - 5.13.2, 5.14.2 pro kinematografické filmy, zvukové archiválie
   * - autor doprovodného textu
     - ``AUTHOR_ACCOMP_TEXT``
     - 5.6.1, hudebniny
   * - autor hudby/skladatel
     - ``COMPOSER``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
   * - autor choreografie/choreograf
     - ``CHOREOGRAPHER``
     - 5.13.2, kinematografické filmy
   * - autor komentáře
     - ``AUTHOR_COMMENT``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
   * - autor námětu
     - ``AUTHOR_TOPIC``
     - 5.13.2, 5.14.2, kinematografické filmy, zvukové archiválie
   * - autor textové složky/textař
     - ``LYRICIST``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - autor textu
     - ``AUTHOR_TEXT``
     - 5.4.1, 5.5.1, 5.6.1, 5.9.1, 5.15.1, 5.17.1, 5.18.1 - úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, mapy (mapová díla, atlasy), tisky, plakáty, štočky
   * - autor triků a speciálních efektů
     - ``TRICKS_EFFECTS``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - autorské dílo
     - ``ARTWORK``
     - :ref:`ead_item_types_aut_dilo`
   * - vydavatel
     - ``PUBLISHER_OWNER``
     - 5.3.1, 5.19.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), cenné papíry, faleristické předměty, numizmatické předměty
   * - vydavatel/nakladatel
     - ``PUBLISHER``
     - 5.6.1, 5.9.1, 5.11.2, 5.16.1, 5.17.1, 5.18.1 - hudebniny, mapy (mapová díla, atlasy), grafické listy, pohlednice, plakáty, štočky
   * - pečetitel
     - ``SEALER``
     - 5.3.1 - listiny (před i po roce 1850)
   * - produkční společnost/producent
     - ``PRODUCER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - objednavatel/příjemce
     - ``CLIENT``
     - 5.5.1, 5.6.1, 5.9.1, 5.13.2, 5.14.2 - rukopisy, hudebniny, mapy (mapová díla, atlasy), kinematografické filmy, zvukové archiválie
   * - distributor
     - ``DISTRIBUTOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - příjemce
     - ``RECIPIENT``
     - 5.3.1, 5.11.2, 5.12.1, 5.15.1, 5.16.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), grafické listy, fotografické archiválie, tisky, pohlednice, faleristické předměty, numizmatické předměty
   * - žadatel
     - ``APPLICANT``
     - 5.3.1 - listiny (před i po roce 1850)
   * - držitel cenného papíru
     - ``HOLDER_SECURITY``
     - 5.19.1 - cenné papíry
   * - odesílatel
     - ``SENDER``
     - 5.12.1, 5.16.1 - fotografické archiválie, pohlednice
   * - schvalovatel technického výkresu
     - ``APPROVER``
     - 5.10.1 - technické výkresy
   * - stavitel
     - ``BUILDER``
     - 5.10.1 - technické výkresy
   * - režisér
     - ``DIRECTOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - scénárista
     - ``SCRIPTWRITER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - kameraman
     - ``CAMERAMAN``
     - 5.13.2 - kinematografické filmy
   * - interpret hudby
     - ``MUSIC_INTERPRETER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - fotograf
     - ``PHOTOGRAPHER``
     - 5.9.1, 5.12.1, 5.15.1, 5.16.1, 5.17.1, 5.18.1 - mapy (mapová díla, atlasy), fotografické archiválie, tisky, pohlednice, plakáty, štočky
   * - redaktor
     - ``REDACTOR``
     - 5.9.1, 5.15.1 - mapy (mapová díla, atlasy), tisky<
   * - kartograf
     - ``CARTOGRAPHER``
     - 5.9.1, 5.15.1, 5.18.1 - mapy (mapová díla, atlasy), tisky, štočky
   * - editor
     - ``EDITOR``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - kreslič
     - ``DRAFTSMAN``
     - 5.9.1, 5.10.1 - mapy (mapová díla, atlasy), technické výkresy
   * - majitel typáře
     - ``OWNER_AUTHORIZED``
     - 5.7.6 - typáře (otisky, kopie otisků)
   * - tvůrce technického zpracování
     - ``CREATOR_TECHNICAL``
     - 5.11.2 - grafické listy
   * - tvůrce výtvarné stránky
     - ``CREATOR_ARTWORK``
     - 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.11.2, 5.13.2, , 5.14.2, 5.15.1, 5.16.1, 5.18.1, 5.19.1, 5.21.1, 5.22.1 - úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), grafické listy, kinematografické filmy, zvukové archiválie, tisky, pohlednice, štočky, cenné papíry, faleristické předměty, numizmatické předměty
   * - dramaturg
     - ``DRAMATURG``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - střih/střihač
     - ``CUTTER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - zvuk/zvukař
     - ``SOUND``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - účinkující
     - ``PERFORMER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - překladatel
     - ``TRANSLATOR``
     - 5.5.1, 5.13.2, 5.14.2, 5.15.1 - rukopisy, kinematografické filmy, zvukové archiválie, tisky
   * - lektor
     - ``LECTOR``
     - 5.15.1 - tisky
   * - svědek
     - ``WITNESS``
     - 5.3.1 - listiny (před i po roce 1850)
   * - ručitel (rukojmě)
     - ``GUARANTOR``
     - 5.3.1 - (před i po roce 1850)
   * - písař
     - ``SCRIBE``
     - 5.3.1, 5.4.1, 5.5.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy
   * - zpracovatel nosiče záznamu
     - ``PROCESSOR_CARRIER``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - výrobce nosiče záznamu
     - ``MANUFACTURER_CARRIER``
     - 5.12.1, 5.13.2, 5.9.1, 5.14.2, 5.15.1 - fotografické archiválie, kinematografické filmy, mapy (mapová díla, atlasy), zvukové archiválie, tisky
   * - tiskárna/tiskař
     - ``PRINTER``
     - 5.6.1, 5.9.1, 5.11.2, 5.15.1, 5.16.1, 5.17.1, , 5.19.1 - hudebniny, mapy (mapová díla, atlasy), grafické listy, tisky, pohlednice, plakáty, , cenné papíry
   * - výrobce
     - ``MANUFACTURER``
     - 5.4.1, 5.7.6, 5.10.1, 5.21.1, 5.22.1 - úřední knihy (registraturní pomůcky, kartotéky), typáře (otisky, kopie otisků), technické výkresy, faleristické předměty, numizmatické předměty
   * - místo natáčení
     - ``LOCATION_SHOOTING``
     - 5.13.2, 5.14.2 - kinematografické filmy, zvukové archiválie
   * - místo vydavatele
     - ``LOCATION_PUBLISHER``
     - 5.21.1, 5.22.1 - faleristické předměty, numizmatické předměty
   * - místo vydání
     - ``LOCATION_PUBLISHING``
     - 5.3.1, 5.7.6, 5.15.1, 5.17.1, 5.16.1, 5.19.1 - listiny (před i po roce 1850), typáře (otisky, kopie otisků), tisky, plakáty, pohlednice, cenné papíry
   * - místo výroby jednotky popisu
     - ``PLACE_MANUFACTURE``
     - 5.13.2, 5.14.2, 5.21.1, 5.22.1 - kinematografické filmy, zvukové archiválie, faleristické předměty, numizmatické předměty
   * - místo vzniku jednotky popisu
     - ``PLACE_ORIGIN``
     - 5.3.1, 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.10.1, 5.11.2, 5.12.1, 5.18.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), technické výkresy, grafické listy, fotografické archiválie, štočky
   * - místo vzniku předlohy popisované kopie
     - ``PLACE_COPY_CREATION``
     - 5.3.1, 5.4.1, 5.5.1, 5.6.1, 5.7.6, 5.9.1, 5.10.1, 5.11.2, 5.15.1, 5.16.1, 5.17.1, 5.18.1, 5.19.1, 5.21.1, 5.22.1 - listiny (před i po roce 1850), úřední knihy (registraturní pomůcky, kartotéky), rukopisy, hudebniny, typáře (otisky, kopie otisků), mapy (mapová díla, atlasy), technické výkresy, grafické listy, tisky, pohlednice, plakáty, štočky, cenné papíry, faleristické předměty, numizmatické předměty
   * - typové označení a název výrobku a typové stavby
     - ``TYPE``
     - 5.10.1 - technické výkresy
   * - související entita
     - ``ENTITY``
     - všechny třídy a podtřídy entit
   * - vyznamenání/cena
     - ``AWARD``
     - vyznamenání nebo cena
   * - nositel vyznamenání/ceny
     - ``PERSON_AWARDED``
     - nositel vyznamenání nebo ceny
   * - navrhovatel
     - ``PROPONENT``
     - navrhovatel
   * - předávající
     - ``PERSON_HANDING``
     - předávající
   * - osoba jmenovaná / ustanovená do funkce
     - ``PERSON_APPOINTED``
     - osoba jmenovaná / ustanovená do funkce
   * - funkce
     - ``POSITION``
     - funkce
   * - korporace výkonu funkce
     - ``CORPORATION_ASSIGNED``
     - korporace výkonu funkce
   * - místo výkonu funkce
     - ``LOCATION_ASSIGNED``
     - místo výkonu funkce
   * - matriční místo
     - ``PLACE_REGISTER``
     - matriční místo, platné pro podtyp matiky
   * - sekundární klasifikace
     - ``CLASSIFICATION``
     - sekundární klasifikace pro dotazy na web
   * - opisovač
     - ``COPYIST``
     - opisovač
   * - vlastník
     - ``OWNER``
     - vlastník
   * - místo fotografování
     - ``LOCATION_PHOTOGRAPHING``
     - místo fotografování
   * - odborná spolupráce
     - ``COOPERATION``
     - odborná spolupráce
   * - místo předání
     - ``PLACE_HANDING``
     - místo předání
   * - obrazově a/nebo zvukově zachycená entita
     - ``CAPTURED_ENTITY``
     - obrazově a/nebo zvukově zachycená entita
