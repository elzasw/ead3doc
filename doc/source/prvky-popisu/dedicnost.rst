.. _ead_item_types_inheritance:

========================
Dědičnost prvků popisu
========================

Prvky popisu jsou uváděny vždy v rámci dané :ref:`úrovně popisu <ead_archdesc_hierarchy>`, 
ale pro jejich plnohodnotnou interpretaci je nutné je posuzovat i v kontextu 
prvků popisu uvedených na jiných úrovních (viz princip dědičnosti a neopakování informací). 
Způsob zacházení s dědičností závisí na zvolené metodě tvorby archivního popisu. 
Za účelem dosažení jednotného a jednoznačného výkladu dat v EAD je pro některé 
prvky popisu explicitně popsán způsob jejich zápisu napříč úrovněmi.

V rámci výměnného formátu je možné u určených prvků popisu informace z vyšších 
úrovní explicitně uvádět i na nižších úrovních popisu. Toto pravidlo realizuje 
formu dědičnosti. Uplatnění dědičnosti se zaznamená uvedením atributu 
``altrender=”inherited”``. Pravidlo lze použít jen u uvedených prvků 
popisu uvedených v kapitole :ref:`ead_item_types_inheritance_inhtypes`. 


.. _ead_item_types_inheritance_inhtypes:

Prvky popisu s uvedenou dědičností
====================================

Prvky popisu uvedené v této části jsou vždy uváděny na všech úrovních, 
kde se mají uplatnit, tj. jedná se o explicitní uplatnění dědičnosti. 
Explicitní uplatnění dědičnosti znamená, že hodnota je uvedena také 
na nižší úrovni, přestože je shodným způsobem uvedena na úrovni vyšší. 
Uplatnění dědičnosti se zaznamená uvedením atributu ``altrender="inherited"``.

Prvky popisu s explicitním uplatněním dědičnosti:

 * :ref:`ead_item_types_unitdatestructured`
 * :ref:`ead_ap_originator`
 * :ref:`ead_item_types_langs`
 * :ref:`ead_item_types_container`
 * :ref:`ead_item_types_ex_kopii`
 * :ref:`ead_ap_relation`
 * :ref:`ead_item_types_aut_dilo`


Prvek s jinou formou dědičnosti
====================================

Jedná se o prvek popisu, u něhož dědičnost není přímo zachycena ve výstupním formátu.

Obsah, regest
---------------

Prvek popisu :ref:`ead_item_types_unittitle` je obvykle nutné interpretovat 
i v kontextu hodnot uvedených na vyšších úrovních archivního popisu 
či způsobu jeho prezentace. Proto nedochází k explicitnímu přenosu těchto 
hodnot na nižší úrovně. Způsob zobrazení a indexace tohoto prvku je záležitostí 
konkrétní prezentační platformy pro badatele.
