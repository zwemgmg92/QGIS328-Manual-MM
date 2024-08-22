.. index:: Table items
.. _layout_table_item:

The Table Items (ဇယား Item များ)
=================================

.. only:: html

   .. contents::
      :local:

မြေပုံကို အလှဆင်ရန်နှင့် ရှင်းလင်းပြသရန် ဇယား item များကိုအသုံးပြုနိုင်သည်-

* :ref:`Attribute table <layout_attribute_table_item>` - ကြိုတင်သတ်မှတ်ထားသော စည်းမျဉ်းများအပေါ် အခြေခံ၍ layer တစ်ခုမှ attribute များအစုတစ်ခုကို ပြပေးသည်။
* :ref:`Fixed table <layout_fixed_table_item>` - အခြား layer များမှ သက်ရောက်မှုမပြုနိုင်သည့်အချက်အလက်များပါဝင်သော စာသားဇယားတစ်ခုကို ထည့်သွင်းပေးသည်။
 
.. _layout_attribute_table_item:

The attribute table item (Attribute ဇယား item)
-----------------------------------------------

Project ရှိ မည်သည့် layer တွင်မဆို print layout (ပုံထုတ်အပြင်အဆင်) တွင် ပြသထားသည့် ၎င်း၏ attribute များ ရှိနိုင်ပါသည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက် <create_layout_item>` ကိုလိုက်နာ၍ :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့်နည်းလမ်းအတိုင်း နောက်ပိုင်းတွင် ကိုင်တွယ်နိုင်မည့် ဇယား item အသစ်တစ်ခုကိုထည့်သွင်းရန် |addTable| :guilabel:`Add Attribute Table` tool ကိုအသုံးပြုပါ။ 

Default အားဖြင့် attribute ဇယားအသစ်တစ်ခုသည် field များအားလုံးပါဝင်သော ပထမဆုံး (အက္ခရာစဉ်အလိုက်စီထားသော) layer ၏ ပထမဆုံး row (အတန်း) များကို ပြသနေမည်ဖြစ်သည်။ သို့သော်လည်း ဇယားအား ၎င်း၏ :guilabel:`Item Properties` panel မှတစ်ဆင့် စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ ဤ feature တွင် :ref:`item များ၏ဘုံဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_table` တွင်ကြည့်ပါ)-


.. _figure_layout_table:

.. figure:: img/attribute_properties.png
   :align: center

   Attribute ဇယား Item ဂုဏ်သတ္တိများ Panel


Main properties (အဓိကဂုဏ်သတ္တိများ)
....................................

Attribute ဇယား ၏ :guilabel:`Main properties` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည်(:numref:`figure_layout_table_ppt` တွင်ကြည့်ပါ)-

.. _figure_layout_table_ppt:

.. figure:: img/attribute_mainproperties.png
   :align: center

   Attribute ဇယား အဓိကဂုဏ်သတ္တိများ အုပ်စု

* :guilabel:`Source` အတွက် project ထဲတွင်ထည့်သွင်းထားသော vector layer များမှ :guilabel:`Layer` တစ်ခုကိုရွေးချယ်ခွင့်ပေးသော **Layer features** များကိုသာ default အားဖြင့် ရွေးချယ်နိုင်သည်။ 
 
  Layer စာရင်းအနီးရှိ |dataDefine| :sup:`Data-defined override` ခလုတ်ဖြင့်  ဇယားကိုဖြည့်ရာတွင် အသုံးပြုသော layer အား အချိန်နှင့်တစ်ပြေးညီ ပြောင်းလဲပေးနိုင်သည်၊ ဥပမာအားဖြင့် atlas စာမျက်နှာတစ်ခုစီတိုင်းတွင် attribute ဇယားကို မတူညီသော layer attribute များဖြင့် ဖြည့်နိုင်သည်။ အသုံးပြုသည့် ဇယားတည်ဆောက်မှုပုံစံ (:numref:`figure_layout_table_select`) သည် :guilabel:`Layer` drop-down စာရင်းထဲတွင် ပြသထားသည့် layer တစ်ခုဖြစ်ပြီး ၎င်းကိုမပြောင်းဘဲချန်လှပ်ထားခဲ့သည်ကိုသတိပြုပါ။ ဆိုလိုသည်မှာ layer တစ်ခုသို့ မတူညီသော field (များ) ဖြင့် data သတ်မှတ်ထားသော ဇယားတစ်ခုကို ချိန်ညှိသတ်မှတ်ပါက ဇယားထဲတွင် column အလွတ်(များ) ရရှိလာမည်ဖြစ်သည်။

  :guilabel:`Atlas` panel ထဲတွင် |checkbox|:guilabel:`Generate an atlas` option အားအသုံးပြုမိလျှင် (:ref:`atlas_generation` ကိုကြည့်ပါ) ထပ်ဆောင်း :guilabel:`Source` နှစ်ခုဖြစ်လာနိုင်ပါသည် -
 
  
  * **Current atlas feature** (:numref:`figure_layout_table_atlas` ကိုကြည့်ပါ)- layer ရွေးချယ်ရန်အတွက် မည်သည့် ရွေးချယ်စရာကိုမျှတွေ့ရမည်မဟုတ်ဘဲ ဇယား item သည် atlas လွှမ်းခြုံသော layer ၏ လက်ရှိ feature မှ attribute များပါဝင်သော row တစ်ခုကိုသာ ပြသနေမည်ဖြစ်သည်။
   
  * နှင့် **Relation children** (:numref:`figure_layout_table_relation` ကိုကြည့်ပါ)- relation (ဆက်နွယ်ချက်) အမည်များပါဝင်သော ရွေးချယ်စရာတစ်ခု ပေါ်လာပါမည်။ Atlas လွှမ်းခြုံသော layer အား parent (မူရင်း) အဖြစ်အသုံးပြု၍ :ref:`relation <vector_relations>` တစ်ခုကိုသတ်မှတ်ပြီးမှသာ ဤ feature ကို အသုံးပြုနိုင်မည်ဖြစ်ပြီး ဇယားသည် atlas လွှမ်းခြုံသော layer ၏ လက်ရှိ feature ၏ children (အခွဲ) row များကို ပြသနေမည်ဖြစ်သည်။

*  ဇယားတွင် အမှန်တကယ်ပါရှိသောအကြောင်းအရာများ ပြောင်းလဲသွားပါက :guilabel:`Refresh Table Data` ခလုတ်အားအသုံးပြု၍ ဇယားအား update လုပ်နိုင်ပါသည်။
 

.. _figure_layout_table_atlas:

.. figure:: img/attribute_mainatlas.png
   :align: center

   'လက်ရှိ atlas feature' အတွက် Attribute ဇယား အဓိကဂုဏ်သတ္တိများ


.. _figure_layout_table_relation:

.. figure:: img/attribute_mainrelation.png
   :align: center

   'Relation children' အတွက် Attribute ဇယား အဓိကဂုဏ်သတ္တိများ

* :guilabel:`Attributes...` ခလုတ်ဖြင့် ဇယားတွင်မြင်ရနိုင်သည့်အကြောင်းအရာများကို ပြောင်းလဲရန်အသုံးပြုသည့် :guilabel:`Select Attributes` dialog ကိုဖွင့်နိုင်သည်(:numref:`figure_layout_table_select` ကိုကြည့်ပါ)။ Window ၏အပေါ်ပိုင်းသည် attribute များစာရင်းကို ပြသနေမည်ဖြစ်ပြီး အောက်ပိုင်းသည် အချက်အလက် data များကို sort (စီစဉ်) ပြုလုပ်ရာတွင် ကူညီပေးမည်ဖြစ်သည်။
 

  .. _figure_layout_table_select:

  .. figure:: img/attribute_select.png
     :align: center

     Attribute ဇယား Select attributes Dialog

  :guilabel:`Columns` အပိုင်းတွင်-

  * အတန်းများ (rows) ကိုရွေးချယ်၍ ၎င်းတို့ကိုရွေ့စေရန် |arrowUp| နှင့် |arrowDown| ခလုတ်များကို အသုံးပြုခြင်းဖြင့် attribute များကို စာရင်းထဲတွင် အပေါ် သို့မဟုတ် အောက်သို့ရွှေ့ပြောင်းနိုင်သည်။ တစ်ကြိမ်တည်းမှာပင် row မြောက်များစွာကို ရွေးချယ်နိုင်၍  ရွှေ့နိုင်ပါသည်။
  * |symbologyAdd| ခလုတ်အသုံးပြုခြင်းဖြင့် attribute တစ်ခုကိုထည့်သွင်းနိုင်သည်။ ထိုခလုတ်သည် ဇယား၏အောက်ခြေတွင် attribute တန်ဖိုးဖြစ်ရန် field တစ်ခုအားရွေးချယ်နိုင်မည့် သို့မဟုတ် ပုံမှန် expression တစ်ခုမှတစ်ဆင့် attribute တစ်ခုကိုဖန်တီးနိုင်မည့် row လွတ်တစ်ခုကိုထည့်သွင်းပေးသည်။
  * |symbologyRemove| ခလုတ်အသုံးပြုခြင်းဖြင့် attribute တစ်ခုကိုဖယ်ရှားနိုင်သည်။ တစ်ကြိမ်တည်းမှာပင်မြောက်များစွာသော row များကို ရွေးချယ်နိုင်၍ ဖယ်ရှားပစ်နိုင်သည်။
  * :guilabel:`Reset` ခလုတ်အသုံးပြုခြင်းဖြင့် attribute ဇယားအား မူလအခြေအနေသို့ပြန်လည်ရောက်ရှိစေရန် သတ်မှတ်နိုင်သည်။
  * :guilabel:`Clear` ခလုတ်အသုံးပြုခြင်းဖြင့် ဇယားအား ရှင်းလင်းနိုင်သည်။ ဤခလုတ်သည် ကြီးသောဇယားများတွင် အနည်းငယ်မျှသော attribute အရေအတွက်ကိုသာပြသလိုပါကအသုံးဝင်သည်။ Row တစ်ခုချင်းစီအား manual ဖယ်ရှားနေမည့် အစား ဇယားအားရှင်းလင်း၍ လိုအပ်သော row များကိုထည့်သွင်းပါက ပိုမိုမြန်ဆန်ပါမည်။
  * :guilabel:`Heading` column တွင်စိတ်ကြိုက်စာသားများထည့်သွင်းခြင်းဖြင့် ဇယားကွက် (cell)၏ခေါင်းစီးများကိုပြောင်းလဲနိုင်သည်။
  * ဇယားကွက် (cell) ချိန်ညှိမှုအား ဇယားကွက် (cell) အတွင်းတွင် စာသားထားရှိလိုသည့်တည်နေရာအားသတ်မှတ်နိုင်မည့် :guilabel:`Alignment` column ဖြင့်စီမံနိုင်သည်။
  * :guilabel:`width` column တွင် စိတ်ကြိုက်တန်ဖိုးများထည့်သွင်းခြင်းဖြင့် ဇယားကွက် (cell)၏အကျယ်ကို လိုသလိုစီမံနိုင်သည်။

  :guilabel:`Sorting` အပိုင်းတွင်- 

  * ဇယားအားအမျိုးအစားခွဲရန် attribute တစ်ခုထည့်သွင်းခြင်း- |symbologyAdd| ခလုတ်ကိုဖိထားလျှင် row လွတ် အသစ်တစ်ခုထပ်ထည့်ပေးပါလိမ့်မည်။ :guilabel:`Attribute` column ထဲတွင် field တစ်ခု သို့မဟုတ် expression တစ်ခုကိုထည့်သွင်း၍ :guilabel:`Sort order` အား  **ငယ်စဉ်ကြီးလိုက်** သို့မဟုတ် **ကြီးစဉ်ငယ်လိုက်** အဖြစ်စီထားနိုင်သည်။
  * Attribute အဆင့်တွင် ဦးစားပေးရမည့် အမျိုးအစားအလိုက်စုစည်းခြင်းအတွက် စာရင်းထဲရှိ row တစ်ခုအားရွေးချယ်၍ |arrowUp| နှင့် |arrowDown| ခလုတ်များ ကိုအသုံးပြု၍ ပြောင်းလဲပါ။ :guilabel:`Sort Order` column ထဲတွင်ဇယားကွက်တစ်ခုအားရွေးလိုက်ခြင်းဖြင့် attribute field ၏ အမျိုးအစားအလိုက်စုစည်းခြင်းဝါစဉ် (sorting order) အားပြောင်းလဲနိုင်သည်။  
  * အမျိုးအစားအလိုက်စုစည်းခြင်းစာရင်းမှ attribute တစ်ခုကိုဖယ်ရှားရန် |symbologyRemove| ခလုတ် ကိုအသုံးပြုနိုင်သည်။ 


Feature filtering (Feature များကိုစစ်ထုတ်ခြင်း)
................................................

Attribute ဇယား၏ :guilabel:`Feature filtering` အုပ်စုတွင်အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် ( :numref:`figure_layout_table_filter` ကိုကြည့်ပါ)-

.. _figure_layout_table_filter:

.. figure:: img/attribute_filter.png
   :align: center

   Attribute ဇယား Feature စစ်ထုတ်ခြင်းအုပ်စု

Attribute ဇယား၏ feature များကိုစစ်ထုတ်ခြင်း အုပ်စုတွင်-

* ပြသမည့် :guilabel:`Maximum rows` (အများဆုံး row) အားသတ်မှတ်နိုင်ပါသည်။
* Unique ဖြစ်သောမှတ်တမ်းများကိုသာပြသရန် |checkbox| :guilabel:`Remove duplicate rows from table` အားအမှန်ခြစ်နိုင်ပါသည်။
* |checkbox| :guilabel:`Show only visible features within a map` အားအမှန်ခြစ်၍ မြင်သာသော feature များ၏ attribute များကိုပြသနေမည့် သက်ဆိုင်ရာ :guilabel:`Linked map` ကို ရွေးချယ်နိုင်ပါသည်။
* |checkbox| :guilabel:`Show only features intersecting Atlas feature` အားအမှန်ခြစ်နိုင်ပါသည်။ ၎င်းသည် |checkbox| :guilabel:`Generate an atlas` အား အမှန်ခြစ်ထားမှသာ ပေါ်နေမည်ဖြစ်မည်။ အမှန်ခြစ်ပြီးသောအခါ လက်ရှိ atlas feature နှင့် ထပ်နေသော feature များသာပါဝင်သည့် ဇယားတစ်ခုကိုပြသလိမ့်မည်။ 
* |checkbox| :guilabel:`Filter with` အားအမှန်ခြစ်၍ input line ထဲတွင်ရိုက်ထည့်ခြင်းဖြင့် filter တစ်ခုထည့်သွင်းနိုင်သကဲ့သို့ ပေးထားသော |expression| expression ခလုတ်အားအသုံးပြုခြင်းဖြင့် ပုံမှန် expression တစ်ခုကိုထည့်သွင်းနိုင်သည်။ Sample dataset မှ airports layer (လေဆိပ် layer များ) နှင့်အလုပ်လုပ်သောအခါအသုံးပြုနိုင်သော filtering statement နမူနာအချို့မှာ - 
  
  * ``ELEV > 500``
  * ``NAME = 'ANIAK'``
  * ``NAME NOT LIKE 'AN%'``
  * ``regexp_match( attribute( $currentfeature, 'USE' )  , '[i]')``

  နောက်ဆုံး expression ၌ attribute field 'USE' တွင် စာလုံး 'i' ပါရှိသော airport များသာပါဝင်သည်။ 

Appearance (အသွင်အပြင်ပုံစံ)
.............................

Attribute ဇယား၏ :guilabel:`Appearance` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် ( :numref:`figure_layout_table_appearance` ကိုကြည့်ပါ)-

.. _figure_layout_table_appearance:

.. figure:: img/attribute_appearance.png
   :align: center

   Attribute ဇယား အသွင်အပြင်ပုံစံအုပ်စု

* Attribute ဇယားတွင် ဇယားကွက် (cell) အလွတ်များဖြင့်ဖြည့်သွင်းရန် |checkbox| :guilabel:`Show empty rows` အား click နှိပ်ပါ။ ပြသလိုသည့် ရလာဒ်တစ်ခုရှိသောအခါ နောက်ထပ် ဇယားကွက် (cell) အလွတ်များထပ်ထည့်လိုပါက ဤရွေးချယ်စရာအားအသုံးပြုနိုင်ပါသည်။
* :guilabel:`Cell margins` ဖြင့် ဇယား၏ ဇယားကွက်တစ်ခုချင်းစီမှ စာသားပတ်လည်တွင် margin သတ်မှတ်နိုင်သည်။
* :guilabel:`Display header` ဖြင့် စာရင်းတစ်ခုရှိ 'On first frame' ၊ 'On all frames' (default ရွေးချယ်စရာ) သို့မဟုတ် 'No header' တို့ထဲမှတစ်ခုကိုရွေးချယ်နိုင်သည်။
  
* ရလာဒ်ရွေးချယ်သည့်နေရာတွင် အလွတ်ဖြစ်နေပါက :guilabel:`Empty table` ဖြင့်မည်သည့်ရလာဒ်ကိုပြသလိုသည်ကို ထိန်းချုပ်နိုင်သည်။

  * **Draw headers only** သည် :guilabel:`Display header` အတွက် 'No header' ကိုမရွေးချယ်ထားမှသာ ခေါင်းစီးကို ပြပေးသည်။
  * **Hide entire table** သည် ဇယား၏နောက်ခံကိုသာပြပေးသည်။ :guilabel:`Frames` ထဲရှိ |checkbox| :guilabel:`Don't draw background if frame is empty` အားအမှန်ခြစ်ပေးခြင်းဖြင့် ဇယားကိုလုံးဝဖျောက်ပစ်နိုင်သည်။
  * **Show set message** သည် ခေါင်းစီးတစ်ခုနှင့် column များအားလုံးကိုခြုံငုံသည့် ဇယားကွက်တစ်ခုအား ထည့်သွင်းပေးကာ :guilabel:`Message to display` option ထဲတွင်ထည့်သွင်းထားနိုင်သည့် 'No result' ကဲ့သို့သောစာတိုတစ်ခုအားပြသပေးသည်။
   
