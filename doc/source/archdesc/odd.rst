.. _ead_archdesc_odd:

Úvod starší archivní pomůcky
==============================

Schéma umožňuje uložení nestrukturovaného úvodu starší archivní pomůcky.
Pro toto je určen element `<odd> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-odd>`_.
Pomocí atributu `localtype="FINDING_AID_INTRO" <http://www.loc.gov/ead/EAD3taglib/EAD3.html#attr-localtype>`_
se určí, že se jedná o nestrukturovaný úvod. Pro nové pomůcky se strukturovaným
způsobem popisu by se element neměl používat.

Element se uvádí jen v kořenovém elementu :ref:`ead_archdesc_fonds`.

Element obsahuje podřízené elementy `<p> <http://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-p>`_ 
obsahující text rozdělený na odstavce.

Příklad:

.. code-block:: xml

  <ead:archdesc level="fonds">
    <ead:odd localtype="FINDING_AID_INTRO">
      <ead:p>První odstavec úvodu ...</ead:p>
      <ead:p>Druhý odstavec úvodu ...</ead:p>
    </ead:odd>
    ...
  </ead:archdesc>
