.. index::
    single: Style manager

.. _vector_style_manager:

**********************************************
Style Manager (Style များစီမံခန့်ခွဲသည့်အရာ)
**********************************************


.. only:: html

   .. contents::
      :local:

Style Manager dialog (Style များ စီမံခန့်ခွဲသည့် dialog)
=========================================================

:guilabel:`Style Manager` သည် ယေဘူယျ style item များကို စီမံခန့်ခွဲနိုင်ပြီး ဖန်တီးနိုင်သည့် နေရာလည်း ဖြစ်သည်။ ၄င်းတို့သည် feature များ၊ layer များ သို့မဟုတ်
print layout များကို symbolize (သင်္ကေတပြုလုပ်) လုပ်နိုင်သည့် သင်္ကေတများ၊ color ramp (ရောင်စဉ်တန်း) များ၊ text format များ သို့မဟုတ် label setting များဖြစ်ကြသည်။ ၄င်းတို့ကို အသုံးပြုသူပရိုဖိုင် 
:ref:`user profile <user_profiles>` အောက်တွင်ရှိသည့် :file:`symbology-style.db` database တွင် သိုလှောင်ထားပြီး ထို profile တွင် ဖွင့်ထားသည့် project file များအားလုံးကို မျှ‌‌‌ဝေထားသည်။
:guilabel:`Style Manager` dialog ၏ export/import လုပ်ဆောင်နိုင်မှုကြောင့် style item များကို တခြားတွင်လည်း မျှဝေပြီး အသုံးပြုနိုင်သည်။

Modeless dialog ကို အောက်ဖော်ပြပါတခုခုနှင့် ဖွင့်နိုင်ပါသည်-

* :menuselection:`Settings -->` မှ |styleManager| :menuselection:`Style
  Manager...` ကို ဖွင့်ပါ။
* Project toolbar မှ |styleManager| :sup:`Style Manager` ခလုတ်ကို နှိပ်ပါ။
* သို့မဟုတ် vector တစ်ခု၏ :menuselection:`Layer Properties -->` menu (:ref:`သင်္ကေတတစ်ခုအား ပြင်ဆင်နေစဉ် <symbol-selector>` သို့မဟုတ် :ref:`စာသားတစ်ခုအား format ပြုလုပ်နေစဉ် <showlabels>`) မှ |styleManager| :sup:`Style Manager` ခလုတ်ကို နှိပ်ပါ။

.. _figure_style_manager:

.. figure:: img/stylemanager.png
   :align: center

   Style Manager


.. index:: Style items
.. _group_symbols:

Organizing style items (Style items များ စီစဉ်ဖွဲ့စည်းခြင်း)
-------------------------------------------------------------

:guilabel:`Style Manager` dialog သည် tab များဖြင့် ဖွဲ့စည်းထားသည့် item များကို အစမ်းကြည့်ရှုရန် ၄င်း၏ အလယ်ဗဟိုတွင် frame တစ်ခုအဖြစ် ပြသထားသည်။

* :guilabel:`All` သည် point၊ linear၊ surface သင်္ကေတများ နှင့် label (အညွှန်း) setting များအပြင် ကြိုတင်သတ်မှတ်ထားသည့် color ramp (ရောင်စဉ်တန်း) များနှင့် text format များကိုလည်း စုစည်းထားသည်။
* |pointLayer| :guilabel:`Marker` သည် point သင်္ကေတများအတွက် ဖြစ်သည်။ 
* |lineLayer| :guilabel:`Line` သည် linear သင်္ကေတများအတွက် ဖြစ်သည်။
* |polygonLayer| :guilabel:`Fill` သည် surface သင်္ကေတများအတွက် ဖြစ်သည်။
* |color| :guilabel:`Color ramp`
* |text| :guilabel:`Text format` သည် စာလုံးဖောင့်၊ အရောင်၊ buffer များ၊ အရိပ်များနှင့် စာသားများ၏ နောက်ခံများ (ဆိုလိုသည်မှာ layout များတွင် label setting အားလုံးကို format ပြုလုပ်ခြင်းဖြစ်သည်။)
  :ref:`text formats <text_format>`  များကို ပြင်ဆင်ဆောင်ရွက်ရန် ဖြစ်သည်။
