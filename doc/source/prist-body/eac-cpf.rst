.. _ead_ap_eac_cpf:

===================
Profil EAC-CPF
===================

Standard `EAC CPF <https://eac.staatsbibliothek-berlin.de/>`_
je určen pro popis archivních entit tříd *osoba/bytost*, *rod/rodina*
a *korporace*. V českém prostředí se navíc přidává *událost* jako 
dočasná korporace.

Strukturovaně popsaná entita je uložena v elementu 
`<objectxmlwrap> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-objectxmlwrap>`_
v části `<control>/<sources>/<source> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_.
Element `<source> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-source>`_ 
povinně obsahuje atribut ``id="...."`` umožňující
jeho odkazování v rámci XML dokumentu.


Identifikátor entity
========================

Identifikátor entity je uložen v elementu `<recordId> <https://eac.staatsbibliothek-berlin.de/schema/taglibrary/cpfTagLibrary2019_EN.html#elem-recordId>`_.
Jedná se o trvalý lokální identifikátor entity v rámci daného archivu.

Identifikátor entity v CAMu
============================

Pokud je entita uložena v systému CAM je její identifikátor 
předán v elementu `<otherRecordId> <https://eac.staatsbibliothek-berlin.de/schema/taglibrary/cpfTagLibrary2019_EN.html#elem-otherRecordId>`_
s povinně uvedenou hodnotou atributu ``localType="CAM"``.


.. _ead_ap_eac_cpf_priklad:

Příklad
===========

.. code-block:: xml

  <ead:source id="ap154">
  <ead:objectxmlwrap>
    <eac:eac-cpf>
      <eac:control>
        <eac:recordId>8c74c33f-a49f-49ab-b500-0021641b2faa</eac:recordId>
        <eac:otherRecordId localType="CAM">33537</eac:otherRecordId>
      </eac:control>
      <eac:cpfDescription>
        <eac:identity>
          <eac:entityType>person</eac:entityType>
          <eac:nameEntryParallel>
          <eac:nameEntry>
            <eac:part>Neruda, Jan (1834-1891)</eac:part>
            <eac:preferredForm>ZP2022_SERIALIZED</eac:preferredForm>
          </eac:nameEntry>
          <eac:nameEntry>
            <eac:part localType="MAIN">Neruda</eac:part>
            <eac:part localType="MINOR">Jan</eac:part>
            <eac:part localType="DATES">1834-1891</eac:part>
          </eac:nameEntry>
          </eac:nameEntryParallel>
        </eac:identity>
      </eac:cpfDescription>
    </eac:eac-cpf>
  </ead:objectxmlwrap>
  </ead:source>
