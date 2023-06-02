.. _ead_item_types_orientace:

===================================================
Orientace z hlediska světových stran
===================================================

Další popis viz: ZP 5.2.7 Orientace z hlediska světových stran

Orientace z hlediska světových stran se uvádí v elementu 
`<materialspec> <https://www.loc.gov/ead/EAD3taglib/EAD3.html#elem-materialspec>`_
s uvedeným atributem ``localtype="ORIENTATION"``. 
Orientace se zapisuje jako prostý text.


.. code-block:: xml
   :caption: Příklad uvedení orientace z hlediska světových stran

   <ead:did>
      <ead:materialspec localtype="ORIENTATION">na sever</ead:materialspec>
   </ead:did>