* |labelingSingle| :guilabel:`Label settings` သည် text format များနှင့် label placement၊ priority၊ callout များနှင့် rendering ကဲ့သို့ label setting ပါဝင်သည့် :ref:`label settings
  <showlabels>` များကို ပြင်ဆင်ဆောင်ရွက်ရန် ဖြစ်သည်။
* |legend| :guilabel:`Legend Patch Shapes` သည် :guilabel:`Marker`၊ :guilabel:`Line` နှင့် :guilabel:`Fill` ဂျီဩမေတြီများပါဝင်သည့် စိတ်ကြိုက် legend patch shape များကို ပြင်ဆင်ဆောင်ရွက်ရန် ဖြစ်သည်။
* |3d| :guilabel:`3D Symbols` သည် :ref:`3D Map view <label_3dmapview>` တွင် feature များကို render ပြုလုပ်ရန်အတွက် :ref:`3D properties
  <3dsymbols>` (extrusion ၊ shading ၊ altitude ၊ ...) သင်္ကေတများကို configure (သတ်မှတ်ပြင်ဆင်) ပြုလုပ်ရန်ဖြစ်သည်။

Style များကို ညာဘက်အောက်ခြေရှိ |iconView| :guilabel:`Icon View` သို့မဟုတ်
|openTable| :guilabel:`List View` တွင် ပြုလုပ်နိုင်သည်။ View နှစ်ခုစလုံးတွင် tooltip သည် style ဥပမာများကို ပြသထားသည်။
Icon များ၏ ဘယ်ဘက်မှာရှိသည့် thumbnail size slider သည် သင်္ကေတများကို အကောင်းဆုံး ကြည့်ရှုဖို့ရန်အတွက် dialog တွင် actual
thumbnail size များကို ချိန်ညှိနိုင်ပါသည်။

Item တစ်ခုချင်းစီအတွက် ဘယ်ဘက် panel ရှိ စာရင်းတွင် element များကို မတူညီသည့် အမျိုးအစားများအဖြစ် ပြုလုပ်နိုင်သည်။

* **Favorites** သည် item တစ်ခုကို configure ပြုလုပ်သည့်အချိန်တွင် ပုံသေပြသသည်။ ၄င်းသည် item များ၏ extensible (ဖြန့်ထုတ်နိုင်သော) set တစ်ခုအဖြစ်လည်း ပြသသည်။
* **All** သည် active ဖြစ်နေသည့် အမျိုးအစားများအတွက် ရရှိနိုင်သည့် item များအားလုံးကို စာရင်းပြုလုပ်ထားသည်။
* **Tags** သည် item များကို သတ်မှတ်ရန် အသုံးပြုနိုင်သည့် label စာရင်းကို ပြသသည်။
  Item တစ်ခုသည် တစ်ကြိမ်ထက် ပိုပြီး tag ပြုလုပ်နိုင်သည်။ List ထဲရှိ tag တစ်ခုကို ရွေးချယ်ပြီး ၄င်းနှင့်သက်ဆိုင်သည့် item များကိုသာ ပြသရန် tag များကို update ပြုလုပ်ပေးသည်။
  Item များကို attach လုပ်နိုင်ရန်အတွက် tag တစ်ခုဖန်တီးရန် :guilabel:`Add Tag...` ခလုတ်ကို နှိပ်ပါ။ သို့မဟုတ် မည်သည့် tag အကြောင်းအရာဆိုင်ရာ menu မှ |symbologyAdd| :guilabel:`Add Tag...` ကိုရွေးပါ။
* **Smart Group** သည် conditions (သတ်မှတ်အခြေအနေများ) နှင့်အညီ ၄င်း၏ သင်္ကေတများကို  dynamically ရယူသည်။ (ဥပမာအနေဖြင့် :numref:`figure_smart_group` ကို ကြည့်ပါ)။ 
  Smart group များကို ဖန်းတီးရန် :guilabel:`Add Smart Group...` ခလုတ်ကို နှိပ်ပါ။ dialog box မှာ ရွေးချယ်ရန် item များကို filter လုပ်ရန်အတွက် expression တစ်ခုကို ပြုလုပ်နိုင်သည်။
  (သီးသန့် tag တစ်ခု၊ နာမည် string တစ်ခု စသည်တို့ပါဝင်သည်)။ အခြေအနေ(များ) နှင့်ကိုက်ညီသည့် သင်္ကေတများ၊ color ramp များ၊ text format များ သို့မဟုတ် label setting များကို smart group ထဲသို့ အလိုအလျောက် ထည့်သွင်းပေးသည်။ 