* :guilabel:`Empty table` အတွက် **Show set message** အားရွေးချယ်ပြီးမှသာ :guilabel:`Message to display` သည်အသက်ဝင်မည်ဖြစ်သည်။ ရလာဒ်သည် ဇယားအလွတ် ဖြစ်နေသောအခါ ဇယား၏ပထမ row တွင် သတိပေး စာတိုပေါ်လာပါမည်။
* :ref:`အရောင်ရွေးချယ်ပေးသည့်အရာ <color-selector>` widget အားအသုံးပြု၍ :guilabel:`Background color` ဖြင့် ဇယား၏နောက်ခံအရောင်ကိုသတ်မှတ်နိုင်သည်။ :guilabel:`Advanced customization` ဖြင့် ဇယားကွက်တစ်ခုချင်းစီအတွက် မတူညီသော နောက်ခံ အရောင်များကိုသတ်မှတ်နိုင်သည် (:numref:`figure_layout_table_background` ကိုကြည့်ပါ)။
 
.. _figure_layout_table_background:

.. figure:: img/attribute_background.png
   :align: center

   Attribute ဇယား အဆင့်မြင့်နောက်ခံအရောင်ထည့်သွင်းခြင်း Dialog

* |checkbox| :guilabel:`Apply layer conditional styling colors` - Layer ထဲတွင်ရှိသော :ref:`conditional table formatting <conditional_formatting>` (နောက်ခံအရောင်၊ စာလုံးအထင်း၊ စာလုံးအစောင်း ၊ စာသားကိုဖြတ်၍မျဉ်းဆွဲခြင်း ၊ စာသားအောက်မျဉ်းသားခြင်း ၊ အရောင် ...အစရှိသော စာလုံးဖောင့်များနှင့် ဂုဏ်သတ္တိများ) ကို layout attribute ဇယားအတွင်းတွင် အသုံးပြုပါသည်။ Conditional formatting (အခြေအနေပေါ်မူတည်၍ format ပြင်ဆင်ခြင်း) စည်းမျဉ်းများသည် အခြား layout ဇယား formatting setting များထက် ဦးစားပေးခံရပါသည်၊ ဥပမာ- row အရောင်များကိုပြောင်းလဲခြင်းကဲ့သို့သော အခြားသော ဇယားကွက်၏ နောက်ခံအရောင် setting များကို အစားထိုးလုပ်ဆောင်ပါလိမ့်မည်။
* :guilabel:`Wrap text on` option ဖြင့် character တစ်ခုကို သတ်မှတ်နိုင်ပြီး ၎င်း character ကိုတွေ့ရှိသည့်အခါတိုင်းတွင် ဇယားရှိအကြောင်းအရာများကို wrap (ခြုံငုံ၍မြင်ရနိုင်စေရန် စာကြောင်းများစွာဖြင့်ပြသ) လုပ်ပေးမည်ဖြစ်သည်။
* ဇယားရှိ column တစ်ခုအတွက် သတ်မှတ်ထားသောအကျယ်သည် ၎င်းတွင်ပါဝင်သော အကြောင်းအရာများ၏အလျားထက် တိုနေလျှင် :guilabel:`Oversized text` ဖြင့် စာသား၏အထားအသိုပုံစံကိုသတ်မှတ်နိုင်သည်။ ၎င်းသည် **Wrap text** သို့မဟုတ် **Truncate text (စာသားဖြတ်ခြင်း)** ဖြစ်နိုင်သည်။
  

