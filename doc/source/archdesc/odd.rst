.. _ead_archdesc_odd:

==============================
Úvod starší archivní pomůcky
==============================

Schéma umožňuje uložení nestrukturovaného úvodu starší archivní pomůcky 
(:ref:`ead_control_localcontrol_rules`, hodnota: ``CZ_ZP1958``).
Pro toto uložení je určen element :ead-el:`odd`.
Pomocí atributu `localtype="FINDING_AID_INTRO" <https://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
se určí, že se jedná o nestrukturovaný úvod. Pro nové pomůcky 
(:ref:`ead_control_localcontrol_rules`, hodnota: ``CZ_ZP2013``) se strukturovaným
způsobem popisu se element nesmí používat.

Element se uvádí jen v kořenovém elementu :ref:`ead_archdesc_fonds`.

Element obsahuje právě jeden podřízený element :ead-el:`p` 
obsahující text rozdělený na odstavce.


Příklad odd
============

.. code-block:: xml

  <ead:archdesc level="fonds">
    ...
    <ead:odd localtype="FINDING_AID_INTRO">
      <ead:p>První odstavec úvodu ...
  Druhý odstavec úvodu ...
      </ead:p>
    </ead:odd>
    ...
  </ead:archdesc>

