.. _symbol-selector:

**********************************************
The Symbol Seclector (သင်္ကေတရွေးချယ်သည့်အရာ)
**********************************************
.. only:: html

   .. contents::
      :local:


သင်္ကေတရွေးချယ်သည့်အရာ သည် သင်္ကေတတစ်ခုကို ဖန်တီးပုံဖော်ရန် အဓိက dialog ဖြစ်သည်။ 
အမှတ်သင်္ကေတ (Marker) ၊ လိုင်းသင်္ကေတ (Line) သို့မဟုတ် အဖြည့် သင်္ကေတ (Fill Symbol) များဖန်တီးခြင်း သို့မဟုတ် ပြင်ဆင်တည်းဖြတ်ခြင်းများဆောင်ရွက်နိုင်သည်။

.. _figure_symbol_selector:

.. figure:: img/symbolselector.png
   :align: Center

   မျဉ်းကြောင်းတွင် အသုံးပြုမည့် line သင်္ကေတ ဒီဇိုင်းပြုလုပ်ခြင်း


သင်္ကေတ Selector dialog ကို အဓိက အစိတ်အပိုင်းနှစ်ခုဖြင့် တည်ဆောက်ထားသည်-

* သင်္ကေတဖွဲ့စည်းပုံ (tree) သည် သင်္ကေတ layer များ ပေါင်းစပ်ထားသော ပင်မသင်္ကေတအသစ် (new global) ဖြစ်သည်။
* Tree ထဲရှိ ရွေးချယ်ထားသော သင်္ကေတ layer ကို ပြင်ဆင်သည့် setting များဖြစ်သည်။

.. _symbol_tree:

The symbol layer tree (သင်္ကေတအလွှာဖွဲ့စည်းပုံ)
================================================

သင်္ကေတတစ်ခုတွင် များစွာသော :guilabel:`Symbol layers` (သင်္ကေတအလွှာများ) ပါဝင်ပါသည်။ သင်္ကေတအလွှာဖွဲ့စည်းပုံ layer tree သည်  ပင်မသင်္ကေတအသစ် (new global) တွင်ပါဝင်သော ထပ်၍ ပေါင်းစပ်ထားသော သင်္ကေတ အလွှာများကို ပြသသည်။ ထို့အပြင် သင်္ကေတ properties (ဝိသေသလက္ခဏာများ) ပြောင်းလဲလိုက်သည်နှင့်  သင်္ကေတ ဖော်ပြမှုများတပြိုင်နက်ပြောင်းလဲသွားမည်ဖြစ်ပါသည်။

သင်္ကေတ tree item များ၏ ရွေးချယ်ထားသောအဆင့်ပေါ်မူတည်၍ အသုံးပြုနိုင်သည့် tools များရှိပါသည်-

* |symbologyAdd| သင်္ကေတ layer တစ်ခုထပ်ပေါင်းထည့်ခြင်း - မိမိလိုချင်သလောက် သင်္ကေတများကို ဆင့်ထပ်ပြသနိုင်ပါသည်။
* |symbologyRemove| ရွေးချယ်ထားသော သင်္ကေတ layer ကို ဖယ်ထုတ်ခြင်း။
* သင်္ကေတ layer ၏ အရောင်ကို ပြောင်းခွင့်ပိတ်ခြင်း (lock ပြုလုပ်ခြင်း)။ ပင်မသင်္ကေတ (global symbol) (သို့မဟုတ် အထက်ဆင့် ရှိ) သင်္ကေတများ အရောင်ပြောင်းလိုက်ချိန်တွင်  |locked| lock ပြုလုပ်ထားသော အရောင်မှာ ပြောင်းလဲမည် မဟုတ်ပါ။
* |duplicateLayer| သင်္ကေတ layer တစ်ခု သို့မဟုတ် အုပ်စုတစ်ခု ကို duplicate (မိတ္တူပွား) ပြုလုပ်ခြင်း။
* သင်္ကေတ layer ကို ‌အပေါ်အောက် ရွှေ့ခြင်း။

.. _edit_symbol:

Configuring a symbol (သင်္ကေတတစ်ခုကို ပြင်ဆင်သတ်မှတ်ခြင်း)
===========================================================

QGIS တွင် symbol တစ်ခုကို ပြင်ဆင်သတ်မှတ်ခြင်းကို အဆင့်နှစ်ဆင့်ဖြင့် လုပ်ဆောင်သည်။ ၄င်းတို့မှာ သင်္ကေတ အဆင့်နှင့် သင်္ကေတ layer အဆင့်တို့ဖြစ်ပါသည်။

The symbol (သင်္ကေတ)
---------------------

ဖွဲ့စည်းပုံ (Tree) ၏ ထိပ်ပိုင်းတွင် ဂျီဩမေတြီ layer ပေါ်မူတည်၍ **Marker (အမှတ်)**၊ **Line (လိုင်း)** သို့မဟုတ် **Fill (အဖြည့်)** ပုံစံများ ဖြစ်နိုင်ပါသည်။
သင်္ကေတတစ်ခုစီတွင် တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော သင်္ကေတများ (အခြား အမျိုးအစားတစ်ခုခု အပါအဝင်) သို့မဟုတ် သင်္ကေတ layer များကို ထည့်သွင်းနိုင်သည်။

အချို့သော parameter (သတ်မှတ်ချက်) များကို ပင်မ (global) သင်္ကေတ ဖန်တီးရန် သတ်မှတ် (setup) ပြုလုပ်နိုင်သည်-

* :guilabel:`Unit` - ယူနစ်သည် **Millimeters (မီလီမီတာ)** ၊ **Points (ပွိုင့်)** ၊ **Pixels** ၊  **Meters at Scale (မီတာစကေး)** ၊ **Map units (မြေပုံတွင်သုံးထားသည့်ယူနစ်)** သို့မဟုတ် **Inches (လက်မ)** ဖြစ်နိုင်ပါသည်။ (အသေးစိတ်ကို :ref:`unit_selector` တွင်ဖော်ပြထားပါသည်။)
* :guilabel:`Opacity` (အလင်းပိတ်နှုန်း)
* :guilabel:`Color` (အရောင်) - Parameter ကို ပြောင်းလဲလိုက်သည့်အခါ value (တန်ဖိုး) သည် lock မလုပ်ထားသော sub-symbols (သင်္ကေတအခွဲများ) အ‌ရောင်အားလုံးသို့ သက်ရောက်သွားပါမည်။
* :guilabel:`Size` (အရွယ်) နှင့် :guilabel:`Rotation` (အလှည့်) သည် marker (အမှတ်) သင်္ကေတများအတွက်ဖြစ်သည်။
* :guilabel:`Width` (အထူ) သည် line သင်္ကေတများအတွက်ဖြစ်သည်။

  .. tip::

    ပါဝင်သည့် သင်္ကေတအလွှာအဆင့်များတွင် :ref:`symbol layers <symbol_layer>` အတိုင်းအတာများအားလုံးကို အချိုးကျအရွယ်အစားပြောင်းရန် :guilabel:`Size` အရွယ်အစား (marker သင်္ကေတအတွက်) သို့မဟုတ် :guilabel:`Width` လိုင်းအထူ (line သင်္ကေတအတွက်) properties ကိုအသုံးပြုပါ။

  .. note::

    Style manager dialog မှ သင်္ကေတကိုသတ်မှတ်လိုက်သောအခါ width (အထူ)၊ size (အရွယ်အစား) သို့မဟုတ် rotation (အလှည့်) parameter များဘေးရှိ :ref:`Data-defined override <data_defined>` ခလုတ်သည် အသက်ဝင်မည်မဟုတ်ပါ။
    သင်္ကေတ ကို Map layer နှင့်ချိတ်ဆက်ထားပါက ထိုခလုတ်သည် :ref:`proportional or multivariate analysis <proportional_symbols>` ပုံဖော်ပြသခြင်းကို ဖန်တီးနိုင်ပါမည်။

* :ref:`symbols library <vector_style_manager>` ကို အစမ်းကြည့်ခြင်း (preview) - အမျိူးအစားတူသော သင်္ကေတများကို ပြသထားပြီး ပြင်ဆင်နိုင်သော drop-down list တွင် free-form text သို့မဟုတ် :ref:`categories <group_symbols>` (အုပ်စု) အလိုက် စစ်ထုတ်နိုင်ပါသည်။ |styleManager| :sup:`Style Manager` ကိုအသုံးပြုခြင်းဖြင့်လည်း သင်္ကေတစာရင်းကို update ပြုလုပ်နိုင်ပြီး  သင်္ကေတတစ်ခုခြင်းကို dialog ဖြင့် ဖွင့်နိုင်သည်။ ထိုနေရာတွင် :ref:`vector_style_manager` ထဲတွင်ဖော်ပြထားသော လုပ်ဆောင်ချက်များကို အသုံးပြုနိုင်ပါသည်။

  သင်္ကေတများကို အောက်ပါပုံစံနှစ်မျိုးဖြင့်ဖော်ပြသည်- 

  * Frame ၏ အောက်ခြေရှိ |openTable| :sup:`List View` ခလုတ် ကိုအသုံးပြု၍ icon list (thumbnail ၊ အမည် နှင့် associated tags (သက်ဆိုင်ရာပူးတွဲများ)) အတွင်း ဖော်ပြခြင်း၊  
  * သို့မဟုတ် |iconView| :sup:`Icon View` ခလုတ်အသုံးပြု၍ icon နမူနာပုံစံ (preview) အနေဖြင့် ဖော်ပြခြင်း၊