.. _figure_smart_group:

.. figure:: img/create_smartgroup.png
   :align: center

   Smart Group တစ်ခု ဖန်တီးခြင်း

Tag များ နှင့် smart group များသည် အပြန်အလှန်ဆက်နွယ်မှု မရှိပါ။ ၄င်းတို့သည် style element များကို စုစည်းနိုင်သော မတူညီသည့် နည်းလမ်းနှစ်မျိုးဖြစ်သည်။  
Smart group များသည် ထည့်သွင်းကန့်သတ်ချက်ပေါ် မူတည်ပြီးတော့ ၄င်းတို့၏ item များကို အလိုအလျောက်ရယူပြီး tag များကို အသုံးပြုသူက ကိုယ်တိုင်ထည့်ပေးရသည်။ 
ထိုအမျိုးအစားတစ်ခုခုကို edit ပြုလုပ်ရန် အောက်ပါအတိုင်း ပြုလုပ်နိုင်သည်-

* Item များကို ရွေးပါ။ right-click နှိပ်ပြီး :menuselection:`Add to Tag -->` ကို ရွေးပါ။ ထို့နောက် tag name ရွေးပါ သို့မဟုတ် tag အသစ်တစ်ခုဖန်တီးပါ။
* Tag ကို ရွေးပြီး :menuselection:`Modify group... --> Attach Selected Tag to Symbols` ကို နှိပ်ပါ။ item တစ်ခုချင်းစီ၏ဘေးတွင် ရွေးချယ်နိုင်သည့် check box ပေါ်လာပါမည်။ 
  ရွေးချယ်ပြီးသည့်အခါ :menuselection:`Modify group... --> Finish Tagging` ကို နှိပ်ပါ။
* Smart group ကို ရွေးပြီး :menuselection:`Modify group... --> Edit smart group...`  ကို နှိပ်ပါ။ ထို့နောက် :guilabel:`Smart Group Editor` dialog တွင် configure ပြုလုပ်ပါ။ ၄င်း option ကို smart group ၏ အကြောင်းအရာဆိုင်ရာ menu ထဲမှလည်း ပြုလုပ်နိုင်သည်။

Tag တစ်ခု သို့မဟုတ် smart group ကို ဖယ်ရှားရန် ၄င်းပေါ်မှာ right-click နှိပ်ပြီး |symbologyRemove|
:guilabel:`Remove` ခလုတ်ကို နှိပ်ပါ။ category ထဲတွင် group လုပ်ထားသည့် item များကို မဖျက်ပါ။

Adding, editing or removing an item (Item တစ်ခုကို ထည့်သွင်းခြင်း၊ ပြင်ဆင်တည်းဖြတ်ခြင်း သို့မဟုတ် ဖယ်ရှားခြင်း)
----------------------------------------------------------------------------------------------------------------

အပေါ်တွင် မြင်တွေ့ရသည့်အတိုင်း active ဖြစ်နေသော အမျိုးအစားများ (tag ၊ smart group ၊ favorites...) ပေါ်မူတည်ပြီး style element များကို ဖော်ပြထားသည်။ Tab တစ်ခု ဖွင့်ပြီး အောက်ပါအတိုင်း ပြုလုပ်နိုင်သည်-

* Item အသစ်များထည့်သွင်းခြင်း - |symbologyAdd| :sup:`Add item` ခလုတ်ကို နှိပ်ပြီး
  :ref:`symbols <symbol-selector>` ၊ :ref:`color ramps <color-ramp>` သို့မဟုတ် :ref:`text format and label <showlabels>` builder description ကို configure ပြုလုပ်ပါ။
