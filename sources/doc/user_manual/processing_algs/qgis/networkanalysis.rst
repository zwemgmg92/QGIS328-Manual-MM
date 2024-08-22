Network analysis (လမ်းကြောင်းကွန်ယက်ဆိုင်ရာ ဆန်းစစ်လေ့လာခြင်း)
===============================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisserviceareafromlayer:

Service area (from layer)  (လုပ်ဆောင်မှု ဧရိယာ (layer မှ))
-----------------------------------------------------------

Point layer တစ်ခုမှ စတင်ပြီး အကွာအဝေးတစ်ခု သို့မဟုတ် အချိန်တစ်ခုအတွင်းတွင် ရောက်ရှိနိုင်သော network (လမ်းကြောင်းကွန်ယက်) တစ်ခု၏ edge များအားလုံး သို့မဟုတ် edge များ၏အစိတ်အပိုင်းများကို ပြန်ထုတ်ပေးပါသည်။ ၎င်းသည် network (လမ်းကြောင်းကွန်ယက်) တစ်ခုအတွင်း သွားလာနိုင်မှုကို အကဲဖြတ်ပေးပါသည်၊ ဥပမာ- တန်ဖိုးတစ်ခု (တန်ဖိုးသည် အကွာအဝေး သို့မဟုတ် အချိန်) ထက်မပိုပဲ လမ်းကွန်ယက်တစ်ခုပေါ်တွင် လမ်းညွှန်သွားလာနိုင်သော နေရာများသည် မည်သည့်နေရာများဖြစ်သလဲ။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector layer representing network** (**Network ကိုကိုယ်စားပြုသော vector layer**)
     - ``INPUT``
     - [vector: line]
     - လွှမ်းခြုံရမည့် network ကိုကိုယ်စားပြုသော line vector layer
   * - **Vector layer with start points** (**အစမှတ်များဖြင့် vector layer**)
     - ``START_POINTS``
     - [vector: point]
     - လုပ်ဆောင်မှုဧရိယာများကို ဖန်တီးရန်အတွက် အစမှတ်များအဖြစ် အသုံးပြုသော feature များ၏ point vector layer
   * - **Path type to calculate** (**တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား**)
     - ``STRATEGY``
     - [enumeration]

       Default: 0
     - တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Shortest (အတိုဆုံး)
       * 1 --- Fastest (အမြန်ဆုံး)
   * - **Travel cost (distance for "Shortest", time for "Fastest")** (**ခရီးသွားကုန်ကျစရိတ် ("အတိုဆုံး" အတွက် အကွာအဝေး၊ "အမြန်ဆုံး" အတွက် အချိန်)**)
     - ``TRAVEL_COST``
     - [number]

       Default: 0
     - *အတိုဆုံး* လမ်းကြောင်းနှင့် *အမြန်ဆုံး* လမ်းကြောင်းအတွက်အချိန် (နာရီဖြင့်) ကိုရှာဖွေသောအခါ အကွာအဝေး (network layer ယူနစ်ဖြင့်) အဖြစ် တန်ဖိုးကိုခန့်မှန်းပါသည်။
   * - **Service area (lines)** (**လုပ်ဆောင်မှုဧရိယာ (line များ)**)
     - ``OUTPUT_LINES``
     - [vector: line]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - လုပ်ဆောင်မှုဧရိယာ အတွက် output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Service area (boundary nodes)** (**လုပ်ဆောင်မှုဧရိယာ (နယ်နိမိတ် ဆုံချက်များ)**)
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Skip output]``
     - လုပ်ဆောင်မှုဧရိယာ နယ်နိမိတ် ဆုံချက်များအတွက် output point layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. **network_advanced_parameters**

.. This section is included in the network analysis algorithms
  qgisserviceareafrompoint, qgisserviceareafromlayer,
  qgisshortestpathlayertopoint, qgisshortestpathpointtolayer, qgisshortestpathpointtopoint
  