* ပြင်ဆင်ထားသော သင်္ကေတများကို သင်္ကေတ library ထဲထည့်ရန် :guilabel:`Save Symbol` ခလုတ်ကိုနှိပ်ပါ။
* :guilabel:`Advanced` |selectString| option ထဲတွင်-

  * Line နှင့် အဖြည့် သင်္ကေတများအတွက် :guilabel:`Clip features to canvas extent`

    .. Todo: Explain what does advanced "clip features to canvas" option mean for the symbol?

  * အဖြည့် သင်္ကေတများအတွက် :guilabel:`Force right-hand rule orientation` (လက်ျာရစ်စနစ်အတိုင်းလှည့်ခြင်း) - ကွင်းတစ်ခုတွင် လိုင်း၏အဆစ်ထောင့် (vertex) များ၏အစီအစဉ် (ring orientation) သည်  "right hand rule" စံသတ်မှတ်ချက်ကိုလိုက်နာသည့် အဖြည့် သင်္ကေတကို ဖန်တီးနိုင်ပါသည်။ (ဆိုလိုသည်မှာ polygon များတွင် အပြင်ဖက်အနား (exterior ring) ၏ အနားသတ်လိုင်း၏အဆစ်ထောင့်များသည် နာရီလက်တံလှည့်သည်အတိုင်း အစီအစဉ်ဖြစ်ပြီး အတွင်းရှိအပေါက် (interior) များ၏ ring များသည် နာရီလက်တံပြောင်းပြန် ဖြစ်သည်။)

    Orientation fix သည် ပုံအဖြစ် ပြသ‌နေသည့်အအချိန်တွင်သာ သက်ရောက်မှုရှိပြီး feature ဂျီဩမေတြီသည် ပြောင်းလဲမည်မဟုတ်ပါ။ ပုံဖော်ပြသနေသည့် feature တစ်ခုချင်းစီ၏ ring orientation များ မည်သို့ပင်ရှိနေသည်ဖြစ်စေ ဤနည်းအားဖြင့် အဖြည့် သင်္ကေတများကို တစ်ပြေးညီအသွင်အပြင် ဖြင့် ပြသပေးနိုင်သည်။

  * Layer ၏ :ref:`symbology <vector_style_menu>` ပေါ်မူတည်၍   သင်္ကေတကို ပြောင်းလဲမည်ဖြစ်ပြီး :guilabel:`Advanced` menu တွင် နောက်ဆက်တွဲ setting (အပြင်အဆင်) များ အသုံးပြုနိုင်ပါသည်-

    * :ref:`Symbol levels... <Symbols_levels>` သည် သင်္ကေတများကို ပုံဖော်ရမည့် ရှေ့ နောက်အစီအစဥ် ကိုသတ်မှတ်သည်
    * :ref:`Data-defined Size Legend <data_defined_size_legend>` - အရွယ်အစားတန်ဖိုးကို data မှရယူအသုံးပြုခြင်း
    * :guilabel:`Match to Saved Symbols...` (ရှိပြီးသား သင်္ကေတများနှင့် တူညီရန်) နှင့် :guilabel:`Match to Symbols from File...` (ဖိုင်ထဲရှိ သင်္ကေတများနှင့် တူညီရန်) များဖြင့် :ref:`(assign symbols to classes) <categorized_advanced_menu>` class အမျိုးအစားများကို အလိုအလျောက် သင်္ကေတ သတ်မှတ်ရန်

.. _symbol_layer:

The symbol layer (သင်္ကေတ layer)
---------------------------------

ဖွဲ့စည်းပုံ (tree) ၏ အောက်ခြေ အဆင့်တွင် သင်္ကေတ layer ကို မိမိစိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ သင်္ကေတ layer အမျိုးအစားများသည်  အထက်ဆင့်တွင်ရှိသည့် သင်္ကေတ အမျိုးအစားပေါ်မူတည်ပါသည်။
သင်္ကေတများကို ပုံဖော်ပြသရာတွင် ပိုမိုကောင်းမွန်စေရန် paintEffects| :ref:`paint effects <draw_effects>` ကို သင်္ကေတ layer အတွက်ဆောင်ရွက်နိုင်ပါသည်။

သင်္ကေတ layer အမျိုးအစားအားလုံး၏ လုပ်ဆောင်နိုင်သည့်အချက်များ (option) အားလုံးကို ဖော်ပြရန် မဖြစ်နိုင်သောကြောင့်၊ အရေးအကြီးဆုံးနှင့် အရေးပါသော အရာများကိုသာ အောက်တွင် ဖော်ပြထားပါသည်။

Common parameters (အသုံးများသည့်သတ်မှတ်ချက်များ)
.................................................

သင်္ကေတ layer တည်ဆောက်ရာတွင်  marker (အမှတ်)၊ line (လိုင်း) သို့မဟုတ် fill (အဖြည့်) မည်သည့်အမျိုးအစားအတွက်မဆို အသုံးပြုနိုင်သည့် တူညီသည့်ရွေးချယ်စရာ (common option) နှင့် widget များရှိသည်- 

* :ref:`color selector <color-selector>` (အရောင်ရွေးချယ်သည့်အရာ) ကို အရောင်ခြယ်ရာတွင် လွယ်ကူစေရန် အသုံးပြုနိုင်သည်။
* :guilabel:`Units` (ယူနစ်) သည် **Millimeters (မီလီမီတာ)** ၊ **Points (ပွိုင့်)** ၊ **Pixels** ၊ **Meters at Scale (မီတာစကေး)** ၊ **Map units (မြေပုံယူနစ်များ)** သို့မဟုတ် **Inches  (လက်မ)** ဖြစ်နိုင်ပါသည် (အသေးစိတ်ကို :ref:`unit_selector` တွင်ဖော်ပြထားပါသည်။)
* |dataDefine| :sup:`Data-defined override` widget သည် option တိုင်းနီးပါးတွင် သင်္ကေတများကို စိတ်ကြိုက်ချဲ့ထွင်မှုများပြုလုပ်နိုင်စေသည်။ (အသေးစိတ်ကို :ref:`data_defined` တွင်ဖော်ပြထားပါသည်)
* |checkbox| :guilabel:`Enable symbol layer` option သည် သင်္ကေတ layer ၏ မြင်ရနိုင်မှု (visibility) ကို ထိန်းချုပ်သည်။ ပိတ်ထားသော (disabled) သင်္ကေတ layer များကို ပုံဖော်ပြသရာတွင် မရေးဆွဲသော်လည်း ၄င်းတို့ကို သင်္ကေတဖွဲ့စည်းပုံထဲတွင် ဆက်လက်သိမ်းဆည်းထားပါသည်။ အကောင်းဆုံး သင်္ကေတ ဒီဇိုင်းကိုရရှိရန် ရှာဖွေနေစဉ်တွင် (မလိုသည့်) သင်္ကေတ layer များကို မဖယ်ရှားဘဲ ၎င်းတို့ကို ပိတ်ပြီး စမ်းသပ်နိုင်ခြင်းသည် ပိုမိုအဆင်ပြေစေသည့်နည်းလမ်းဖြစ်ပါသည်။ ဖြည့်ရမည့် အချက်အလက်များကို ဒေတာမှရယူအသုံးပြုခြင်း (data-defined) က အားလုံးကိုလွှမ်းမိုးလုပ်ဆောင်သည့်အတွက် သင်္ကေတ layer များကို ပိတ်ထားခြင်း သို့မဟုတ် ဖွင့်ထားခြင်းများကို Expression ဖြင့် ပြုမည်ဆိုပါကလုပ်နိုင်ပါသည်။ (ဉပမာ- feature attribute များ)
* |checkbox| :guilabel:`Draw effects` (ရေးဆွဲပုံဖော်နည်းများ) သည် :ref:`effects rendering <draw_effects>` အတွက် ခလုတ်ဖြစ်ပါသည်။

.. note:: အောက်တွင်ဖော်ပြထားသောဖော်ပြချက်သည် သင်္ကေတ layer အမျိုးအစားသည် feature ဂျီဩမေတြီ နှင့် ဆက်စပ်နေသည်ဟု ယူဆနိုင်သော်လည်း သင်္ကေတ layer များသည် တစ်ခုအတွင်း အခြားတစ်ခု ထည့်သွင်း ပေါင်းစည်းနိုင်သည်။ ယင်းအခြေအနေတွင် အတွင်းကျသည့် (lower level) သင်္ကေတ layer ၏ အချက်အလက်များ (parameter) ဖြစ်သည့် နေရာချထားပုံ (placement)၊ နေရာမှန်မှခွဲခွာဖော်ပြခြင်း  (offset) စသည့်များသည် feature ဂျီဩမေတြီ ကိုယ်တိုင်တွင် မချိတ်ဆက်ပဲ အပြင်ဖက်/အထက်အဆင့် (upper level) သင်္ကေတများနှင့် ချိတ်ဆက်နိုင်သည်။

.. _vector_marker_symbols:

Marker Symbols (တည်နေရာအမှတ်အသား သင်္ကေတများ)
..............................................

Point (တည်နေရာအမှတ်) ဂျီဩမေတြီ feature များအတွက် သင့်လျော်ပြီး အမှတ်အသားသင်္ကေတ (marker symbol) များတွင် :guilabel:`သင်္ကေတ layer အမျိုးအစား` များစွာရှိပါသည်-

.. _simple_marker_symbol:

* **Simple marker (ရိုးရှင်းသည့် အမှတ်သင်္ကေတ** (default)

  .. _figure_simple_marker_symbol:

  .. figure:: img/simpleMarkerSymbol.png
     :align: center

     ရိုးရှင်းသည့် အမှတ်သင်္ကေတ (Marker Symbol) တစ်ခုကို ဒီဇိုင်းရေးဆွဲခြင်း။

  ရိုးရှင်းသည့် အမှတ်သင်္ကေတ layer အမျိုးအစားတွင် အောက်ဖော်ပြပါ ဂုဏ်သတ္တိ (properties) များရှိပါသည်-

  * :guilabel:`Size` (အရွယ်အစား) တွင် ယူနစ်အမျိုးမျိူးအသုံးပြုနိုင်သည်။
  * :guilabel:`Fill color` (အဖြည့်အရောင်)
  * :guilabel:`Stroke color` (လိုင်းအရောင်) ၊ ကြိုတင်ထည့်ထားသည့်စာရင်း (list) မှ :guilabel:`Stroke style` (လိုင်း၏အဆင်) နှင့် :guilabel:`Stroke size` (လိုင်းအထူအရွယ်အစား)
  * :guilabel:`Join style` (လိုင်းတစ်ခုနှင့်တစ်ခုထိစပ်ပုံ) သည် **Bevel (စောင်းသတ်)** ၊ **Miter (စောင်းတိ)** သို့မဟုတ် **Round (စောင်းလုံး)** ဖြစ်နိုင်သည်။
  * :guilabel:`Cap style` (လိုင်းထိပ်နှစ်ဘက်) သည် **Square (လေးထောင့်)** ၊ **Flat (အပြား)** သို့မဟုတ် **Round (အလုံး)** ဖြစ်နိုင်သည်။
  * :guilabel:`Rotation` (လှည့်ထောင့်)
  * :guilabel:`Offset` ကို feature ၏ :guilabel:`X` နှင့် :guilabel:`Y` ဝန်ရိုးများအတွက် သတ်မှတ်နိုင်သည်။
  * :guilabel:`Anchor point` - ဆိုသည်မှာ သင်္ကေတ၏ အရပ်လေးမျက်နှာ ထောင့် တစ်ခုခုတွင် မူလချထားနေရာအဖြစ် သတ်မှတ်သည့် အမှတ်ဖြစ်သည်။ ဤအမှတ် point သည် :guilabel:`Offset` အပေါ် သက်ရောက်မှု ရှိသည်။

* **Ellipse marker (ဘဲဥပုံအမှတ်အသား)** သည် အကျယ်နှင့် အမြင့်ကို ပြင်ဆင်နိုင်သည့် simple marker သင်္ကေတ တစ်ခု ဖြစ်သည်။
* **Filled marker** သည် :ref:`fill sub symbol <vector_fill_symbols>` ကိုအသုံးပြုပြီး marker ကို ပုံဖော်သည်မှလွဲ၍ simple marker သင်္ကေတ နှင့်ဆင်တူဖြစ်သည်။ ၎င်းသည် လက်ရှိသုံးနေသည့် QGIS ၏ အဖြည့် (fill) နှင့်  လိုင်းစုတ်ချက် (stroke) များအားလုံးကို marker များ ပုံဖော်ပြရာတွင် အသုံးပြုနိုင်စေသည်။ ဥပမာ- ရောင်ပြေး (gradient) သို့မဟုတ် shapeburst fills များ
* **Font marker (ဖောင့်)** - သည် marker marker ပြုလုပ်ရန်အတွက် ထည့်ထားသည့် ဖောင့် (fonts) များကိုသုံးသည်မှလွဲ၍ simple marker သင်္ကေတ နည်းတူဖြစ်သည်။ နောက်ထပ်အပိုပါဝင်လာသည့် properties များမှာ-

  * :guilabel:`Font family` (ဖောင့်အုပ်စု)
  * :guilabel:`Font style` (ဖောင့်ပုံစံ)
  * :guilabel:`Character(s)` သည် စာသားဖြင့်ဖော်ပြသော သင်္ကေတ ဖြစ်သည်။
    ၄င်းတွင် စာရိုက်၍ သော်လည်းကောင်း font ရွေးချယ်၍ သော်လည်းကောင်း font characters widget တွင်ရွေးချယ်နိုင်သည်။
    ထို့ပြင် :guilabel:`Preview` ကို နှိပ်၍ ရွေးချယ်ထားသော setting များ အရဖြစ်လာမည့် အနေအထားကို ကြိုကြည့် (preview) နိုင်သည်။

* **Geometry generator** (:ref:`geometry_generator_symbol` တွင်ဖော်ပြထားပါသည်)

.. _mask_marker_symbol:

* **Mask** - ၎င်း၏ သင်္ကေတခွဲသည် mask shape (အဖုံးအကာသဏ္ဍာန်) တစ်ခုသတ်မှတ်လိုက်ပြီး ထို mask shape ၏ အရောင် property ကို လစ်လျူရှုနိုင်ပြီး အလင်းပိတ်မှု (opacity) ကိုသာ အသုံးပြုမည်ဖြစ်ပါသည်။ Marker သင်္ကေတ သည် စာများ သို့မဟုတ်အခြား အရောင်ခြင်းဆင်တူသည့်သင်္ကေတ များနှင့် ရောယှက်ထပ်နေသည့်အခါ ဖြစ်သည့် ဖတ်ရခက်ခဲမှုကို ရှင်းလင်းအဆင်ပြေစေပါသည်။ အသေးစိတ်ကို :ref:`vector_mask_menu` တွင်ဖော်ပြထားပါသည်။

.. _raster_image_marker:

* **Raster image marker ပုံများ** - Image (ရုပ်ပုံ) တစ်ခု (:file:`PNG` ၊ :file:`JPG` ၊ :file:`BMP` ...) ကို marker သင်္ကေတ အဖြစ်အသုံးပြုခြင်းဖြစ်သည်။ အသုံးပြုသည့် image သည် disk ပေါ်ရှိ ဖိုင်တစ်ခုသော် လည်းကောင်း၊ အခြား တစ်နေရာကိုညွှန်းသည့် URL အဖြစ်လည်းကောင်း၊ style database ထဲတွင်ထည့်ထားသည့်ပုံ သော်လည်းကောင်း (:ref:`more details <embedded_file_selector>`) သို့မဟုတ် base64 string အဖြစ် တိုက်ရိုက်ထည့် (encoded) သုံးခြင်းမျိုးဖြစ်နိုင်သည်။ Image ၏ အကျယ်နှင့် အမြင့်ကို ခွဲ သတ်မှတ်နိုင်သည် သို့မဟုတ် |lockedGray| :sup:`Lock aspect ratio` ကိုလည်းအသုံးပြုနိုင်သည်။ :ref:`common units <unit_selector>` (အသုံးများယူနစ်) တစ်ခုခုကိုအသုံးပြု၍ အရွယ်အစားကို သတ်မှတ်နိုင်သည် သို့မဟုတ် မူလပုံ၏ အရွယ်အစား ရာခိုင်နှုန်း (percentage) ဖြင့်လည်း သတ်မှတ်နိုင်သည်။ (ပုံ၏ မူလအကျယ်၏ အဆဖြင့် ချုံ့ခြင်း)
* **Vector Field marker** (:ref:`vector_field_marker` တွင်ဖော်ပြထားပါသည်)

.. _svg_marker:

* **SVG marker** - သည် SVG path (:menuselection:`Settings --> Options... --> System` menu ထဲတွင်သတ်မှတ်ပါ) များမှ image များဖြင့် marker သင်္ကေတ ပြုလုပ်နိုင်ရန် ထောက်ပံ့ပေးပါသည်။ သင်္ကေတ၏ အကျယ်နှင့် အမြင့်ကို လိုအပ်သလို သတ်မှတ်နိုင်သည် သို့မဟုတ် |lockedGray| :sup:`Lock aspect ratio` (အမြင့်-အကျယ်အချိုး) ကိုလည်းအသုံးပြုနိုင်သည်။ SVG ဖိုင် အရောင်များနှင့် လိုင်းပုံစံ (stroke) ကို လိုအပ်သလို ပြုလုပ်နိုင်သည်။  အသုံးပြု သည့် image သည် disk ပေါ်ရှိ ဖိုင်တစ်ခုသော် လည်းကောင်း၊ အခြား တစ်နေရာကိုညွှန်းသည့် URL အဖြစ်လည်းကောင်း၊ style database ထဲတွင်ထည့်ထားသည့်ပုံ သော်လည်းကောင်း (:ref:`more details <embedded_file_selector>`) သို့မဟုတ် base64 string အဖြစ် တိုက်ရိုက်ထည့်(encoded) သုံးခြင်းမျိုးဖြစ်နိုင်သည်။

  ထိုသင်္ကေတကို :guilabel:`Dynamic SVG parameters` များဖြင့်လည်း သတ်မှတ်နိုင်ပါသည်။
  SVG symbol တစ်ခုသတ်မှတ်ခြင်းအပိုင်းကို :ref:`svg_symbol` တွင်ဖော်ပြထားပါသည်။

  .. note:: SVG version requirements (SVG version လိုအပ်ချက်များ)

   QGIS သည် `SVG Tiny 1.2 profile
   <https://www.w3.org/TR/SVGMobile12/>`_  ကိုဆောင်ရွက်နိုင်သော SVG ဖိုင်များကို ဆဲလ်ဖုန်းနှင့် PDA များမှ laptop နှင့် desktop ကွန်ပျူတာများအထိ စက်ပစ္စည်းအမျိုးမျိုးတွင် အကောင်အထည်ဖော်ရန် ရည်ရွယ်ထားပြီး ဆဲလ်ဖုန်းနှင့် PDA များမှ သည် laptop နှင့် desktop ကွန်ပျူတာများအထိ စက်ပစ္စည်းအမျိုးမျိုးတွင် အသုံးပြုနိုင်ရန် ရည်ရွယ်ထားသည့်  `SVG Tiny 1.2 profile <https://www.w3.org/TR/SVGMobile12/>`_ သတ်မှတ်ချက်များကို လိုက်နာသည့် SVG file များကို QGIS သည်ပုံဖော်ပြသနိုင်ပါသည်။ ထို profile ထဲတွင် SVG 1.1 Full ထဲတွင်ပါသည့် အရာတစ်ချို့ နှင့်အတူ SVG ၏ စွမ်းဆောင်ရည်ကို ကျော်လွန်သည့် လုပ်ဆောင်ချက်အသစ်များလည်း ပါဝင်နေသည်။
   
   ဤသတ်မှတ်ချက်များတွင် မပါဝင်သော အချို့သော လုပ်ဆောင်ချက် (feature)  များကို QGIS တွင် မှန်ကန်စွာဆောင်ရွက်နိုင်မည်မဟုတ်ပါ။


.. _vector_line_symbols:

Line Symbol (Line သင်္ကေတ)
...........................

Line ဂျီဩမေတြီ feature များအတွက် သင့်လျော်သော line သင်္ကေတများတွင် အောက်ဖော်ပြပါ သင်္ကေတ Layer အမျိူးအစားများရှိပါသည်-

.. _simple_line_symbol:

* **Simple line (ရိုးရိုးလိုင်း)** (default)

  .. _figure_simple_line_symbol:

  .. figure:: img/simpleLineSymbol.png
     :align: center

     ရိုးရှင်းသည့် လိုင်းသင်္ကေတ (Line symbol) တစ်ခုကို ဒီဇိုင်းဆွဲခြင်း။

  ရိုးရှင်းသည့် line သင်္ကေတ layer အမျိုးအစားတွင် :ref:`simple marker symbol <simple_marker_symbol>` ကဲ့သို့ တူညီသော ဂုဏ်သတ္တိ (properties) များစွာ ရှိပါသည်။ ထို့အပြင်-

  * |checkbox| :guilabel:`Use custom dash pattern` (အသုံးပြုသူသတ်မှတ်ပေးသည့် မျဉ်းပြတ်ပုံစံ) သည် :guilabel:`Stroke style` setting ကို မိမိစိတ်ကြိုက်ဖြစ်သော မျဉ်းပြတ်ပုံစံအသစ် (dash) ဖြင့် အစားထိုးနိုင်သည်။  တစ်ဆက်တည်းရှိနေသည့် မျဉ်းပြတ်များ (dash) ၏အရှည်နှင့် ကြားအကွာအဝေးများကို သတ်မှတ်ပေးရန် လိုအပ်ပါသည်။ Pattern တစ်ခုလုံး၏ အလျားကို dialog အောက်ခြေတွင် ‌ဖော်ပြနေပါလိမ့်မည်။
  * :guilabel:`Pattern offset` (မူလနေရာမှ ခွာပြီးပြခြင်း) - ၎င်းတို့သည် ထောင့်ချိုးများတွင် ပိုမိုပုံစံကျ ရန်လိုပါက line ပေါ်တွင် မျဉ်းပြတ် နှင့် ကြားကွက်လပ်များ (dashes/spaces) ကို လိုအပ်သလို (ရှေ့ တိုး/နောက်ဆုတ်) နေရာချနိုင်သည်။ (ကပ်လျှက်ရှိသော dash pattern borders များနှင့် ထပ်တူညီစေရန် "align" ပြုလုပ်ပြီး အသုံးပြုနိုင်ပါသည်။)
  * |checkbox| :guilabel:`Align dash pattern to line length` သည် လိုင်းအဆုံးတွင် မျဉ်းပြတ်အဆုံးသည် ဟ မ‌နေ ပဲ ကွက်တိကျစေရန် အလျားကို ချိန်ညှိသွားပါလိမ့်မည်။
  * |checkbox| :guilabel:`Tweak dash pattern at sharp corners` သည် မျဉ်းပြတ်ကို ထောင့်ချိုးပေါ်တွင် အပြည့် ရှိစေပါသည်။ :guilabel:`Align dash pattern to line length` ကိုနှိပ်ထားမှသာ သက်ရောက်မှု ရှိသည်။
  * :guilabel:`Start` (အစ) တွင် သို့မဟုတ်  :guilabel:`End` (အဆုံး) အပိုင်းတွင် သို့မဟုတ် အစ နှင့် အဆုံး နှစ်ဖက်လုံးတွင် :guilabel:`Trim lines` (လိုင်းကိုဖြတ်တောက်ခြင်း) - လိုင်းအစနှင့် အဆုံးတွင် လိုအပ်သလို ဖြတ်တောက်ခြင်း ပြုလုပ်နိုင်သည်။ လိုင်းတစ်ခုလုံးအလျား၏ ရာခိုင်နှုန်း (%) အပါအဝင် အလျား :ref:`ယူနစ်များ <unit_selector>` အတော်များများကို ထောက်ပံ့ပေးထားပါသည်။ ၎င်းအပြင် ဒေတာမှ ရယူသတ်မှတ်ပေးနိုင်ပါသေးသည်။ လိုင်းအစ နှင့် အဆုံး တွင် အကွာအဝေးတစ်ခုဖြင့် ခွာထားခြင်းကို ဥပမာ- အဆင့်မြင့် သင်္ကေတများကို ဖန်တီးသောအခါ line layer သည် ၎င်း၏ အစနှင့် အဆုံးတွင် ရှိသော marker သင်္ကေတ layer များနှင့် ထပ်မနေစေချင်သည့်အခါ အသုံးပြုနိုင်ပါသည်။

.. _arrow_symbol:

* **Arrow** - မြှားခေါင်း တစ်ခု သို့မဟုတ် နှစ်ခုပါသော မျဉ်းများ (အကွေး သို့မဟုတ် အဖြောင့်) ကို ဆွဲရာတွင် အောက်ပါတို့ကို ရွေးချယ်နိုင်သည် (Data ဖြင့်လည်း သတ်မှတ်ပေးနိုင်သည်)-  

  * :guilabel:`Head type` (မြှားခေါင်းပုံစံ)
  * :guilabel:`Arrow type` (မြှားအမျိုးအစား)
  * :guilabel:`Arrow width` (မြှားအထူ)
  * :guilabel:`Arrow width at start` (မြှားအစပိုင်းအထူ)
  * :guilabel:`Head length` (မြှားခေါင်းအရှည်)
  * :guilabel:`Head thickness` (မြှားခေါင်းအထူ)
  * :guilabel:`Offset` (ဘယ်ညာအလွှဲ)

  |checkbox| :guilabel:`Curved arrows` မြှားအကွေး (line feature သည် အနည်းဆုံး vertices သုံးခုပါရှိရမည်) နှင့် |checkbox| :guilabel:`Repeat arrow on each segment` (လိုင်းအပိုင်းတိုင်းတွင် မြားများဆက်တိုက်ပြသည့်ပုံစံ) ကို ဖန်တီးနိုင်ပါသည်။
  မြှား၏ ကိုယ်ထည်ကို ပုံဖော်ရန် gradients သို့မဟုတ် shapeburst ကဲ့သို့ :ref:`fill symbol <vector_fill_symbols>` ကို အသုံးပြုနိုင်ပါသည်။
  ဂျီဩမေတြီ generator နှင့် တွဲသုံးပါက ဤမြှားသင်္ကေတ layer အမျိုးအစားသည် flow map များတွင် အသုံးဝင်ပါသည်။
* **Geometry generator** (:ref:`geometry_generator_symbol` တွင်ဖော်ပြထားပါသည်။)

.. _interpolated_line_symbol:

* **Interpolated line** သည် :guilabel:`Stroke width` (လိုင်းအထူ)
  နှင့်/သို့မဟုတ် :guilabel:`Color` (အရောင်) ကို လိုင်းတလျောက် တွင်‌ ပုံသေ (:guilabel:`Fixed width` နှင့် :guilabel:`Single color` parameter များ)  သို့မဟုတ် အပြောင်းအလဲ ရှိသည့် line တစ်ခုကို ပြုလုပ်နိုင်သည်။ အထူနှင့်အ‌ရောင်ကို ပြောင်းလဲစေလိုသောအခါ- 

  * :guilabel:`Start value` (အစ တန်ဖိုး) နှင့် :guilabel:`End value` (အဆုံးတန်ဖိုး) - feature ဂျီဩမေတြီ ၏ အစွန်းများတွင် ရှိမည့်တန်ဖိုးများသတ်မှတ်ခြင်း။ ၎င်းတို့သည် ပုံသေ တန်ဖိုးများဖြစ်နိုင်ပြီး feature ၏ attribute များ သို့မဟုတ် ခိုင်းစေချက် (expression) မှလာသောတန်ဖိုး တစ်ခုခုဖြစ်နိုင်သည်။
  * :guilabel:`Min. value` (အနိမ့်ဆုံးတန်ဖိုး) နှင့် :guilabel:`Max. value` (အမြင့်ဆုံးတန်ဖိုး) - ၎င်းတို့၏ ကြားထဲရှိတန်ဖိုးများကို တွက်ချက်ရယူသည်။ Layer အတွက် အနိမ့်ဆုံးနှင့် အမြင့်ဆုံး အစ/အဆုံး value များအပေါ် အခြေခံ၍ အလိုအလျောက်ဖြည့်ရန် |refresh| :sup:`Load` ခလုတ်ကို နှိပ်ပါ။
  * Stroke option (လိုင်းပုံစံရွေးချယ်မှု) အတွက်သာ ရရှိနိုင်ပါသည်-

    * လိုင်းအထူအတွက် :guilabel:`Min. width` (အနည်းဆုံးတန်ဖိုး) နှင့် :guilabel:`Max. width` (အများဆုံးတန်ဖိုး) သည်ပြောင်းလဲနိုင်သည့်လိုင်းအထူအပါး ပမာဏအပိုင်းအခြားကို သတ်မှတ်ပေးပါသည်။  
      :guilabel:`Min. width` သည်  :guilabel:`Min. value` ကို သတ်မှတ်ပြီး  :guilabel:`Max. width` သည် :guilabel:`Max. value` ကို သတ်မှတ်ပေးပါသည်။
      :ref:`unit <unit_selector>` (ယူနစ်) အမျိုးအစားကိုသတ်မှတ်ပေးနိုင်သည်။
    * |checkbox| :guilabel:`Use absolute value` - Interpolation ပြုလုပ်ရာတွင် absolute value (ပကတိတန်ဖိုး) အဖြစ် မှတ်ယူပါသည်။ (အနုတ် value များကို အပေါင်း value များအဖြစ် ပြောင်းလဲအသုံးပြုပါသည်)
    * |checkbox| :guilabel:`Ignore out of range` - default (ပုံမှန်) အားဖြင့် feature တစ်ခု၏ ``[start value - end value]`` အစ နှင့် အဆုံး တန်ဖိုးများသည်  ``[min. value - max. value]`` အနည်းဆုံး နှင့် အများဆုံးတန်ဖိုး အပိုင်းအခြားအတွင်း မရှိပါက ကျော်လွန်နေသာ အပိုင်းများ၏ လိုင်းအထူပမာဏကို ထိုအနည်းဆုံး နှင့် အများဆုံးတန်ဖိုးများ အတိုင်း သတ်မှတ်ပေးသည်။ ၎င်း ကျော်လွန်နေသောအပိုင်းများကို လုံးလုံး မပြသလိုပါက ဤ option ကို နှိပ်ထားပါ။
  * အရောင်အမျိုးမျိုးပြောင်းရန်အတွက် :ref:`color ramp classification <color_ramp_shader>` ၏ interpolation နည်းလမ်းများထဲမှ တစ်ခုခုကို အသုံးပြုနိုင်ပါသည်။

  .. _figure_interpolated_line_symbol:

  .. figure:: img/interpolatedLineSymbol.png
     :align: center
     :width: 100%

     Interpolation လုပ်ဆောင်ထားသည့် Line ဥပမာ ပုံစံများ

.. _marker_line_symbol:

* **Marker line** - :ref:`marker symbol
  <vector_marker_symbols>` ကို line တလျှောက်ပေါ်တွင် ထပ်ခါတလဲလဲဖြစ်ပေါ်စေသည်။

  * :guilabel:`Marker placement` (နေရာချထားပုံ) ကို အကွာအဝေးညီညီ interval setting သုံး၍ လည်းကောင်း၊ (ပထမဆုံး vertex မှ စတင်ပါ) line ဂျီဩမေတြီ property ကိုသုံး၍ လည်းကောင်း သတ်မှတ်နိုင်သည်။ (ပထမဆုံး သို့မဟုတ် နောက်ဆုံး vertex ၊ အတွင်းပိုင်း vertex များ၊ အပိုင်းတစ်ခုချင်းစီ၏ အလယ် point သို့မဟုတ် line ၏ အလယ် point သို့မဟုတ် မျဉ်းကွေးအမှတ် (curve point) အားလုံးပေါ်တွင်)
  * ပထမ သို့ မဟုတ် နောက်ဆုံး vertex placement ကို ယူထားသောအခါ |checkbox| :guilabel:`Place on every part extremity - အပိုင်းတိုင်း၏အစွန်းတိုင်းတွင်ဖော်ပြရန်` ရွေးချယ်ခွင့် (option) သည် multipart geometries မှ အစိတ်အပိုင်းအားလုံး၏ ပထမဆုံး နှင့် နောက်ဆုံး vertex နေရာတွင် marker များကိုဖော်ပြပေးပါလိမ့်မည်။
  * :guilabel:`Offset along line - လိုင်းပေါ်တွင်နေရာရွေ့ခြင်း` - Markers placement ကို line တလျှောက် နေရာရွေ့ချ (offset) ရာတွင် :ref:`unit <unit_selector>` (ယူနစ်) တစ်ခုခု သုံး၍ သတ်မှတ်ပေးနိုင်သည်။ (မီလီမီတာ၊ ပွိုင့်၊ မြေပုံယူနစ်၊ မီတာစကေး၊ ရာခိုင်နှုန်း စသည့်ယူနစ်များဖြင့်)
    
    * အရွေ့ (offset) တန်ဖိုးများသည် အပေါင်းဖြစ်ပြီး (:guilabel:`On first vertex` နှင့် :guilabel:`With interval` placements ယူထားပါက) Marker သင်္ကေတကို လိုင်းဦးတည်ရာဘက်အတိုင်းရွှေ့ ပေးပြီး၊  (:guilabel:`On last vertex` placement ကို ယူထားပါက) Marker သင်္ကေတကို နောက်ပြန်နေရာ ရွေ့ပေးသည်။
    * မပိတ်သော  line ပေါ်တွင် အနှုတ် တန်ဖိုးများသည် (:guilabel:`On first vertex` နှင့် :guilabel:`On last vertex` placements အတွက်) မည်သို့မျှသက်ရောက်မှုမရှိပါ။ သို့မဟုတ် နောက်ဆုံး vertex ဘက်မှ နေပြီး သင်္ကေတကို အနောက်ဖက် ရွှေ့ပေးသည်။
    * အစနှင့် အဆုံး ဆက်မိသော ကွင်းလိုင်း (ring) တွင် QGIS သည် အရွေ့ (offset) တန်ဖိုးဖြင့် Marker များကို ကွင်းတစ်ပါတ်လည် လိုက်ရွေ့စေသည် (အရှေ့ဘက် သို့မဟုတ် နောက်ပြန်)
      ဥပမာ- offset ကို 150% (resp. -10% သို့မဟုတ် -110%) ထားပါ ကွင်းလိုင်း (ring) အရှည်၏ တစ်ဝက် 50% (resp. 90%) နှင့် အညီ နေရာရွှေ့ပြပါလိမ့်မည်။

  * |checkbox| :guilabel:`Rotate marker to follow line direction` (လိုင်းဦးတည်ရာ အတိုင်း Marker ကို လှည့်စေခြင်း) - ထိုရွေးချယ်ခွင့်သည် လိုင်း၏ဦးတည်ရာနှင့်ယှဉ်ပြီး marker များကို လှည့်စေပါသည်။

    Line တစ်ခုသည် များသောအားဖြင့် ဦးတည်ချက်မတူသော လိုင်းတိုအစိတ်အပိုင်းများဖြင့် ပေါင်းစပ်ထားသောကြောင့် marker လှည့်ရမည့် ထောင့် အတွက် တန်ဖိုးကို သတ်မှတ်ထားသည့် အကွာအဝေးတစ်ခုအတွင်းရှိ မျဉ်းတိုများ၏ ပျှမ်းမျှဦးတည်ရာ ထောင့် အဖြစ် တွက်ချက်ပြီး အသုံးပြုသည်။ ဥပမာ- :guilabel:`Average angle over` ၏ တန်ဖိုး ကို ``4mm`` ဟုထားလိုက်ပါက သင်္ကေတ ချမည့် နေရာ ရှေ့ 2mm နှင့် နောက်ဖက် 2mm  ရှိအမှတ်နှစ်မှတ် ကို သုံးပြီး သင်္ကေတ အတွက် လိုင်းလားရာ ထောင့် ကိုတွက်ချက်ခြင်းဖြစ်သည်။ ၄င်းသည် line ဦးတည်ချက်မှ သွေဖယ်မှု အသေးအမွှားများကို ဖြည်ချောခြင်း (သို့မဟုတ် ဖယ်ထုတ်ခြင်း) ဖြစ်စေပြီး marker များ၏အလှည့် ကို အမြင်တွင်ပိုမိုကြည့်ကောင်းစေသည်။
  * :guilabel:`Line offset` (လိုင်း၏ဘယ်ညာအရွေ့) - marker သင်္ကေတကို line feature ၏ဘေးဘက် တွင်ပေါ်စေရန် ဘယ်ညာရွေ့ (offset) နိုင်သည်။

.. _hashed_line_symbol:

* **Hashed line** သည် line သင်္ကေတ တစ်လျှောက်တွင် line အတိုတစ်ခုကို ထပ်တလဲလဲ ပေါ်စေရန် ( hash တစ်ခု) ပြုလုပ်ခြင်းဖြစ်သည်။ လိုင်းတိုပေါ်တွင် နောက်ထပ်လိုင်းအတိုများပါဝင်နိုင်သည်။ တနည်းအားဖြင့် hashed line သည် marker သင်္ကေတ ကို segment များဖြင့် အစားထိုးထားသော marker line ပုံစံဖြစ်သည်။ ထို့ကြောင့် hashed line တွင် marker line သင်္ကေတကဲ့သို့ :ref:`same properties <marker_line_symbol>` (တူညီသောဂုဏ်သတ္တိများ) ရှိပါသည်။
  ၄င်းနှင့်အတူ-

  * :guilabel:`Hash length` (လိုင်းတို၏အရှည်)
  * :guilabel:`Hash rotation` (လိုင်းတို၏အလှည့်) ဂုဏ်သတ္တိများပါရှိပါသည်။

  .. _figure_hashed_line_symbol:

  .. figure:: img/hashedLineSymbol.png
     :align: center
     :width: 100%

     Hashed lines ဥပမာ ပုံစံများ

.. _raster_line_symbol:

* **Raster line** သည် line တလျှောက်တွင် raster image များဖြင့် ပုံဖော်ထားသော line သင်္ကေတ ဖြစ်သည်။ :guilabel:`Stroke width (လိုင်းအထူ)` ၊ :guilabel:`Offset (ဘယ်ညာအရွေ့တန်ဖိုး)` ၊ :guilabel:`Join style (လိုင်းအဆက်ပုံစံ)` ၊ :guilabel:`Cap style (လိုင်းထိပ်အုပ်ပုံစံ)` နှင့် :guilabel:`Opacity (အလင်းပိတ်နှုန်း)` များကို လိုအပ်သလို ချိန်ညှိနိုင်သည်။

  .. _figure_raster_line_symbol:

  .. figure:: img/rasterLineSymbol.png
     :align: center
     :width: 100%

     Raster lines ဥပမာ ပုံစံများ

.. _lineburst_symbol:

* **Lineburst** သည် line ၏ အထူကို gradient ဖြင့် ခြယ်ထားသော line သင်္ကေတ ဖြစ်သည်။
  :guilabel:`Two color (နှစ်ရောင်)` သို့မဟုတ် :guilabel:`Color ramp (ရောင်စဉ်တန်း)` အကြား ရွေးချယ်နိုင်ပြီး :guilabel:`Stroke width (လိုင်းအထူ)` ၊ :guilabel:`Offset (ဘယ်ညာအရွေ့တန်ဖိုး)` ၊ :guilabel:`Join style (လိုင်းအဆက်ပုံစံ)` ၊ :guilabel:`Cap style (လိုင်းထိပ်အုပ်ပုံစံ)` များကို လိုအပ်သလို ချိန်ညှိနိုင်သည်။

  .. _figure_lineburst_symbol:

  .. figure:: img/lineburstSymbol.png
     :align: center
     :width: 100%

     Lineburst lines ဥပမာ ပုံစံများ


.. _vector_fill_symbols:

Fill Symbols (အဖြည့် သင်္ကေတများ)
..................................

Polygon (ဧရိယာအဝန်းအဝိုင်း) ဂျီဩမေတြီ feature များအတွက် သင့်လျော်ပါသည်။ အဖြည့် (fill) သင်္ကေတ တွင် သင်္ကေတ layer အမျိုးအစားများစွာရှိပါသည်-

* **Simple fill** (default) - polygon တစ်ခုကို အရောင် တစ်ရောင်တည်းချယ်ပါသည်။

  .. _figure_simple_fill_symbol:

  .. figure:: img/simpleFillSymbol.png
     :align: center

     Simple Fill သင်္ကေတ တစ်ခု ဒီဇိုင်းပြုလုပ်ခြင်း

* **Centroid fill** သည် မြင်ရသော feature ၏ အလယ်မှတ် (centroid) တွင် :ref:`marker symbol <vector_marker_symbols>` ကိုဖော်ပြသည်။ Marker ၏ နေရာသည် feature ၏ အလယ်မှတ် အစစ်အမှန် မဖြစ်နိုင်ပေ၊ အဘယ်ကြောင့်ဆိုသော် အလယ်မှတ်ကိုတွက်ချက်ရာတွင်  map canvas မြင်ကွင်းက ဖြတ်တောက်ပြသော polygon ၏ ဧရိယာကိုသာထည့်သွင်းတွက်ချက်ခြင်း ၊ အပေါက်များကို လျစ်လျူရှုခြင်း စသည်တို့ကြောင့် ဖြစ်သည်။ Centroid အတိအကျကို လိုချင်ပါက :ref:`geometry generator symbol <geometry_generator_symbol>` ကိုအသုံးပြုပါ။

  ဆက်လက်၍-

  * :guilabel:`Force placement of markers inside polygons` (Marker များကို အမြဲ polygon အတွင်းတွင်ထားခြင်း)
  * :guilabel:`Draw markers on every part of multi-part features` (Marker များကိုအစိတ်အပိုင်းတစ်ခုစီအတွက်ဆွဲခြင်း) သို့မဟုတ် အကြီးဆုံးအစိတ်အပိုင်းနေရာတွင်သာ ထားရှိခြင်း။
  * Marker သင်္ကေတ (များ) ကို တစ်ခုလုံး သို့မဟုတ် တစ်စိတ်တစ်ပိုင်းပေါ်တွင် ဖော်ပြခြင်း ၊ အစိတ်အပိုင်းများကို လက်ရှိ feature ဂျီဩမေတြီ (:guilabel:`Clip markers to polygon boundary`) သို့မဟုတ် သင်္ကေတနှင့် သက်ဆိုင်သည့် ဂျီဩမေတြီ အပိုင်းနှင့် (:guilabel:`Clip markers to current part boundary only`) ထပ်နေသည့်အပိုင်းများကို ဖြတ်တောက်ပြီးပြသခြင်း တို့လုပ်ဆောင်နိုင်ပါသည်။

* **Geometry generator** (:ref:`geometry_generator_symbol` တွင်ဖော်ပြထားပါသည်။)
* **Gradient fill** - ရိုးရှင်းသော နှစ်ရောင်ပါ gradient များ သို့မဟုတ် ကြိုတင်သတ်မှတ်ပေးထားသော :ref:`gradient color ramp <color-ramp>` ပေါ်အခြေခံ၍  polygon ကို ဖြည့်ရန် အလယ်မှ ဖြာထွက်သည့်ပုံစံ (radial)၊ အဖြောင့် ဖြာထွက်သည့်ပုံစံ (linear) သို့မဟုတ် ထုချွန် ဖြာထွက်သည့်ပုံစံ (conical) gradient များ အသုံးပြုနိုင်ပါသည်။ အရောင်ပြေး Gradient ကို feature တစ်ခုချင်း အတွက် သို့မဟုတ် မြေပုံ တစ်ခုလုံးအတွက် လှည့်နိုင်သည်။ အစနှင့် အဆုံး မှတ်များကိုလည်း coordinates သို့မဟုတ် (feature သို့မဟုတ် map ၏) centroid များ အသုံးပြု၍ သတ်မှတ်နိုင်သည်။ အရွေ့ကို data ဖြင့်လည်းသတ်မှတ်ပေးနိုင်သည် (data-defined offset)။
* **Line pattern fill** - Polygon ကို :ref:`line symbol layer <vector_line_symbols>` ၏ hatching pattern တစ်ခုဖြင့် ဖြည့်နိုင်ပါသည်။ အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်-

  * :guilabel:`Alignment (ညီညာတန်းနေမှု)` - Feature (များ)နှင့် ယှဉ်၍ pattern ကို မည်သို့ နေရာချထားမည်ကို သတ်မှတ်ပါသည်။

    * :guilabel:`Align pattern to feature` - Line များကို feature တစ်ခုချင်းစီတွင် ဖော်ပြပါသည်။
    * :guilabel:`Align pattern to map extent` - Feature များတလျှောက် line များကို ကောင်းမွန်စွာ align (ညီညာအောင်ပြုလုပ်) လုပ်ပေးပြီး pattern တစ်ခုကို map extent တစ်ခုလုံးတွင် ဖော်ပြပါသည်။
  * Line များကို နာရီလက်တံပြောင်းပြန် (လက်ဝဲရစ်) အတိုင်း :guilabel:`Rotation` လှည့်ခြင်း
  * :guilabel:`Spacing` - တစ်ဆက်တည်းဖြစ်နေသည့် line များအကြား အကွာအဝေး
  * :guilabel:`Offset` - Line များကို feature နယ်နိမိတ်မှ ခွာထားလိုသည့် အကွာအဝေး
  * :guilabel:`Clipping` - ဖြည့်ချယ် (fill) ထားသော polygon ၏ ပုံသဏ္ဍာန် ဖြင့် line များကို မည်သို့ ဖြတ်တောက် (clip) ပြရမည်ကို သတ်မှတ်ပေးနိုင်သည်။ ရွေးချယ်ခွင့် (Option) များမှာ-

    * :guilabel:`Clip During Render Only` - Line များကို feature ၏ အကျယ်အဝန်းစတုဂံ တစ်ခုလုံးအပြည့် ဦးစွာဖန်တီးပြီး ပုံဖော်ပြသချိန် (drawing) တွင်မှ ဖြတ်တောက် (clip)ပြီးပြသစေသည်။ Line အစွန်းများ (အစနှင့် အဆုံး) ကို မြင်ရမည်မဟုတ်ပါ။
    * :guilabel:`Clip Lines Before Render` - Line များကို polygon ဖြင့် အတိအကျ အရင်ဖြတ် တောက် (clip) ပြီး မှ ပုံဖော်ပြသစေသည်။ Line အစွန်းများ (ထိပ်ဖုံး style များ၊ အစ/အဆုံး marker line object များ၊ စသည်တို့ ...) ကိုမြင်နိုင်ပြီး တစ်ခါတစ်ရံ polygon ၏ အပြင်ဘက်သို့ ကျော်ထွက်နေခြင်းများလည်း ဖြစ်နိုင်ပါသည်။ (line သင်္ကေတ setting ပေါ်မူတည်ပါသည်)
    * :guilabel:`No Clipping` - ဖြတ်တောက်ခြင်း (clip) လုံးဝ မပြုလုပ်ပေးပါ။ Line များသည် feature ၏ အကျယ်အဝန်းစတုဂံတစ်ခုလုံးကို ဖြည့်ပြီး ပြသနေပါလိမ့်မည်။

* **Point pattern fill** - Polygon ကို :ref:`marker symbol <vector_marker_symbols>` များဖြင့် grid pattern (အကွက်ပုံစံ) ဖြည့်ပါသည်။ အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်-

  * :guilabel:`Alignment (ညီညာတန်းနေမှု)` - Feature (များ)နှင့် ယှဉ်၍ pattern များကို မည်သို့ နေရာချထားမည်ကို သတ်မှတ်ပါသည်။

    * :guilabel:`Align pattern to feature` - Marker line များကို feature တစ်ခုချင်းစီတွင် နေရာချပါသည်။
    * :guilabel:`Align pattern to map extent` - Features များတစ်လျှောက် line များကို ကောင်းမွန်စွာ align လုပ်ပေးပြီး pattern တစ်ခုကို map extent တစ်ခုလုံးတွင် နေရာချပါသည်။

      .. _figure_point_pattern_alignment:

      .. figure:: img/pointPatternAlignment.png
         :align: center

         Feature တွင် point pattern align ပြုလုပ်ခြင်း (ဘယ်ဘက်) နှင့် map extent တွင် point pattern align ပြုလုပ်ခြင်း (ညာဘက်)

  * :guilabel:`Distance` (အကွာအဝေး) - တဆက်တည်းဖြစ်နေသည့် marker များအကြား :guilabel:`Horizontal` (ဘေးတိုက်) နှင့် :guilabel:`Vertical` (အထက်အောက်) အကွာအဝေးများ
  * :guilabel:`Displacement` (အရွေ့) - Column တစ်ခုအတွင်းရှိ တဆက်တည်းဖြစ်နေသည့် marker များအကြား (resp. row တစ်ခုအတွင်း) alignment ၏ :guilabel:`Horizontal` (resp. :guilabel:`Vertical`) offset တစ်ခု
  * :guilabel:`Offset` - Feature နယ်နိမိတ်မှ :guilabel:`Horizontal` နှင့် :guilabel:`Vertical` အကွာအဝေးများ
  * :guilabel:`Clipping` - Fill ထားသည့် marker များကို polygon shape ဖြစ်အောင် ဖြတ်တောက်ခြင်းကို ထိန်းချုပ်နိုင်စေပါသည်။ ရွေးချယ်ခွင့် (Option) များမှာ-

    * :guilabel:`Clip to shape` (Shape အတိုင်းဖြတ်တောက်ခြင်း) - Marker များကို ဖြတ်တောက်ထားသောကြောင့် polygon အတွင်းရှိ အပိုင်းကိုသာ မြင်တွေ့ရမည်ဖြစ်ပါသည်။
    * :guilabel:`Marker centroid within shape` (Shape အတွင်း marker ၏ centroid) - Marker ၏ centroid သည် Polygon အတွင်းပိုင်းသို့ ကျရောက်နေသည်များကိုသာ ရေးဆွဲမည်ဖြစ်ပြီး polygon အပြင်ဘက်ရှိ marker များကို ဖြတ်တောက်ပြသမည်မဟုတ်ပါ။
    * :guilabel:`Marker completely within shape` (Shape အတွင်း အပြည့်အဝကျရောက်နေသည့် marker) - Polygon အတွင်းသို့ အပြည့်အဝ ကျရောက်နေသည့် marker များကိုသာ ပြသမည်ဖြစ်ပါသည်။ 
    * :guilabel:`No clipping` (ဖြတ်တောက်မှုမရှိခြင်း) - Polygon နှင့် ထိစပ်နေသည့် မည်သည့် marker မဆို ဖော်ပြမည်ဖြစ်ပါသည်။ (တိတိကျကျဆိုလျှင် marker ၏ အကျယ်အဝန်းစတုဂံ နှင့် ထိဖြတ်နေခြင်းဖြစ်သည်)

      .. _figure_clip_point_pattern_fill:

      .. figure:: img/clipPointPatternFill.png
         :align: center

         ဖြည့်ထားသည့် marker များအား clipping ပြုလုပ်ခြင်း - ဝဲဘက် မှ ယာဘက်သို့ : Clip to shape ၊ Marker centroid within shape ၊ Marker completely within shape ၊ No clipping

  * Pattern တစ်ခုလုံးကို နာရီလက်တံအတိုင်း :guilabel:`Rotation` လှည့်ခြင်း
  * :guilabel:`Randomize pattern` (ကျပန်းပုံစံ) group setting သည် point pattern fill အတွင်းရှိ point တစ်ခုချင်းစီကို သတ်မှတ်ထားသည့် အများဆုံးအကွာအဝေးထိ :guilabel:`Horizontally` (ဘယ်ညာ) သို့မဟုတ် :guilabel:`Vertically` (အထက်အောက်) ကျပန်း ‌‌‌‌ရွေ့လျားခွင့်ပြုပါသည်။ အမြင့်ဆုံး offset ကို မီလီမီတာ၊ ပွိုင့်၊ မြေပုံ၏ယူနစ် သို့မဟုတ် "ရာခိုင်နှုန်း" (ဤနေရာတွင် ရာခိုင်နှုန်း သည် parttern အကျယ် သို့မဟုတ် အမြင့်တို့ဖြင့် နှိုင်းရ ရာခိုင်နှုန်းဖြစ်သည်) ကဲ့သို့ အသုံးပြုနိုင်သည့် မည်သည့်ယူနစ်များဖြင့်မဆို သတ်မှတ်နိုင်ပါသည်။

    Map refresh များပြုလုပ်သောအခါ သင်္ကေတ pattern များ နေရာပြောင်းခြင်း ("jumping") ဖြစ်ခြင်းမှ ရှောင်ရှားရန် ကျပန်းအစပျိုးတန်ဖိုး (random number seed) ကို သတ်မှတ်နိုင်သည်။ Data ဖြင့် အစားထိုး override လုပ်ခြင်းကိုလည်း ဆောင်ရွက်နိုင်ပါသည်။

    .. note::  :guilabel:`Randomize pattern` နှင့် :ref:`random marker fill <random_marker_fill>`  သင်္ကေတ အမျိုးအစားများအကြား အဓိကကွာခြားချက်မှာ marker များ quasi-"regular" နေရာချထားမှုအတွက် point pattern တစ်ခုဖြင့် ကျပန်းအရွေ့ (random offset) ကို သုံးနိုင်ခြင်းဖြစ်သည်။ အဘယ်ကြောင့်ဆိုသော် pattern ၏အစိတ်အပိုင်း ဖြစ်သည့် point များကို grid တစ်ခုဖြင့် ကန့်သတ်ထားသောကြောင့်ဖြစ်သည်။ ၄င်းသည် နေရာလွတ်များ သို့မဟုတ် ထပ်နေသည့် marker များမရှိသော ကျပန်းမကျတကျဖြည့်မှု (semi-random fill) များကို ဖန်တီးနိုင်ပါသည်။ (၎င်းနှင့် ဆန့်ကျင်ဘက်ဖြစ်နေသည့် random marker fill တွင် point များကို လုံးဝ ကျပန်း နေရာချခြင်းဖြစ်ရာ တစ်ခါတစ်ရံ point များသည် အမြင်အားဖြင့် ဟိုတစ်စု ဒီတစ်စု ဖြစ်နေခြင်း သို့မဟုတ် မလိုလားအပ်သည့် နေရာလွတ်များကို ဖြစ်ပေါ်စေသည်)

.. _random_marker_fill:

* **Random marker fill** သည် Polygon နယ်နိမိတ်အတွင်း ကျပန်းနေရာများ၌ :ref:`marker symbol 
  <vector_marker_symbols>` ဖြင့် polygon ကို ဖြည့်ပါသည်။ အောက်ပါတို့ကို သတ်မှတ်နိုင်ပါသည်-

  * :guilabel:`Count method` (ရေတွက်ခြင်းနည်း) - ဖြည့်မည့် marker သင်္ကေတ အရေအတွက်ကို အရေအတွက်အတိအကျ သို့မဟုတ် သိပ်သည်းဆ ဖြင့် သတ်မှတ်နိုင်သည်။
  * :guilabel:`Point count` (Point အရေအတွက်) - ဖြည့်မည့် marker သင်္ကေတ အရေအတွက်ကို သတ်မှတ်နိုင်သည်။
  * တသမတ်တည်းနေရာချထားပေးရန်အတွက် :guilabel:`seed` (ကျပန်းအစပျိုးတန်ဖိုး) ကိုသတ်မှတ်ပေးနိုင်သည်။
  * :guilabel:`Density area` (သိပ်သည်းမှုဧရိယာ) - သိပ်သည်းမှုအခြေပြု အရေအတွက် နည်းလမ်း (density-based count method) ကိုသုံးထားသည့်အခါတွင် scale / zoom levels အမျိုးမျိုးတွင် ဖော်ပြမည့် သင်္ကေတများ၏သိပ်သည်းမှု (fill density) အနေအထားကို မြေပုံကို refresh ပြန် လုပ်သည့်အခါတိုင်းတွင် တူနေစေရန်ပြုလုပ်ပေးသည် (Tile-based နှင့် QGIS server တွင်လည်း ကျပန်းနေရာချထားမှု ကိုကောင်းမွန်စေသည်)
  * :guilabel:`Clip markers to polygon boundary` (Polygon နယ်နိမိတ်အတိုင်း marker များဖြတ်တောက်ခြင်း) - Polygon အနားစွန်းအနီးရှိ marker များကို polygon နယ်နိမိတ်အတိုင်း ဖြတ်တောက် (clip) စေလိုပါက ဆောင်ရွက်နိုင်ပါသည်။

* **Raster image fill** - Polygon ကို raster image (:file:`PNG` ၊ :file:`JPG` ၊ :file:`BMP` ...) မှ tile များဖြင့် ဖြည့်ပါသည်။ Image သည် disk ပေါ်တွင် ဖိုင် တစ်ခုအဖြစ် လည်းကောင်း၊ အခြား တစ်နေရာကို ညွှန်းသည့် remote URL တစ်ခုအဖြစ် လည်းကောင်း၊ file တစ်ခုလုံးကို string အဖြစ် ထည့်သွင်း (embeded) သိမ်းဆည်းခြင်း (encoded) ပြုလုပ်နိုင်သည်။ (:ref:`အသေးစိတ်ကြည့်ရှုရန် <embedded_file_selector>`) ရွေးချယ်စရာများမှာ (data သတ်မှတ်သည့်) opacity (အလင်းပိတ်နှုန်း) ၊ image အကျယ်၊ coordinate mode (object သို့မဟုတ် viewport)၊ rotation (အလှည့်ထောင့်) နှင့် offset (အရွေ့) တို့ဖြစ်ပါသည်။ Image အကျယ်ကို :ref:`common units (အသုံးများသည့်ယူနစ်များ) <unit_selector>` တစ်မျိုးမျိုးဖြင့် သတ်မှတ်ပေးနိုင်သည် သို့မဟုတ် မူလအရွယ်အစား၏ရာခိုင်နှုန်း ဖြင့်လည်းထားနိုင်ပါသည်။
* **SVG fill** - Polygon ကို :ref:`SVG markers <svg_marker>` ဖြင့် ပေးထားသော အရွယ်အစား (:guilabel:`Texture width`) ဖြင့် ဖြည့်ပါသည်။ 
* **Shapeburst fill** - Gradient fill ကို buffer လုပ်ပြီးပြသပါသည်။ ဤနေရာတွင် gradient ကို 
  polygon ၏နယ်နိမိတ်မှ polygon ၏ ဗဟိုဆီသို့ ရေးဆွဲပါသည်။ ပြင်ဆင်နိင်သော parameter များတွင် အရောင်အစနှင့် နယ်နိမိတ်ကြား အကွာအဝေး၊ အရောင်စဉ် ramp များ၊ သို့မဟုတ် အရောင် နှစ်မျိုး ပါ ရိုးရိုး gradientများ ၊  fill ကိုမှုန်းဝါးစေခြင်း နှင့် နေရာရွေ့ပြစေမည့် offset တို့ပါဝင်ပါသည်။
* **Outline: Arrow** - Polygon နယ်နိမိတ်ကို ပြသရန် line :ref:`arrow symbol <arrow_symbol>` layer တစ်ခုကို အသုံးပြုပါသည်။ Outline arrow အတွက် setting များသည် arrow line သင်္ကေတများ၏ setting များနှင့် အတူတူပင်ဖြစ်ပါသည်။
* **Outline: Hashed line** - Polygon နယ်နိမိတ် (:guilabel:`Rings`) ကို ပြသရန် :ref:`hash line symbol <hashed_line_symbol>` layer ကိုအသုံးပြုပါသည်။ ၄င်းသည် အတွင်းရှိအပေါက်များ (interior ring) သီးသန့် သို့မဟုတ် အပြင်အနား (exterior ring) သီးသန့် သို့မဟုတ် နှစ်မျိုးစလုံးတွင် ဖော်ပြနိုင်သည်။ Outline hashed line အတွက် အခြားသော setting များသည် hashed line သင်္ကေတများ၏ setting များနှင့် အတူတူပင်ဖြစ်ပါသည်။
* **Outline: Marker line** - Polygon နယ်နိမိတ် (:guilabel:`Rings`) ကို ပြသရန် :ref:`marker line symbol <marker_line_symbol>` layer ကိုအသုံးပြုပါသည်။ ၄င်းသည် အတွင်းရှိအပေါက်များ (interior ring) သီးသန့် သို့မဟုတ် အပြင်အနား (exterior ring) သီးသန့် သို့မဟုတ် နှစ်မျိုးစလုံးတွင် ဖော်ပြနိုင်သည်။ Outline marker line အတွက် အခြားသော setting များသည် marker line သင်္ကေတ များ၏ setting များနှင့် အတူတူပင်ဖြစ်ပါသည်။
* **Outline: simple line** - Polygon နယ်နိမိတ် (:guilabel:`Rings`) ကို ပြသရန် :ref:`simple line symbol <simple_line_symbol>` layer ကိုအသုံးပြုပါသည်။ ၄င်းသည် အတွင်းရှိအပေါက်များ (interior ring) သီးသန့် သို့မဟုတ် အပြင်အနား (exterior ring) သီးသန့် သို့မဟုတ် နှစ်မျိုးစလုံး တွင် ဖော်ပြနိုင်သည်။ :guilabel:`Draw line only inside polygon` option သည်  border လိုင်းကို polygon အတွင်းဖက်တွင် ဖော်ပြသည့်အတွက် ကပ်လျှက်ရှိနေသည့် polygon နယ်နိမိတ်များကို ရှင်းလင်းစွာဖော်ပြရာတွင် အသုံးဝင်ပါသည်။ Outline simple line အတွက် အခြားသော setting များသည် simple line သင်္ကေတများ၏ setting နှင့် အတူတူပင်ဖြစ်ပါသည်။
  
.. note::

 ဂျီဩမေတြီ အမျိုးအစားသည် polygon ဖြစ်နေလျှင် line/polygon များကို canvas extent ဖြင့် အလိုအလျှောက် ဖြတ်တောက် (clip) ခြင်းကို disable (ပိတ်ထား) လုပ်ထားရန် ရွေးချယ်နိုင်ပါသည်။ တချို့သောကိစ္စရပ်များတွင် clip ပြုလုပ်ခြင်းသည် အဆင်မပြေသည့် symbology (သင်္ကေတဖော်ပြမှု) ကို ဖြစ်စေပါသည်။ (ဥပမာ - centroid fill ပြုလုပ်ရာတွင် centroid သည် feature ၏ အမှန်တကယ် centroid ဖြစ်ရပါမည်။) 

.. _svg_symbol:

Parametrizable SVG (ချိန်ညှိနိုင်သည့် SVG)
...........................................

:guilabel:`SVG marker` ၏ အရောင်ကို ပြောင်းလဲနိုင်ပါသည်။ အ‌ရောင်ဖြည့်အတွက်  ``param(fill)`` ၊ လိုင်းအရောင်အတွက် ``param(outline)`` နှင့် လိုင်းအထူအတွက်  ``param(outline)`` စသည့် placeholder များကို ထည့်ပေးထားခြင်းဖြင့် လုပ်ဆောင်နိုင်ပါသည်။ Placeholder များကို default တန်ဖိုးဖြင့်လည်းသတ်မှတ်နိုင်ပါသည်။ ဥပမာ-

.. code-block:: xml

    <svg width="100%" height="100%">
    <rect fill="param(fill) #ff0000" stroke="param(outline) #00ff00" stroke-width="param(outline-width) 10" width="100" height="100">
    </rect>
    </svg>

ယေဘုယျအားဖြင့် SVG များကို ``param(param_name)`` ကိုအသုံးပြု၍ လွတ်လပ်စွာ ချိန်ညှိပေးနိုင်ပါသည်။ ထို param ကို attribute တန်ဖိုးတစ်ခု သို့မဟုတ် node စာသားတစ်ခုအနေဖြင့် အသုံးပြုနိုင်ပါသည်-

.. code-block:: xml

    <g stroke-width=".265" text-anchor="middle" alignment-baseline="param(align)">
      <text x="98" y="147.5" font-size="6px">param(text1)</text>
      <text x="98" y="156.3" font-size="4.5px">param(text2)</text>
    </g>

Parameter များကို :guilabel:`Dynamic SVG parameters` ဇယားတွင် expression များအဖြစ် သတ်မှတ်နိုင်သည်။

.. figure:: img/svg_parameters.png
   :align: center

   Dynamic SVG parameters table (တပြိုင်နက်တည်းပြောင်းလဲနိုင်သည့် SVG parameter များ ဇယား) 


.. _geometry_generator_symbol: 
 
The Geometry Generator (ဂျီဩမေတြီ အရာဝတ္တုဖန်တီးသည့်အရာ)
.........................................................

သင်္ကေတ အမျိုးအစားအားလုံးတွင် အသုံးပြုနိုင်ပါသည်။ :guilabel:`geometry generator` သင်္ကေတ layer သည် ပုံဖော်သည့် (rendering) လုပ်ငန်း ဆောင်ရွက်နေစဥ်အတွင်း geometery တစ်ခုကို တချိန်တည်းမှာ (on the fly) generate လုပ်ဆောင်နိုင်ရန် :ref:`expression syntax <functions_list>` ကို အသုံးပြုနိုင်ပါသည်။ ရရှိလာသော ဂျီဩမေတြီ သည် မူလ :guilabel:`Geometry type` နှင့် အမျိုးအစားတူရန်မလိုအပ်ပါ။ ထို့အပြင် အမျိုးမျိုးကွဲပြားစွာပြုလုပ်ထားသော သင်္ကေတ layer များစွာကို တစ်ခုနှင့်တစ်ခုအပေါ်တွင် ထပ်မံထည့်သွင်းနိုင်ပါသည်။

Layer တစ်ခု ကို ဂျီဩမေတြီ generator သင်္ကေတ မသက်ရောက်‌သည့်အခါ :guilabel:`Units` (ယူနစ်) property ကို သတ်မှတ်နိုင်ပါသည်။ (ဥပမာ - ၄င်းကို layout item တစ်ခုပေါ်တွင် အသုံးပြုသည့်အခါ) ၄င်းသည် ထွက်ရှိလာသော output ကို ပိုမို၍ ထိန်းချုပ်နိုင်ပါသည်။

အချို့သော ဥပမာများမှာ-

::

  -- render the centroid of a feature
  centroid( $geometry ) 

  -- visually overlap features within a 100 map units distance from a point
  -- feature, i.e generate a 100m buffer around the point
  buffer( $geometry, 100 )

  -- Given polygon layer1( id1, layer2_id, ...) and layer2( id2, fieldn...)
  -- render layer1 with a line joining centroids of both where layer2_id = id2
  make_line( centroid( $geometry ),
             centroid( geometry( get_feature( 'layer2', 'id2', attribute(
                 $currentfeature, 'layer2_id') ) )
           ) 

  -- Create a nice radial effect of points surrounding the central feature
  -- point when used as a MultiPoint geometry generator
  collect_geometries(
    array_foreach(
      generate_series( 0, 330, 30 ),
        project( $geometry, .2, radians( @element ) )
    )
  )


.. _vector_field_marker:

The Vector Field Marker (Vector Field အမှတ်အသား)
.................................................

Vector field marker ကို vector field data ဥပမာ- earth deformation (ကမ္ဘာမြေပုံစံပျက်ယွင်းမှု) ၊ tidal flow (ဒီရေစီးကြောင်း) များနှင့် အလားတူအရာများကိုဖော်ပြရန် အသုံးပြုပါသည်။ ၄င်းသည် line (မြားဖြင့် ပြလျှင် ပိုကောင်းသည်) များအဖြစ်ဖော်ပြသည့်အခါ ‌ရွေးချယ်ထားသော data point များ၏ attribute များပေါ်မူတည်၍ လိုင်းအရွယ်အစားကို စကေးပြုလုပ် (scaled) ပြီး လားရာအတိုင်း ဦးတည်ဖန်တီးပေးပါသည်။ ၄င်းကို point data များကို ပုံဖော်ပြသ (render) သည့်အခါတွင်သာ အသုံးပြုနိုင်ပြီး line နှင့် polygon များကို ဤသင်္ကေတဖြင့် ရေးဆွဲ၍ မရပါ။

Vector field ကို data ရှိ attribute ဖြင့် သတ်မှတ်ပါသည်။ ၄င်းသည် အောက်ဖော်ပြပါ ပုံစံတစ်ခုခုဖြင့် field ကို ဖော်ပြနိုင်ပါသည်- 

* **cartesian** စနစ် ( field ၏ ``x`` နှင့် ``y`` အစိတ်အပိုင်းများ)
* သို့မဟုတ် **polar** (ဝင်ရိုးစွန်း) coordinates စနစ် - ဤအခြေအနေတွင် attribute များသည် ``Length`` (အလျား) နှင့် ``Angle`` (ထောင့်) ကို သတ်မှတ်သည်။ Angle ကို မြောက်အရပ်မှစပြီး  နာရီလက်တံ (လက်ယာရစ်) အတိုင်း တိုင်းတာနိုင်ပြီး အရှေ့အရပ်မှစပြီး နာရီလက်တံပြောင်းပြန် (လက်ဝဲရစ်) အတိုင်း တိုင်းတာနိုင်ပါသည်။ ထောင့် ယူနစ်သည် Degrees (ဒီဂရီ) သို့မဟုတ် radian အနေဖြင့်ဖြစ်နိုင်ပါသည်။
* သို့မဟုတ် **height only (အမြင့်တန်ဖိုးတစ်ခုတည်းသာ)** data အနေဖြင့် - ၄င်းသည် data ၏ attribute တစ်ခုကို အသုံးပြု၍ စကေးကိုက် ဒေါင်လိုက်မြှား (vertical arrow) ကို ပြသပါသည်။ ဥပမာအားဖြင့် ၄င်းသည် ပုံပျက်ယွင်းမှု (deformation) ၏ ဒေါင်လိုက် (vertical) အစိတ်အပိုင်းများကို ပြသရာတွင် သင့်လျော်ပါသည်။

အဆင်ဆင်ပြေပြေ မြင်ရသည့် သင့်လျော်သောအရွယ်အစား ရရှိအောင် field ၏ တန်ဖိုးကိန်းဂဏန်းကို စကေး အတိုးအလျှော့ ပြုလုပ်နိုင်ပါသည်။ 


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |duplicateLayer| image:: /static/common/mActionDuplicateLayer.png
   :width: 1.5em
.. |iconView| image:: /static/common/mActionIconView.png
   :width: 1.5em
.. |locked| image:: /static/common/locked.png
   :width: 1.5em
.. |lockedGray| image:: /static/common/lockedGray.png
   :width: 1.2em
.. |openTable| image:: /static/common/mActionOpenTable.png
   :width: 1.5em
.. |paintEffects| image:: /static/common/mIconPaintEffects.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |styleManager| image:: /static/common/mActionStyleManager.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