* ရှိပြီးသား item တစ်ခုကို Modify ပြုလုပ်ခြင်း - Item တစ်ခုကို ရွေးပြီး |symbologyEdit| :sup:`Edit item` ခလုတ်ကို နှိပ်ပါ။ ထို့နောက် item အသစ်ထည့်သွင်းခြင်းကဲ့သို့ configure ပြုလုပ်ပါ။ 
* ရှိပြီးသား item များကို delete (ဖျက်ခြင်း) လုပ်ခြင်း - Element တစ်ခု delete လုပ်ရန်အတွက် delete လုပ်လိုသည့် element ကို ရွေးပြီး |symbologyRemove| :sup:`Remove item` နှိပ်ပါ။ (right-click နှိပ်ပြီးလည်း ပြုလုပ်နိုင်သည်) Item သည် local database မှ ဖယ်ရှားသွားလိမ့်မည်။

:guilabel:`All` tab သည် item အမျိုးမျိုးကို ရွေးချယ်နိုင်သည်။

ရွေးချယ်ထားသော item ပေါ်တွင် Right-click နှိပ်ခြင်းဖြင့် လုပ်ဆောင်နိုင်သည်များမှာ-

* :guilabel:`Add to Favorites` (Favorite များထဲသို့ ပေါင်းထည့်ခြင်း)၊
* :guilabel:`Remove from Favorites` (Favorite များထဲမှ ဖယ်ရှားခြင်း)၊
* :menuselection:`Add to Tag -->` နှင့် သင့်လျော်သော tag ကို ရွေးပါ။ သို့မဟုတ် အသစ်တစ်ခု ဖန်တီးပါ။ ရှိပြီးသား tag များကို စစ်ဆေးပါ။
* :guilabel:`Clear Tags` - Tag ထဲရှိ သင်္ကေတများကို ဖယ်ထုတ်ခြင်း
* :guilabel:`Remove Item(s)` (Item များအား ဖယ်ရှားခြင်း)
* :guilabel:`Edit Item` - Edit ပြုလုပ်လိုသည့် item တစ်ခုပေါ်တွင် right-click နှိပ်ပါ။
* :guilabel:`Copy Item` (Item ကို ကူးယူခြင်း)
* :guilabel:`Paste Item ...` - style manager ထဲမှ category တစ်ခုခုထဲတွင် သို့မဟုတ် QGIS ထဲရှိ တစ်နေရာရာတွင် (symbols သို့မဟုတ် color buttons ) paste လုပ်ပါ။
* :guilabel:`Export Selected Symbol(s) as PNG...` (သင်္ကေတများအတွက်သာ ဖြစ်သည်။)
* :guilabel:`Export Selected Symbol(s) as SVG...` (သင်္ကေတများအတွက်သာ ဖြစ်သည်။)

.. _share_symbols:

Sharing style items (Style item များကို မျှဝေခြင်း)
----------------------------------------------------

Style Manager dialog ၏ ဘယ်ဘက်အောက်ခြေတွင်ရှိသည့် |sharing| :guilabel:`Import/Export` tool သည် symbolများ၊ color ramp များ၊ text
format များနှင့် label setting များကို share ပြုလုပ်နိုင်သည်။ ထိုလုပ်ဆောင်မှုများကို item များပေါ်တွင် right click နှိပ်ပြီးလည်း ပြုလုပ်နိုင်သည်။

Exporting items (Item များကို Export ပြုလုပ်ခြင်း)
...................................................

Item များကို :file:`.XML` ဖိုင်အဖြစ် export ပြုလုပ်နိုင်သည်။

#. |sharing| :guilabel:`Import/Export` drop-down menu ထဲရှိ
   |fileSave| :guilabel:`Export Item(s)...` ကို ရွေးပါ။
#. Export ပြုလုပ်လိုသော item များကို ရွေးချယ်ရာတွင် mouse ဖြင့်သော်လည်းကောင်း၊ tag တစ်ခုကို ရွေးချယ်၍သော်လည်းကောင်း သို့မဟုတ် ရှိပြီးသား group တစ်ခုချင်းအလိုက်လည်း ပြုလုပ်နိုင်သည်။
#. ရွေးချယ်ပြီးပါက :guilabel:`Export` ကို နှိပ်ပါ။ ဖိုင် သိမ်းဆည်းမည့် နေရာကို ပြပါလိမ့်မည်။ ရွေးချယ်ထားသည့် item များပါဝင်သော XML format တစ်ခုကို ရရှိပါမည်။
   ဤ ဖိုင်ကို တစ်ခြားအသုံးပြုသူ၏ style library တွင် ထည့်သွင်းအသုံးပြုနိုင်သည်။