.. note:: Attribute ဇယား item ၏ အခြား ဂုဏ်သတ္တိများအား :ref:`tables_common_properties` section တွင် ဖော်ပြထားပါသည်။

.. _layout_fixed_table_item:

The fixed table item (ပုံသေသတ်မှတ်ထားသော ဇယား item)
----------------------------------------------------

မြေပုံနှင့်ပတ်သက်၍နောက်ဆက်တွဲအချက်အလက်များကို |addManualTable| :guilabel:`Add Fixed Table` အားရွေးချယ်ခြင်းဖြင့် ဇယားတစ်ခုအတွင်းသို့ ထည့်သွင်းနိုင်ပြီး :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့်နည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည့် ဇယားအသစ်တစ်ခုကိုထည့်သွင်းရန် :ref:`item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက်များ <create_layout_item>` အားလိုက်နာနိုင်ပါသည်။ 
 
Default အားဖြင့် ချုံ့ထားသော column နှစ်ခု row နှစ်ခုပါဝင်သော ဇယားအလွတ်တစ်ခုသည် မြေပုံ layout ထဲတွင်ပေါ်နေမည်ဖြစ်သည်။ ဇယားကို :guilabel:`Item Properties` panel ထဲတွင် စိတ်ကြိုက်ပြင်ဆင်ရမည်ဖြစ်သည်။ ဤ feature တွင် :ref:`item များ၏ဘုံဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည်-

Main properties (အဓိက ဂုဏ်သတ္တိများ)
.....................................

.. _figure_table_designer_fixed_table:

.. figure:: img/fixedtable_table_designer.png
   :align: center

   Table designer ဖြင့် ပုံသေသတ်မှတ်ထားသော ဇယား Item ဂုဏ်သတ္တိများ Panel

:guilabel:`Main properties` ထဲတွင် :guilabel:`Edit table ...` ကို click နှိပ်ပြီးလျှင် :guilabel:`Table designer` နှင့်အလုပ်လုပ်နိုင်ပြီဖြစ်သည်-

* ဇယားထဲတွင် click နှိပ်ဝင်ရောက်၍ စာသားများကို ကိုယ်တိုင်ထည့်သွင်းနိုင်ပါသည်။
* အပေါ်ရှိ menu များမှတစ်ဆင့် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်ပါသည်-

  * :guilabel:`File` သို့သွား၍ :guilabel:`Import Content From Clipboard` (Clipboard မှ အကြောင်းအရာများထည့်သွင်းခြင်း) (၎င်းသည် ပေးထားသော input များကို အစားထိုးလုပ်ဆောင်သွားမည်ဖြစ်သည်)
  * :guilabel:`Edit` သို့သွားခြင်းဖြင့် row များနှင့် column များအတွက် ရွေးချယ်ခြင်းဆိုင်ရာ လုပ်ဆောင်ချက်များဖြင့် အလုပ်လုပ်နိုင်သည်။
  * :guilabel:`Insert rows` ၊ :guilabel:`Insert columns` ၊ :guilabel:`Delete Rows` ၊ :guilabel:`Delete Columns` များအပြင် |checkbox| :guilabel:`Include Header Row` (ခေါင်းစီး row ပါဝင်စေခြင်း) option ကို အသုံးပြုခြင်း။ 

* ညာဘက်ရှိ :guilabel:`Cell Contents` အပိုင်းဖြင့် အလုပ်လုပ်နိုင်သည့်အပြင်-

  * :guilabel:`Formatting` ထဲတွင် ရွေးချယ်ထားသောဇယားကွက်များ၏ စာသား format အား သတ်မှတ်နိုင်သည်-

    * ပေးထားသော |expression| expression ခလုတ်ပေါ်တွင် click နှိပ်ခြင်းနှင့်  ဇယားကွက်တွင်ထည့်သွင်းရန် ပုံမှန် expression တစ်ခုကိုအသုံးပြုခြင်းဖြင့်၊  
    * :guilabel:`Text format` အားရွေးချယ်ခြင်းဖြင့်၊
    * |checkbox| :guilabel:`Format as number` ဖြင့် (များစွာသော format များဖြင့်ရရှိနိုင်သည်)
    * :guilabel:`Horizontal alignment` (ရေပြင်ညီတန်းညှိခြင်း) နှင့် :guilabel:`Vertical alignment` (ဒေါင်လိုက်တန်းညှိခြင်း) အားသတ်မှတ်ခြင်းဖြင့်၊
    * :guilabel:`Background color` တစ်ခုအားရွေးချယ်ခြင်းဖြင့်၊

  * :guilabel:`Row height` နှင့် :guilabel:`Column width` တို့ဖြင့် :guilabel:`Cell Size` ကိုသတ်မှတ်နိုင်သည်။
    

Appearance (အသွင်အပြင်ပုံစံ)
.............................

ပုံသေသတ်မှတ်ထားသောဇယား၏ :guilabel:`Appearance` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည်-

* ဇယားကွက်အလွတ်များဖြင့် attribute ဇယားအားဖြည့်ရန် |checkbox| :guilabel:`Show empty rows` အား click နှိပ်ပါ။
* :guilabel:`Cell margins` ဖြင့် ဇယားမှ ဇယားကွက်တစ်ခုချင်းစီရှိ စာသား၏ပတ်လည်တွင် margin သတ်မှတ်နိုင်သည်။
* :guilabel:`Display header` ဖြင့် စာရင်းတစ်ခုရှိ  'On first frame' ၊ 'On all frames' (default ရွေးချယ်စရာ) သို့မဟုတ် 'No header' တို့ထဲမှတစ်ခုကိုရွေးချယ်နိုင်သည်။
* :ref:`အရောင်ရွေးချယ်ပေးသည့်အရာ <color-selector>` widget အားအသုံးပြု၍ ဇယား၏နောက်ခံအရောင်ကို :guilabel:`Background color` ဖြင့် သတ်မှတ်နိုင်သည်။ :guilabel:`Advanced customization` ကိုရွေးချယ်ခြင်းဖြင့် ဇယားကွက်တစ်ခုချင်းစီအတွက် မတူညီသောနောက်ခံအရောင်များ သတ်မှတ်နိုင်မည်ဖြစ်သည်။
* ဇယားရှိ column တစ်ခုအတွက် သတ်မှတ်ထားသော အကျယ်သည် ၎င်းတွင်ပါဝင်သောအကြောင်းအရာ၏ အလျားထက် တိုနေလျှင် :guilabel:`Oversized text` ဖြင့် စာ၏အထားအသိုကိုသတ်မှတ်နိုင်သည်။ ၎င်းသည် **Wrap text** သို့မဟုတ် **Truncate text** ဖြစ်နိုင်သည်။
  

.. note:: ပုံသေသတ်မှတ်ထားသော ဇယား item ၏ အခြားဂုဏ်သတ္တိများကို  :ref:`tables_common_properties` အပိုင်းတွင်ဖော်ပြထားပါသည်။
   

.. _tables_common_properties:

Tables common functionalities (ဇယားများ၏ ဘုံလုပ်ဆောင်ချက်များ )
----------------------------------------------------------------

Show grid (Grid ကိုပြသခြင်း)
.............................

ဇယား item များ၏ :guilabel:`Show grid` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည် (:numref:`figure_layout_table_grid` ကိုကြည့်ပါ)-

.. _figure_layout_table_grid:

.. figure:: img/attribute_grid.png
   :align: center

   Attribute ဇယား၏ grid ကိုပြသပေးခြင်းအုပ်စု

* ဇယားကွက်များ၏ ဘောင်များဖြစ်သည့် grid အား ပြသလိုသည့်အခါ |checkbox| :guilabel:`Show grid` ကို အမှန်ခြစ်ပါ။ :guilabel:`Draw horizontal lines` ကို ဖြစ်စေ :guilabel:`Draw vertical lines` ကို ဖြစ်စေ နှစ်ခုစလုံးကို ဖြစ်စေရွေးချယ်နိုင်သည်။
* :guilabel:`Line width` ဖြင့် grid တွင် အသုံးပြုသော မျဉ်းများ၏ အထူကိုသတ်မှတ်နိုင်သည်။
* အရောင်ရွေးချယ်ခြင်းဆိုင်ရာ widget ကိုအသုံးပြုခြင်းဖြင့် grid ၏ :guilabel:`Color` (အရောင်) ကိုသတ်မှတ်နိုင်သည်။


Fonts and text styling (စာလုံးဖောင့်များ နှင့် စာသား သင်္ကေတပုံစံ)
...................................................................

ဇယား item များ၏ :guilabel:`Fonts and text styling` အုပ်စုတွင်အောက်ပါလုပ်ဆောင်ချက်များပါဝင်ပါသည် (:numref:`figure_layout_table_fonts` ကိုကြည့်ပါ)-

.. _figure_layout_table_fonts:

.. figure:: img/attribute_fonts.png
   :align: center

   Attribute ဇယား စာလုံးဖောင့်များနှင့် စာသားသင်္ကေတပုံစံ အုပ်စု

* :guilabel:`Table heading` (ဇယားခေါင်းစီး) နှင့် :guilabel:`Table contents` (ဇယားအကြောင်းအရာ) များအတွက် အဆင့်မြင့် :ref:`text settings <text_format>` widget (buffer ၊ အရိပ် ၊ အရောင်ချယ်သခြင်း effect များ ၊ ဖောက်ထွင်းမြင်နိုင်မှု၊ နောက်ခံ၊ အရောင်ထည့်သွင်းခြင်း...စသည်တို့) ကိုအသုံးပြုခြင်းဖြင့် :guilabel:`Font` ဂုဏ်သတ္တိများကိုသတ်မှတ်နိုင်သည်။ :guilabel:`Appearance` အပိုင်းမှဖြစ်စေ :guilabel:`Table Designer` dialog မှဖြစ်စေ ဤသို့ပြောင်းလဲလိုက်မှုများသည် စိတ်ကြိုက်စာလုံးဖောင့်များ ပြုပြင်ထည့်သွင်းထားသည့် ဇယားကွက်များသို့ သက်ရောက်မှုရှိမည်မဟုတ်သည်ကို သတိပြုပါ။ Default ပုံဖော်ပြသခြင်း (rendering) ရှိသော ဇယားကွက်များအပေါ်တွင်သာ သက်ရောက်မှုရှိမည်ဖြစ်သည်။ 
* :guilabel:`Table heading` အတွက် :guilabel:`Alignment` အား ``Follow column alignment`` အဖြစ် ထပ်မံသတ်မှတ်နိုင်သည် သို့မဟုတ် ``Left`` ၊ ``Center`` သို့မဟုတ်  ``Right`` အားရွေးချယ်ခြင်းဖြင့် ဤ setting အား အစားထိုးလုပ်ဆောင်နိုင်သည်။ :guilabel:`Select Attributes` dialog အားအသုံးပြုခြင်းဖြင့် column alignment အားသတ်မှတ်ပေးပါသည် (:numref:`figure_layout_table_select` ကိုကြည့်ပါ)။
   

Frames (ဘောင်များ)
...................

ဇယား item ဂုဏ်သတ္တိများ၏ :guilabel:`Frames` အုပ်စုတွင်အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သည် (:numref:`figure_layout_table_frames` ကိုကြည့်ပါ)-

.. _figure_layout_table_frames:

.. figure:: img/attribute_frame.png
   :align: center

   Attribute ဇယား ဘောင်များဆိုင်ရာ အုပ်စု

* :guilabel:`Resize mode` ဖြင့် attribute ဇယားမှအကြောင်းအရာများကို မည်သို့ ပုံဖော်ပြသမည်ကိုရွေးချယ်နိုင်သည်-

  * ``Use existing frames`` သည် ပထမဆုံး frame နှင့် ထည့်သွင်းထားသော frame များတွင်သာ ရလာဒ်ကိုပြသပေးသည်။  
  * ``Extend to next page`` သည် attribute ဇယား၏ အပြည့်အဝရွေးမှတ်ထားမှုအားပြသနိုင်ရန်အတွက် frame များ (ပြီးလျှင် သက်ဆိုင်ရာ စာမျက်နှာများ) ကို လိုသလောက်များများ ဖန်တီးပေးမည်ဖြစ်သည်။ Frame တစ်ခုချင်းစီအား layout ပေါ်တွင် ရွှေ့နိုင်ပါသည်။ Frame တစ်ခု၏အရွယ်အစားအား ပြန်လည်သတ်မှတ်လျှင် ရရှိလာသောဇယားသည် အခြား frame များကြားတွင် နှစ်ပိုင်းကွဲသွားမည်ဖြစ်ပြီး နောက်ဆုံး frame အား ဇယားနှင့်ဝင်ဆန့်စေရန် ဖြတ်ထုတ်လိုက်မည်ဖြစ်သည်။
  * ``Repeat until finished`` သည် `Extend to next page` option ကဲ့သို့ frame များစွာဖန်တီးပေးမည်ဖြစ်သော်လည်း frame များအားလုံးတွင်တူညီသောအရွယ်အစားရှိမည်ဖြစ်သည်။
    
* ရွေးချယ်ထားသော frame ကဲ့သို့ အရွယ်အစားတူသည့် နောက် frame အားထည့်သွင်းရန် :guilabel:`Add Frame` ခလုတ်အား အသုံးပြုပါ။ Resize mode (အရွယ်အစားပြန်သတ်မှတ်ခြင်းနည်းလမ်း) ``Use existing frames`` အားအသုံးပြုသည့်အခါ ပထမဆုံး frame ထဲတွင် မဆန့်သည့် ဇယားမှရလာဒ်များသည် နောက် frame ထဲတွင် ဆက်သွားမည်ဖြစ်သည်။
  
* ဇယား frame တွင်အကြောင်းအရာများမပါရှိသောစာမျက်နှာကို export လုပ်ခြင်းမှကာကွယ်ထားလိုပါက |checkbox| :guilabel:`Don't export page if frame is empty` ကိုအမှန်ခြစ်ထားပါ။ ဆိုလိုသည်မှာ အခြား layout item များအားလုံး၊ မြေပုံများ၊ စကေးဘားများ နှင့် ရည်ညွှန်းချက်များ အစရှိသည်တို့ကို ရလာဒ်ထဲတွင် မြင်ရမည်မဟုတ်ပါ။
* ဇယား frame တွင်အကြောင်းအရာများမပါရှိပါက နောက်ခံပေါ်တွင်မြေပုံရေးဆွဲခြင်းအား ကာကွယ်ထားရန် |checkbox| :guilabel:`Don't draw background if frame is empty` ကိုအမှန်ခြစ်ထားပါ။
  

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addManualTable| image:: /static/common/mActionAddManualTable.png
   :width: 1.5em
.. |addTable| image:: /static/common/mActionAddTable.png
   :width: 1.5em
.. |arrowDown| image:: /static/common/mActionArrowDown.png
   :width: 1.5em
.. |arrowUp| image:: /static/common/mActionArrowUp.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |expression| image:: /static/common/mIconExpression.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