.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Direction field** (**ဦးတည်ရာ field**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DIRECTION_FIELD``
     - [tablefield: string]

       Default: 0.0
     - Network edge များအတွက် ဉီးတည်ရာများကို သတ်မှတ်ရန် အသုံးပြုသော field ။ ၎င်း field ထဲတွင်အသုံးပြုသော တန်ဖိုးများကို parameter သုံးမျိုး (``Value for forward direction (ရှေ့ဘက်ဦးတည်ရာအတွက် တန်ဖိုး)`` ၊ ``Value for backward direction (နောက်ဘက်ဦးတည်ရာအတွက် တန်ဖိုး)`` နှင့် ``Value for both directions (ဦးတည်ရာနှစ်ဖက်လုံးအတွက် တန်ဖိုး)``) ဖြင့် သတ်မှတ်ပါသည်။ ရှေ့ဘက်နှင့် နောက်ဘက် ဦးတည်ရာများသည် တစ်ဖက်တည်းသွားသော edge နှင့် သက်ဆိုင်ပြီး "ဦးတည်ရာနှစ်ခုလုံး" သည် နှစ်ဖက်သွား edge ဖြစ်ပါသည်။ Feature တစ်ခုသည် ၎င်း field ထဲတွင် တန်ဖိုးတစ်ခုမှ မရှိလျှင် သို့မဟုတ် မည်သည့် column ကိုမှသတ်မှတ်မထားလျှင် မူရင်းဦးတည်ရာ (``Default direction (မူရင်းဦးတည်ရာ)`` parameter ကိုပေးထားပါသည်) setting ကိုအသုံးပြုပါသည်။
   * - **Value for forward direction** (**ရှေ့ဘက်ဦးတည်ရာအတွက် တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``VALUE_FORWARD``
     - [string]

       Default: ''
     - ရှေ့ဘက်သို့သွားသော ဦးတည်ရာတစ်ခုအသုံးပြုပြီး edge များကိုဖော်ထုတ်ရန် ဦးတည်ရာ field ထဲတွင်သတ်မှတ်ထားသော တန်ဖိုး
   * - **Value for backward direction** (**နောက်ဘက် ဦးတည်ရာအတွက် တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``VALUE_BACKWARD``
     - [string]

       Default: ''
     - နောက်ဘက်သို့သွားသော ဦးတည်ရာတစ်ခုအသုံးပြုပြီး edge များကိုဖော်ထုတ်ရန် ဦးတည်ရာ field ထဲတွင်သတ်မှတ်ထားသော တန်ဖိုး
   * - **Value for both directions** (**ဦးတည်ရာနှစ်ခုလုံး အတွက် တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``VALUE_BOTH``
     - [string]

       Default: ''
     - ဦးတည်ရာနှစ်ဖက်လုံး edge များကို ဖော်ထုတ်ရန် ဦးတည်ရာ field ထဲတွင်သတ်မှတ်ထားသော တန်ဖိုး
   * - **Default direction** (**မူရင်း ဦးတည်ရာ**)
     - ``DEFAULT_DIRECTION``
     - [enumeration]

       Default: 2
     - Feature တစ်ခု၏ ဦးတည်ရာ field ထဲတွင် မည်သည့်တန်ဖိုးကိုမျှ သတ်မှတ်မထားလျှင် သို့မဟုတ် ဦးတည်ရာ field ကိုသတ်မှတ်မထားလျှင် ဤမူရင်းဦးတည်ရာတန်ဖိုးကို အသုံးပြုပါမည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Forward direction (ရှေ့ဘက် ဦးတည်ရာ)
       * 1 --- Backward direction (နောက်ဘက် ဦးတည်ရာ)
       * 2 --- Both directions (ဦးတည်ရာနှစ်ခုလုံး)
   * - **Speed field** (**အမြန်နှုန်း field**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SPEED_FIELD``
     - [tablefield: string]

     - အမြန်ဆုံးလမ်းကြောင်းကို ရှာဖွေသောအခါ network ၏ edge များအတွက် အမြန်နှုန်းတန်ဖိုး (``km/h`` ဖြင့်) ကိုပေးထားသော field။  Feature တစ်ခုသည် ဤ field ထဲတွင် တန်ဖိုးတစ်ခု မရှိလျှင် သို့မဟုတ် မည်သည့် column မှ သတ်မှတ်မထားလျှင် မူရင်းအမြန်နှုန်းတန်ဖိုး (``Default speed (မူရင်းအမြန်နှုန်း)`` parameter ကို ပေးထားပါသည်) ကိုအသုံးပြုပါသည်။
   * - **Default speed (km/h)** (**မူရင်းအမြန်နှုန်း (km/h)**)
     - ``DEFAULT_SPEED``
     - [number]

       Default: 50.0
     - Edge တစ်ခုအတွက် အမြန်နှုန်း field ကိုပေးမထားလျှင် ခရီးသွားကြာချိန်ကို တွက်ချက်ရန်အတွက် အသုံးပြုသောတန်ဖိုး
   * - **Topology tolerance** (**ဆက်စပ်တည်ရှိမှုအရဖွဲ့စည်းပုံဆိုင်ရာ လက်ခံနိုင်စွမ်း**)
     - ``TOLERANCE``
     - [number]

       Default: 0.0
     - သတ်မှတ်ထားသော လက်ခံနိုင်စွမ်းထက် ပိုနီးသော ဆုံချက် (node) များဖြင့် line နှစ်ခုကို ချိတ်ဆက်ထားသည်ဟု ယူဆပါသည်။

.. **end_network_advanced_parameters**

.. list-table::
   :widths: 20 20 20 40

   * - **Include upper/lower bound points** (**အပေါ်ဘက်/အောက်ဘက် ကန့်သတ် point များထည့်သွင်းခြင်း**)
     - ``INCLUDE_BOUNDS``
     - [boolean]

       Default: False
     - လုပ်ဆောင်မှုဧရိယာ၏ နယ်နိမိတ်ပေါ်ရှိ edge တစ်ခုချင်းစီအတွက် point နှစ်ခုပါဝင်သော point layer output တစ်ခုကိုဖန်တီးပေးပါသည်။ Point တစ်ခုသည် ၎င်း edge ၏ အစဖြစ်ပြီး အခြား point သည် အဆုံးသတ် ဖြစ်ပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Service area (boundary nodes)** (**လုပ်ဆောင်မှုဧရိယာ (နယ်နိမိတ် ဆုံချက်များ)**)
     - ``OUTPUT``
     - [vector: point]
     - လုပ်ဆောင်မှုဧရိယာ နယ်နိမိတ် ဆုံချက်များပါဝင်သော output point layer
   * - **Service area (lines)** (**လုပ်ဆောင်မှုဧရိယာ (line များ)**)
     - ``OUTPUT_LINES``
     - [vector: line]
     - သတ်မှတ် အကွာအဝေး သို့မဟုတ် အချိန်အတွက် အစမှတ်များမှ သွားလာနိုင်သော network ၏ အစိတ်အပိုင်းများကို ကိုယ်စားပြုသော line layer။

Python code
............

**Algorithm ID**: ``qgis:serviceareafromlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisserviceareafrompoint:

Service area (from point) (လုပ်ဆောင်မှု ဧရိယာ (point မှ))
----------------------------------------------------------

တစ်ခုမှ စတင်ပြီး အကွာအဝေးတစ်ခု သို့မဟုတ် အချိန်တစ်ခုအတွင်းတွင် ရောက်ရှိနိုင်သော network (လမ်းကြောင်းကွန်ယက်) တစ်ခု၏ edge များအားလုံး သို့မဟုတ် edge များ၏အစိတ်အပိုင်းများကို ပြန်ထုတ်ပေးပါသည်။ ၎င်းသည် network (လမ်းကြောင်းကွန်ယက်) တစ်ခုအတွင်း သွားလာနိုင်မှုကို အကဲဖြတ်ပေးပါသည်၊ ဥပမာ- တန်ဖိုးတစ်ခု (တန်ဖိုးသည် အကွာအဝေး သို့မဟုတ် အချိန်) ထက်မပိုပဲ လမ်းကွန်ယက်တစ်ခုပေါ်တွင် လမ်းညွှန်သွားလာနိုင်သော နေရာများသည် မည်သည့်နေရာများဖြစ်သလဲ။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector layer representing the network** (**Network ကိုကိုယ်စားပြုသော vector layer**)
     - ``INPUT``
     - [vector: line]
     - လွှမ်းခြုံရမည့် network ကိုကိုယ်စားပြုသော line vector layer
   * - **Start point (x, y)** (**အစမှတ် (x၊ y)**)
     - ``START_POINT``
     - [coordinates]

     - လုပ်ဆောင်မှုဧရိယာ ပတ်လည်တွင် တွက်ချက်မည့် point ၏ ကိုဩဒိနိတ်။
   * - **Path type to calculate** (**တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား**)
     - ``STRATEGY``
     - [enumeration]

       Default: 0
     - တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Shortest (အတိုဆုံး)
       * 1 --- Fastest (အမြန်ဆုံး)
   * - **Travel cost (distance for "Shortest", time for "Fastest")** (**ခရီးသွားကုန်ကျစရိတ် ("အတိုဆုံး" အတွက် အကွာအဝေး၊ "အမြန်ဆုံး" အတွက် အချိန်)**)
     - ``TRAVEL_COST``
     - [number]

       Default: 0
     - *အတိုဆုံး* လမ်းကြောင်းနှင့် *အမြန်ဆုံး* လမ်းကြောင်းအတွက်အချိန် (နာရီဖြင့်) ကိုရှာဖွေသောအခါ အကွာအဝေး (network layer ယူနစ်ဖြင့်) အဖြစ် တန်ဖိုးကိုခန့်မှန်းပါသည်။
   * - **Service area (lines)** (**လုပ်ဆောင်မှုဧရိယာ (line များ)**)
     - ``OUTPUT_LINES``
     - [vector: line]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - လုပ်ဆောင်မှုဧရိယာ အတွက် output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Service area (boundary nodes)** (**လုပ်ဆောင်မှုဧရိယာ (နယ်နိမိတ် အမှတ်များ)**)
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Skip output]``
     - လုပ်ဆောင်မှုဧရိယာ နယ်နိမိတ် ဆုံချက်များအတွက် output point layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: ./networkanalysis.rst
  :start-after: .. **network_advanced_parameters**
  :end-before: .. **end_network_advanced_parameters**

.. list-table::
   :widths: 20 20 20 40

   * - **Include upper/lower bound points** (**အပေါ်ဘက်/အောက်ဘက် ကန့်သတ် point များထည့်သွင်းခြင်း**)
     - ``INCLUDE_BOUNDS``
     - [boolean]

       Default: False
     - လုပ်ဆောင်မှုဧရိယာ၏ နယ်နိမိတ်ပေါ်ရှိ edge တစ်ခုချင်းစီအတွက် point နှစ်ခုပါဝင်သော point layer output တစ်ခုကိုဖန်တီးပေးပါသည်။ Point တစ်ခုသည် ၎င်း edge ၏ အစဖြစ်ပြီး အခြား point သည် အဆုံးသတ် ဖြစ်ပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Service area (boundary nodes)** (**လုပ်ဆောင်မှုဧရိယာ (နယ်နိမိတ် အမှတ်များ)**)
     - ``OUTPUT``
     - [vector: point]
     - လုပ်ဆောင်မှုဧရိယာ နယ်နိမိတ် ဆုံချက်များဖြင့် output point layer
   * - **Service area (lines)** (**လုပ်ဆောင်မှုဧရိယာ (line များ)**)
     - ``OUTPUT_LINES``
     - [vector: line]
     - သတ်မှတ် အကွာအဝေး သို့မဟုတ် အချိန်အတွက် အစမှတ်များမှ သွားလာနိုင်သော network ၏ အစိတ်အပိုင်းများကို ကိုယ်စားပြုသော line layer  

Python code
............

**Algorithm ID**: ``native:serviceareafrompoint``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisshortestpathlayertopoint:

Shortest path (layer to point) (အတိုဆုံးလမ်းကြောင်း (layer မှ point သို့))
---------------------------------------------------------------------------

Vector layer တစ်ခုမှသတ်မှတ်ထားသော အစမှတ်များစွာမှ ဆုံးမှတ်တစ်ခုဆီသို့သွားရန် အကောင်းဆုံး (အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး) လမ်းကြောင်းများကို တွက်ထုတ်ပေးပါသည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector layer representing network** (**Network ကိုကိုယ်စားပြုသော vector layer**)
     - ``INPUT``
     - [vector: line]
     - လွှမ်းခြုံရမည့် network ကိုကိုယ်စားပြုသော line vector layer
   * - **Path type to calculate** (**တွက်ချက်ရန် လမ်းကြောင်းအမျိုးအစား**)
     - ``STRATEGY``
     - [enumeration]

       Default: 0
     - တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Shortest (အတိုဆုံး)
       * 1 --- Fastest (အမြန်ဆုံး)
   * - **Vector layer with start points** (**အစမှတ်များဖြင့် vector layer**)
     - ``START_POINTS``
     - [vector: point]
     - Route များ၏ အစမှတ်များအဖြစ် အသုံးပြုသော feature များပါဝင်သော point vector layer
   * - **End point (x, y)** (**အဆုံးမှတ် (x၊ y)**)
     - ``END_POINT``
     - [coordinates]

     - Route များ၏ အဆုံးမှတ်ကိုကိုယ်စားပြုသော point feature
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အတိုဆုံးလမ်းကြောင်းများအတွက် output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: ./networkanalysis.rst
  :start-after: .. **network_advanced_parameters**
  :end-before: .. **end_network_advanced_parameters**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အစမှတ်တစ်ခုချင်းစီမှ အဆုံးမှတ်သို့ရောက်ရန် အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး လမ်းကြောင်း၏ line layer

Python code
............

**Algorithm ID**: ``native:shortestpathlayertopoint``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisshortestpathpointtolayer:

Shortest path (point to layer) (အတိုဆုံးလမ်းကြောင်း (point မှ layer သို့))
---------------------------------------------------------------------------

Point vector layer တစ်ခုမှ သတ်မှတ်ထားသော အဆုံးမှတ်စွာနှင့် စမှတ်တစ်ခုအကြား အကောင်းဆုံးလမ်းကြောင်းများ (အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး) ကို တွက်ထုတ်ပေးပါသည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector layer representing network** (**ကွန်ယက်ကိုကိုယ်စားပြုသော vector layer**)
     - ``INPUT``
     - [vector: line]
     - လွှမ်းခြုံရမည့် network ကိုကိုယ်စားပြုသော line vector layer
   * - **Path type to calculate** (**တွက်ချက်ရန် လမ်းကြောင်းအမျိုးအစား**)
     - ``STRATEGY``
     - [enumeration]

       Default: 0
     - တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Shortest (အတိုဆုံး)
       * 1 --- Fastest (အမြန်ဆုံး)
   * - **Start point (x, y)** (**အစမှတ် (x၊ y)**)
     - ``START_POINT``
     - [coordinates]
     - Route များ၏အစမှတ်ကိုကိုယ်စားပြုသော point feature
   * - **Vector layer with end points** (**အဆုံးမှတ်များပါဝင်သော vector layer**)
     - ``END_POINTS``

     - [vector: point]
     - Route များ၏အဆုံးမှတ်များအဖြစ် အသုံးပြုသော feature များပါဝင်သည့် point vector layer 
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အတိုဆုံးလမ်းကြောင်းများအတွက် output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: ./networkanalysis.rst
  :start-after: .. **network_advanced_parameters**
  :end-before: .. **end_network_advanced_parameters**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အစမှတ်တစ်ခုချင်းစီမှ အဆုံးမှတ်သို့ရောက်ရန် အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး လမ်းကြောင်း၏ line layer 

Python code
............

**Algorithm ID**: ``native:shortestpathpointtolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisshortestpathpointtopoint:

Shortest path (point to point) (အတိုဆုံးလမ်းကြောင်း (point မှ point သို့))
---------------------------------------------------------------------------
Computes the optimal (shortest or fastest) route between a given start
point and a given end point.

အစမှတ်တစ်ခုမှ အဆုံးမှတ်တစ်ခုအကြားရှိ အကောင်းဆုံး (အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး) လမ်းကြောင်း  ကို တွက်ချက်ပေးပါသည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector layer representing network** (**Network ကိုကိုယ်စားပြုသော vector layer**)
     - ``INPUT``
     - [vector: line]
     - လွှမ်းခြုံရမည့် network ကိုကိုယ်စားပြုသော line vector layer
   * - **Path type to calculate** (**တွက်ချက်ရန် လမ်းကြောင်းအမျိုးအစား**)
     - ``STRATEGY``
     - [enumeration]

       Default: 0
     - တွက်ချက်မည့် လမ်းကြောင်းအမျိုးအစား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Shortest (အတိုဆုံး)
       * 1 --- Fastest (အမြန်ဆုံး)
   * - **Start point (x, y)** (**အစမှတ် (x၊ y)**)
     - ``START_POINT``
     - [coordinates]
     - Route များ၏အစမှတ်ကိုကိုယ်စားပြုသော point feature
   * - **End point (x, y)** (**အဆုံးမှတ် (x၊ y)**)
     - ``END_POINT``
     - [coordinates]
     - Route များ၏ အဆုံးမှတ်ကိုကိုယ်စားပြုသော point feature
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အတိုဆုံးလမ်းကြောင်းများအတွက် output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. include:: ./networkanalysis.rst
  :start-after: .. **network_advanced_parameters**
  :end-before: .. **end_network_advanced_parameters**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Shortest path** (**အတိုဆုံးလမ်းကြောင်း**)
     - ``OUTPUT``
     - [vector: line]
     - အစမှတ်တစ်ခုချင်းစီမှ အဆုံးမှတ်သို့ရောက်ရန် အတိုဆုံး သို့မဟုတ် အမြန်ဆုံး လမ်းကြောင်း၏ line layer

Python code
............

**Algorithm ID**: ``native:shortestpathpointtopoint``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