.. _figure_symbol_export:

.. figure:: img/export_styles.png
   :align: center

   Style item များကို Export ပြုလုပ်ခြင်း

သင်္ကေတများကို  ရွေးချယ်ပြီး :file:`.PNG` သို့မဟုတ် :file:`.SVG` ဖိုင်အဖြစ် export ပြုလုပ်နိုင်သည်။ :file:`.PNG` သို့မဟုတ် :file:`.SVG` export ပြုလုပ်ခြင်းသည် (ဖိုင် နှစ်ခုစလုံးသည် အခြား style item အမျိုးအစားများအတွက် မရရှိနိုင်ပါ) ပေးထားသည့် folder ထဲမှာပဲ ရွေးချယ်ထားသည့် သင်္ကေတ တစ်ခုစီအတွက် ဖိုင်တစ်ခု ဖန်တီးပေးခြင်းဖြစ်သည်။
SVG folder ကို တခြား အသုံးပြုသူမှ :menuselection:`Settings --> Options -->System` menu ထဲတွင်ရှိသည့် :guilabel:`SVG paths` တွင် ထည့်သွင်းပြီး သင်္ကေတ များကိုတိုက်ရိုက်အသုံးပြုနိုင်သည်။

.. _import_style_items:

Importing items (Item များကို Import ပြုလုပ်ခြင်း)
...................................................

Item အသစ်များကို import လုပ်ခြင်းဖြင့် style library ကို ထပ်တိုးနိုင်သည်။

#. |sharing| :guilabel:`Import/Export` drop-down menu ကိုနှိပ်ပြီး ဘယ်ဘက်အောက်ခြေရှိ
   |fileOpen| :guilabel:`Import Item(s)` ကို ရွေးပါ။
#. Dialog အသစ်တွင်  style item များ၏ source ကို ညွှန်ပြပါ။ (၄င်းသည် disk ပေါ်ရှိ 
   :file:`.xml` ဖိုင် သို့မဟုတ် url ဖိုင် ဖြစ်နိုင်သည်။)
#. Import လုပ်မည့် item များကို |unchecked| :guilabel:`Add to favorites` ထဲထည့်သွင်းရန် အမှန်ခြစ် ဖြုတ်ခြင်းရှိမရှိ ရွေးချယ်ပါ။
#. Import လုပ်ထားသည့် item များနှင့် ဆက်စပ်နေသည့် tag များကို ရှောင်ရှားရန် |unchecked| :guilabel:`Do not import embedded tags` ကို အမှန်ခြစ်ပါ။
#. Item အသစ်များကို အသုံးပြုရန် :guilabel:`Additional tag(s)` ကို နာမည်ပေးပါ။
#. Library သို့ ထည့်သွင်းလိုသည့် သင်္ကေတများကို preview မှ ရွေးပါ။
#. :guilabel:`Import` ကို နှိပ်ပါ။

.. _figure_symbol_import:

.. figure:: img/import_styles.png
   :align: center

   Style item များကို import ပြုလုပ်ခြင်း

.. index::
   pair: Browser; Style items

Using the Browser panel (Browser panel ကို အသုံးပြုခြင်း)
..........................................................

အသုံးပြုသူပရိုဖိုင်၏ style database ထဲသို့ item style များကို :guilabel:`Browser` panel မှ တိုက်ရိုက် import ပြုလုပ်နိုင်သည်။
       
#. Browser ထဲမှ :file:`.xml` style ဖိုင်ကို ရွေးပါ။
#. Map canvas ထဲသို့ Drag-and-drop ဆွဲပါ သို့မဟုတ် right-click နှိပ်ပြီး
   :guilabel:`Import Style...` ကို ရွေးပါ။
#. :ref:`import_style_items` အတိုင်း :guilabel:`Import Items` dialog ကို ဖြည့်ပါ။
#. :guilabel:`Import` နှိပ်ပြီး ရွေးချယ်ထားသော style item များကို
   style database ထဲသို့ ထည့်သွင်းပါ။

Browser တွင်ရှိသည့် style ဖိုင်ကို double-click ပြုလုပ်လိုက်လျှင် ဖိုင်ထဲမှ item များကိုပြသသည့် 
:guilabel:`Style Manager` dialog ပွင့်လာမည်။ ၄င်းတို့ကို ရွေးချယ်ပြီး active ဖြစ်နေသော style
database ထဲသို့ import ပြုလုပ်ရန် :guilabel:`Copy to Default Style...` ကို နှိပ်ပါ။ ၄င်း item များအတွက် tag များသတ်မှတ်နိုင်သည်။ ၄င်း item များကို right-click နှိပ်ပြီး
:guilabel:`Open Style...` command အသုံးပြုခြင်းဖြင့်လည်း ရနိုင်သည်။

.. _figure_symbol_open:

.. figure:: img/open_style_file.png
   :align: center

   Style items ဖိုင်ကို ဖွင့်ခြင်း

Dialog သည် သင်္ကေတတစ်ခုချင်းစီကို :file:`.PNG` or :file:`.SVG` ဖိုင်များအဖြစ် ထုတ်ပေးနိုင်သည်။


Using the online repository (Online သိုလှောင်ခန်းများကို အသုံးပြုခြင်း)
........................................................................

QGIS သည် QGIS အသုံးပြုသူများ share ထားသော style များ စုစည်းထားသည့် repository တစ်ခု ထားရှိပါသည်။ Style များကို https://plugins.qgis.org/styles တွင် ရရှိနိုင်ပြီး
:guilabel:`Style Manager` dialog မှ အောက်ခြေတွင် ရှိသည့်  |search|
:guilabel:`Browse Online Styles` ခလုတ်ကို နှိပ်ခြင်းဖြင့်လည်း ရရှိနိုင်သည်။

Repository ထဲတွင် အောက်ပါတို့ကို ပြုလုပ်နိုင်သည်-

#. အမျိုးအစား သို့မဟုတ် နာမည်ပေါ် အခြေခံပြီး style item များကို ရှာပါ။
#. Style ဖိုင်ကို download ပြုလုပ်ပြီး ၄င်းဖိုင်ကို unzip ပြုလုပ်ပါ။
#. အထက်တွင် ဖော်ပြထားသည့် import နည်းလမ်းများကို အသုံးပြုပြီး :file:`.xml` ဖိုင်ကို QGIS ၏ style database ထဲသို့ ထည့်သွင်းပါ။


.. _color-ramp:

Setting a Color Ramp (ရောင်စဉ်တန်း တစ်ခုကို Setting ပြုလုပ်ခြင်း)
==================================================================

.. index:: Colors
   single: Colors; Color ramp
   single: Colors; Gradient color ramp
   single: Colors; Color brewer
   single: Colors; Custom color ramp

:guilabel:`Style Manager` dialog ထဲရှိ color ramp tab သည် ဘယ်ဘက် panel မှ 
ရွေးချယ်ထားသည့် အမျိုးအစားပေါ်မူတည်ပြီး color ramp အမျိုးမျိုးကို ကြည့်ရှုနိုင်သည်။

Custom color ramp တစ်ခု ဖန်တီးရန် color ramp tab ကို activate ပြုလုပ်ပြီး 
|symbologyAdd| :sup:`Add item` ခလုတ်ကို click လုပ်ပါ။ ၄င်းတွင် color ramp အမျိုးအစားရွေးချယ်ရန် drop-down list ပြသထားသည်။

* :guilabel:`Gradient` သည် အစ အရောင် နှင့် အဆုံးသတ် အရောင် ကို ပေးပြီး **continuous (တစ်ဆက်တည်းဖြစ်သော)** သို့မဟုတ် **discrete (သီးခြားလိုက် ဖြစ်သော)** ဖြစ်နိုင်သည့် color ramp တစ်ခု ထုတ်ပေးသည်။
  Ramp preview ကို double-click နှိပ်ပြီး အလိုရှိသည့် intermediate (ကြား) အရောင်များကို ထည့်နိုင်သည်။
  Color stop indicator (အရောင်အဖြတ်ညွှန်းကိန်း) ကို click နှိပ်ပြီး :guilabel:`Gradient stop` အောက်တွင် ပြုလုပ်နိုင်သည်များမှာ-
  
  * Color ramp အစမှ :guilabel:`Relative position` ကို adjust လုပ်ပါ။
    Indicator ကို mouse ဖြင့် ဆွဲခြင်း သို့မဟုတ် arrow key များကို နှိပ်ပြီး ပြုလုပ်နိုင်သည်။
    (ကြီးကြီးမားမားရွှေ့ရန် arrow key ကို :kbd:`Shift` key ဖြင့် တွဲပြီးသုံးနိုင်သည်)
  * Color များကြား interpolate ပြုလုပ်လိုသည့်အခါ အသုံးပြုရန် color model ကို သတ်မှတ်ပါ။
    ၄င်းသည် :guilabel:`RGB` ၊ :guilabel:`HSL` သို့မဟုတ် :guilabel:`HSV` ဖြစ်သည်။
    အချို့အခြေအနေများတွင် desaturated mid tone များကို ရှောင်နိုင်သောကြောင့် ပိုမို၍ကြည့်ကောင်းသည့် gradient များကို ရရှိနိုင်သည်။
  * :guilabel:`HSL` သို့မဟုတ် :guilabel:`HSV` color သတ်မှတ်ချက်၏ **Hue** အစိတ်အပိုင်းအတွက် interpolation ပြုလုပ်ခြင်း၏ ဦးတည်ချက်ကို 
    :guilabel:`Clockwise` သို့မဟုတ် :guilabel:`Counterclockwise` ဖြင့် သတ်မှတ်နိုင်သည်။
  * :ref:`color properties <color-selector>` ကို သတ်မှတ်ပါ။
  * :guilabel:`Delete stop` သို့မဟုတ် :kbd:`DEL` နှိပ်၍ အရောင်ကို ဖယ်ရှားပါ။

  :guilabel:`Plots` group သည် color ramp (ရောင်စဉ်တန်း) များကို ဒီဇိုင်းဆွဲရန်၊ အရောင် stop များ၏ တည်နေရာ သို့မဟုတ် opacity (အလင်းပိတ်နှုန်း) နှင့် HSL 
  အစိတ်အပိုင်းများ ပြောင်းလဲရန်အတွက် တခြား graphical နည်းလမ်းကို ပံ့ပိုးပေးသည်။

  .. _figure_color_custom_ramp:

  .. figure:: img/customColorRampGradient.png
     :align: center

     Stops (အဖြတ်) အများအပြားပါဝင်သည့် စိတ်ကြိုက်ပြင်ဆင်ထားသော gradient color ramp ဥပမာ

  .. hint:: Color spot တွင် အရောင် တခုကို gradient ramp preview ပေါ်သို့ ဆွဲထည့်ခြင်းသည် အရောင် stop အသစ်တခုကို ထပ်တိုးစေသည်။

* :guilabel:`Color presets` - အသုံးပြုသူမှ ရွေးချယ်ထားသော color list ပါဝင်သည့် color ramp (ရောင်စဉ်တန်း) အသစ်တစ်ခုကို ဖန်တီးနိုင်သည်။
* :guilabel:`Random` - :guilabel:`Hue` ၊ :guilabel:`Saturation` ၊ :guilabel:`Value` ၊ :guilabel:`Opacity`
  နှင့် အရောင်များစွာ (:guilabel:`Classes`) အတွက် တန်ဖိုးများပေါ် မူတည်ပြီး ကျပန်းအရောင် အစုကို ဖန်တီးပေးသည်။
* :guilabel:`Catalog: ColorBrewer` - Ramp တွင် color အရေအတွက်ကို customize လုပ်နိုင်မည့် ကြိုတင်သတ်မှတ်ထားသည့် discrete color gradient အစုံဖြင့် လုပ်ဆောင်နိုင်သည်။
* သို့မဟုတ် :guilabel:`Catalog: cpt-city` - :guilabel:`save as standard gradient` ပြုလုပ်ပြီး color gradient များ၏ catalog တစ်ခုလုံးသို့ အသုံးပြုနိုင်သည့် အရာတစ်ခုဖြစ်သည်။ 
  cpt-city option သည် 'out of the box' ပါဝင်သည့် themes ရာပေါင်းများစွာ ပါရှိသော dialog အသစ်တစ်ခုကို ဖွင့်ပေးသည်။

.. _figure_color_cpt_city:

.. figure:: img/cpt-cityColorRamps.png
   :align: center

   Color ramp ရာပေါင်းများစွာပါရှိသည့် cpt-city dialog


.. _legend_patch:

Creating a Legend Patch Shape (Legend Patch Shape တစ်ခု ဖန်တီးခြင်း)
=====================================================================

Legend Patch Shape အသစ်တစ်ခုဖန်တီးရန် :guilabel:`Legend Patch Shapes` tab ကို activate ပြုလုပ်ပြီး
|symbologyAdd| :sup:`Add item` ခလုတ်ကို click နှိပ်ပါ။
အောက်ပါ ဂျီဩမေတြီ အမျိုးအစားများကို ရွေးနိုင်သည့် drop-down list ပေါ်လာမည်ဖြစ်သည်-

* :guilabel:`Marker Legend Patch Shape...` - point ဂျီဩမေတြီ များဖြင့် အသုံးပြုရန်။
* :guilabel:`Line Legend Patch Shape...` - line ဂျီဩမေတြီ များဖြင့် အသုံးပြုရန်။
* :guilabel:`Fill Legend Patch Shape...` - polygon ဂျီဩမေတြီ များဖြင့် အသုံးပြုရန်။

ရွေးချယ်စရာ သုံးခုစလုံးသည် တူညီသည့် dialog ကို ပြသပါလိမ့်မည်။

.. _figure_legend_patch:

.. figure:: img/createLegendPatchShape.png
   :align: center

   Legend Patch Shape တစ်ခု ဖန်တီးခြင်း  

ရွေးချယ်ထားသည့် ဂျီဩမေတြီ အမျိုးအစားနှင့် ပတ်သက်ပြီး shape အမျိုးအစား နှင့် ပြသထားသည့် legend patch shape သည် ကွဲပြားပါလိမ့်မည်။ အောက်ပါရွေးချယ်မှုများ ရရှိပါလိမ့်မည်-

* :guilabel:`Shape` - Legend patch shape ၏ shape ကို WKT string အဖြစ် သတ်မှတ်ပါ။
  Single နှင့် multipart ဂျီဩမေတြီ များ အသုံးပြုနိုင်သော်လည်း GeometryCollection မရှိပါ။
* |checkbox| :guilabel:`Preserve aspect ratio`
* tag များဖြင့် filter လုပ်ထားသည့် ရရှိသော legend patch shape များ၏ |iconView| :guilabel:`Icon View` သို့မဟုတ် |openTable| :guilabel:`List View`

Shape အသစ်ကို သတ်မှတ်ပြီးသောအခါ :guilabel:`Save Legend Patch Shape...` သို့မဟုတ် :guilabel:`OK` ကိုနှိပ်ပါ။ ထိုနှစ်ခုစလုံး သည် dialog တစ်ခုတည်းကို ဦးတည်သွားပါလိမ့်မည်။

.. _figure_safe_legend_patch:

.. figure:: img/safeLegendPatchShape.png
   :align: center

   Legend Patch Shape အသစ်တစ်ခုကို သိမ်းဆည်းခြင်း
  
Shape ကို ဖော်ပြရန် နာမည်၊ tag များ ရွေးချယ်ပြီး favourite ထဲသို့ ထည့်ထားနိုင်သည်။

:guilabel:`Save...` ကို နှိပ်လျှင် shape သည် list ထဲသို့ ထည့်သွင်းပြီးသားဖြစ်ပြီး
Shape အသစ်များကို ဆက်လက်ဖန်တီးရန်  :guilabel:`New Legend Patch Shape` dialog သို့ ပြန်လည်ရောက်ရှိသွားမည်ဖြစ်သည်။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |color| image:: /static/common/color.png
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |iconView| image:: /static/common/mActionIconView.png
   :width: 1.5em
.. |labelingSingle| image:: /static/common/labelingSingle.png
   :width: 1.5em
.. |legend| image:: /static/common/legend.png
   :width: 1.2em
.. |lineLayer| image:: /static/common/mIconLineLayer.png
   :width: 1.5em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |pointLayer| image:: /static/common/mIconPointLayer.png
   :width: 1.5em
.. |polygonLayer| image:: /static/common/mIconPolygonLayer.png
   :width: 1.5em
.. |search| image:: /static/common/search.png
   :width: 1.5em
.. |sharing| image:: /static/common/mActionSharing.png
   :width: 1.5em
.. |styleManager| image:: /static/common/mActionStyleManager.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |text| image:: /static/common/text.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
