Cartography (မြေပုံရေးဆွဲခြင်းပညာ)
===================================

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc_columns

.. _qgisangletonearest:

Align points to features (Point များကို feature များနှင့်ညီအောင် ညှိခြင်း)
---------------------------------------------------------------------------

Point feature များကို အခြား reference layer (ရည်ညွှန်း layer) တစ်ခုမှ ၎င်းတို့၏အနီးဆုံး feature များနှင့် အတန်းညီစေရန် လိုအပ်သော rotation (လှည့်ထောင့်) ကို တွက်ချက်ပေးပါသည်။ အနီးဆုံး reference feature တွင် ထောင့် (ဒီဂရီဖြင့်၊ နာရီလက်တံပြောင်းပြန်) ဖြင့်ဖြည့်ပေးသော output layer သို့ field အသစ်တစ်ခုထည့်ပေါင်းပေးပါသည်။

Marker symbol များကိုလှည့်ရန် တွက်ထုတ်ထားသော လှည့်ထောင့်တန်ဖိုးပါသည့် column ကိုအလိုအလျှောက်အသုံးပြုရန် output layer ၏ symbology (သင်္ကေတ) ကိုသတ်မှတ်နိုင်ပါသည်။ လိုအပ်လျှင် သီးခြားဖြစ်နေသော point များကို ဝေးကွာသော feature များနှင့် အတန်းညီအောင်ညှိခြင်းကို မဖြစ်စေရန် point များကို အတန်းညီအောင်ညှိသောအခါ အများဆုံးအကွာအဝေးကို သတ်မှတ်နိုင်ပါသည်။

 
.. hint:: အဆောက်အဦ point symbol များကို အနီးဆုံး လမ်းဦးတည်ရာအတိုင်း လိုက်သွားစေရန် ကဲ့သို့ ကိစ္စမျိုးအတွက် ယခု algorithm ကိုဖန်တီးထားခြင်း ဖြစ်ပါသည်။

|checkbox| Point feature များ၏ :ref:`features in-place modification (feature များကိုနေရာတွင် မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကိုလုပ်ဆောင်ပေးနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: point]
     - လှည့်ထောင့်ကိုတွက်ချက်မည့် point feature များ
   * - **Reference layer** (**ရည်ညွှန်း layer**)
     - ``REFERENCE_LAYER``
     - [vector: any]
     - လှည့်ထောင့် တွက်ချက်ခြင်းအတွက် မှ အနီးဆုံး feature ကို ရှာရန် layer
   * - **Maximum distance to consider** (**ထည့်သွင်းစဉ်းစားရန် အများဆုံးအကွာအဝေး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAX_DISTANCE``
     - [number]

       Default: Not set
     - ၎င်းအကွာအဝေးထဲတွင် reference feature ကိုမတွေ့လျှင် point feature တွင် လှည့်ထောင့်ကို သတ်မှတ်မပေးပါ။
   * - **Angle field name** (**ထောင့် field နာမည်**)
     - ``FIELD_NAME``
     - [string]

       Default: 'rotation' 
     - လှည့်ထောင့်တန်ဖိုးကို သိမ်းဆည်းထားမည့် field
   * - **Automatically apply symbology** (**သင်္ကေတဆိုင်ရာ ကိုအလိုအလျှောက်အသုံးချခြင်း**)
     - ``APPLY_SYMBOLOGY``
     - [boolean]

       Default: True
     - ထောင့် field တန်ဖိုးကိုအသုံးပြုပြီး feature များ၏ သင်္ကေတ marker ကိုလှည့်ပေးပါသည်
   * - **Aligned layer** (**အတန်းညီအောင်ညှိထားသော layer**)
     - ``OUTPUT``
     - [vector: point]
       
       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - လှည့်ထားသော output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Aligned layer** (**အတန်းညီအောင်ညှိထားသော layer**)
     - ``OUTPUT``
     - [vector: point]
     - Point layer ကို လှည့်ထောင့်တန်ဖိုးပါသော field တစ်ခုဖြင့် ချိတ်တွဲပေါင်းထည့်ထားပါသည်။ QGIS ထဲသို့ထည့်သွင်းလျှင် marker သင်္ကေတ၏ data သတ်မှတ်ထားသော လှည့်ထောင့်တစ်ခုဖြင့် ၎င်းကို default အနေဖြင့် input layer သင်္ကေတတွင် အသုံးချပါသည်။

Python code
............

**Algorithm ID**: ``native:angletonearest``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscombinestyles:

Combine style databases (Style database များကိုပေါင်းစပ်ခြင်း)
---------------------------------------------------------------

QGIS style database များစွာကို style database တစ်ခုတည်းအဖြစ်သို့ပေါင်းစပ်ပေးပါသည်။ မတူညီသော ရင်းမြစ် database များထဲတွင် နာမည်တူညီပြီး အမျိုးအစားတူညီသော item များရှိနေလျှင် ထွက်လာမည့် ပေါင်းစပ်ထားသော database ထဲတွင် ၎င်းတို့ကို မတူညီသောနာမည်များ အဖြစ် နာမည်အသစ်များပေးပါလိမ့်မည်။

.. seealso:: :ref:`qgisstylefromproject`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input databases** (**ထည့်သွင်းအသုံးပြုသော database များ**)
     - ``INPUT``
     - [file] [list]
     - QGIS style item များပါဝင်သော file များ
   * - **Objects to combine** (**ပေါင်းစပ်မည့် object များ**)
     - ``OBJECTS``
     - [enumeration] [list]
     - Database အသစ်ထဲတွင် ထည့်လိုသည့် input database များထဲရှိ style item များ၏အမျိုးအစားများ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- :ref:`Symbols <edit_symbol>` (သင်္ကေတများ)
       * 1 --- :ref:`Color ramps <color-ramp>` (ရောင်စဉ်တန်းများ)
       * 2 --- :ref:`Text formats <text_format>` (စာသား format များ)
       * 3 --- :ref:`Label settings <showlabels>` (အညွှန်း setting များ)

   * - **Output style database**
     - ``OUTPUT``
     - [file]
       
       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - ရွေးချယ်ထားသော style item များကိုပေါင်းစပ်ထားသော Output :file:`.XML` file ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Color ramp count** (**ရောင်စဉ်တန်း အရေအတွက်**)
     - ``COLORRAMPS``
     - [number]
     - 
   * - **Label settings count** (**အညွှန်း setting များအရေအတွက်**)
     - ``LABELSETTINGS``
     - [number]
     - 
   * - **Output style database**
     - ``OUTPUT``
     - [file]
     - ရွေးချယ်ထားသော style item များကိုပေါင်းစပ်ထားသော output :file:`.XML` file
   * - **Symbol count** (**Symbol အရေအတွက်**)
     - ``SYMBOLS``
     - [number]
     - 
   * - **Text format count** (**စာသား format အရေအတွက်**)
     - ``TEXTFORMATS``
     - [number]
     - 

Python code
............

**Algorithm ID**: ``native:combinestyles``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscategorizeusingstyle:

Create categorized renderer from styles (အမျိုးအစားဖြင့်ခွဲခြားထားသော ပုံဖော်ပြသပေးသည့်အရာကို Style များမှ ဖန်တီးခြင်း)
------------------------------------------------------------------------------------------------------------------------

Style database တစ်ခုမှ ကိုက်ညီသော သင်္ကေတများကိုအသုံးပြုပြီး vector layer ၏ ပုံဖော်ပြသပေးသည့်အရာ (renderer) တစ်ခုကို အမျိုးအစားဖြင့်ခွဲခြားထားသော ပုံဖော်ပြသပေးသည့်အရာ (renderer) တစ်ခုသို့သတ်မှတ်ပေးပါသည်။ မည်သည့် style မှ သတ်မှတ်မထားလျှင် အသုံးပြုသူ၏ လက်ရှိ :ref:`symbol library <vector_symbol_library>` မှ သင်္ကေတများကိုအသုံးပြုပါသည်။


Renderer အတွက် အမျိုးအစားများကို ဖန်တီးရန် သီးခြား expression တစ်ခု သို့မဟုတ် field တစ်ခုကိုအသုံးပြုပါသည်။ QGIS XML style database ထဲတွင် ရှိသော သင်္ကေတများနှင့် အမျိုးအစားတစ်ခုချင်းစီကို ယှဉ်တွဲပေးပါသည်။ ကိုက်ညီသော သင်္ကေတ နာမည်ကိုတွေ့သည့်အခါတိုင်း အမျိုးအစား၏သင်္ကေတကို ၎င်းနှင့်ကိုက်ညီသော သင်္ကေတသို့သတ်မှတ်ပေးပါသည်။

လိုအပ်လျှင် output များသည် သင်္ကေတများနှင့် ယှဉ်တွဲပေး၍မရနိုင်သော အမျိုးအစားများ နှင့် အမျိုးအစားများနှင့် မကိုက်ညီခဲ့သော သင်္ကေတများစာရင်းပါဝင်သော ဇယားလည်း ဖြစ်နိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - အမျိုးအစားခွဲထားသော style ကိုအသုံးပြုမည့် vector layer
   * - **Categorize using expression** (**Expression ကိုအသုံးပြုပြီး အမျိုးအစားခွဲခြားခြင်း**)
     - ``FIELD``
     - [expression]
     - Feature များကို အမျိုးအစားခွဲခြားရန် field သို့မဟုတ် expression
   * - **Style database (leave blank to use saved symbols)** (**Style database (သိမ်းထားသော symbol များကိုအသုံးပြုရန် ဗလာထားပါ)**)
     - ``STYLE``
     - [file]
     - Input layer အမျိုးအစားများတွင် အသုံးချရန် သင်္ကေတများပါဝင်သော file (:file:`.XML`)။ File ကို Style Manager :ref:`Share symbols <share_symbols>` tool မှ ရရှိနိုင်ပါသည်။ File သတ်မှတ်မထားလျှင် QGIS ထဲရှိ သင်္ကေတများ library ကိုအသုံးပြုပါသည်။
   * - **Use case-sensitive match to symbol names** (**Symbol နာမည်များကို စာလုံးအကြီးအသေး လွဲလို့မရသော ယှဉ်တွဲမှုကိုအသုံးပြုခြင်း**)
     - ``CASE_SENSITIVE``
     - [boolean]

       Default: False
     - True (အမှန်ခြစ်ထားလျှင်) ကိုထားလျှင် အမျိုးအစားများနှင့် သင်္ကေတနာမည်များအကြားတွင် စာလုံးအကြီးအသေး လွဲလို့မရသော နှိုင်းယှဉ်မှုကို အသုံးပြုပါမည်။
   * - **Ignore non-alphanumeric characters while matching** (**ယှဉ်တွဲစဉ်တွင် အက္ခရာမဟုတ်သော character များကို လျှစ်လျှူရှုခြင်း**)
     - ``TOLERANT``
     - [boolean]

       Default: False
     - True (အမှန်ခြစ်ထားလျှင်) ကိုထားလျှင် အမျိုးအစားများနှင့် သင်္ကေတနာမည်များထဲရှိ အက္ခရာမဟုတ်သော character များကို လျစ်လျှူရှုပြီး ယှဉ်တွဲစဉ်တွင် ပိုကောင်းသော ယှဉ်တွဲနိုင်စွမ်းကို ရရှိစေပါသည်။ 
   * - **Non-matching categories** (**မကိုက်ညီသော အမျိုးအစားများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NON_MATCHING_CATEGORIES``
     - [table]

       Default: ``[Skip output] ([Output ကိုကျော်ပစ်ခြင်း])``
     - Database ထဲရှိ မည်သည့် သင်္ကေတနှင့်မှ မကိုက်ညီသော အမျိုးအစားများအတွက် output ဇယား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

   * - **Non-matching symbol names** (**မကိုက်ညီသော သင်္ကေတ နာမည်များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NON_MATCHING_SYMBOLS``
     - [table]

       Default: ``[Skip output] ([Output ကိုကျော်ပစ်ခြင်း])``
     - မည်သည့် အမျိုးအစားနှင့်မှ မကိုက်ညီသော အသုံးပြုထားသည့် style database မှ သင်္ကေတများအတွက် output ဇယား။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Non-matching categories** (**မကိုက်ညီသော အမျိုးအစားများ**)
     - ``NON_MATCHING_CATEGORIES``
     - [table]

     - အသုံးပြုထားသော style database ထဲရှိ မည်သည့် သင်္ကေတနှင့်မှ ယှဉ်တွဲပေး၍မရနိုင်သော အမျိုးအစားများကို စာရင်းပြုစုပေးပါသည်
   * - **Non-matching symbol names** (**မကိုက်ညီသော သင်္ကေတ နာမည်များ**)
     - ``NON_MATCHING_SYMBOLS``
     - [table]

     - မည်သည့် အမျိုးအစားနှင့်မှ ယှဉ်တွဲပေး၍မရနိုင်သော အသုံးပြုထားသည့် style database မှ သင်္ကေတ များကို စာရင်းပြုစုပေးပါသည်
   * - **Categorized layer** (**အမျိုးအစားအစားခွဲခြားထားသော layer**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - အမျိုးအစားခွဲခြားထားသော style အသုံးပြုထားသည့် input vector layer ။ Output အနေဖြင့် layer အသစ် ရရှိမည်မဟုတ်ပါ။

Python code
............

**Algorithm ID**: ``native:categorizeusingstyle``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisstylefromproject:

Create style database from project (Project မှ style database ဖန်တီးခြင်း)
---------------------------------------------------------------------------

QGIS project တစ်ခုမှ style object များအားလုံး (သင်္ကေတများ၊ ရောင်စဉ်တန်းများ၊ စာသား format များနှင့် အညွှန်း setting များ) ကို ဆွဲထုတ်ပေးပါသည်။


:ref:`Style Manager <vector_style_manager>` dialog မှ ထည့်သွင်းပြီး စီမံခန့်ခွဲနိုင်သော QGIS style database (:file:`XML` format) တစ်ခုထဲတွင် ဆွဲထုတ်ထားသော သင်္ကေတများကိုသိမ်းဆည်းပါသည်။

.. seealso:: :ref:`qgiscombinestyles`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input project (leave blank to use current)** (**ထည့်သွင်းအသုံးပြုသော project (လက်ရှိကိုအသုံးပြုရန် ဗလာအဖြစ်ထားပါ)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT``
     - [file]
     - Style item များကို ဆွဲထုတ်ရန် QGIS project file တစ်ခု
   * - **Objects to extract** (**ဆွဲထုတ်မည့် object များ**)
     - ``OBJECTS``
     - [enumeration] [list]
     - Database အသစ်ထဲသို့ထည့်လိုသော input project ထဲရှိ style item အမျိုးအစားများ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်နိုင်ပါသည် -

       * 0 --- :ref:`Symbols <edit_symbol>` (သင်္ကေတများ)
       * 1 --- :ref:`Color ramps <color-ramp>` (ရောင်စဉ်တန်းများ)
       * 2 --- :ref:`Text formats <text_format>` (စာသား format များ)
       * 3 --- :ref:`Label settings <showlabels>` (အညွှန်း setting များ)

   * - **Output style database**
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - ရွေးချယ်ထားသော style item များအတွက် output :file:`.XML` file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Color ramp count** (**ရောင်စဉ်တန်းအရေအတွက်**)
     - ``COLORRAMPS``
     - [number]
     - ရောင်စဉ်တန်းများ အရေအတွက်
   * - **Label settings count** (**Label setting အရေအတွက်**)
     - ``LABELSETTINGS``
     - [number]
     - Label setting များအရေအတွက်
   * - **Output style database**
     - ``OUTPUT``
     - [file]
     - ရွေးချယ်ထားသော style item များအတွက် output :file:`.XML` file
   * - **Symbol count** (**Symbol အရေအတွက်**)
     - ``SYMBOLS``
     - [number]
     - သင်္ကေတများအရေအတွက်
   * - **Text format count** (**စာသား format အရေအတွက်**)
     - ``TEXTFORMATS``
     - [number]
     - စာသား format များအရေအတွက်

Python code
............

**Algorithm ID**: ``native:stylefromproject``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisatlaslayouttoimage:

Export atlas layout as image (မြေပုံစီးရီး အပြင်အဆင်ကို ဓာတ်ပုံအဖြစ်ထုတ်ခြင်း)
-------------------------------------------------------------------------------

မြေပုံ layout တစ်ခု၏ atlas (မြေပုံစီးရီး) ကို image file များအဖြစ် ထုတ်ယူပေးပါသည် (ဥပမာ- PNG သို့မဟုတ် JPEG ဓာတ်ပုံများ)။

လွှမ်းခြုံမှု layer တစ်ခုကိုသတ်မှတ်ထားလျှင် ယခု algorithm ထဲတွင် ဖော်ပြသည့် ရွေးချယ်ထားသော layout atlas setting များကို အစားထိုးပြင်ဆင်လိမ့်မည်ဖြစ်သည်။ ယခုကိစ္စတွင် ဘာမှမရှိသော စစ်ထုတ်မှု သို့မဟုတ် expression ဖြင့် စီစဉ်ထားမှုတို့သည် ၎င်း setting များကို ပိတ်ပစ်ပါမည်။

Parameters (Parameter များ)
............................

အခြေခံ parameter များ (Basic parameters)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Atlas layout**
     - ``LAYOUT``
     - [layout]
     - Export ထုတ်မည့် layout
   * - **Coverage layer** (**လွှမ်းခြုံမှု layer**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``COVERAGE_LAYER``
     - [vector: any]
     - Atlas (မြေပုံစီးရီး) ကိုဖန်တီးရန် အသုံးပြုသော layer
   * - **Filter expression** (**စစ်ထုတ်ခြင်း expression**)
     - ``FILTER_EXPRESSION``
     - [expression]
     - Atlas feature များကိုစစ်ထုတ်ရန် အသုံးပြုမည့် expression
   * - **Sort expression** (**စီစဉ်မှု expression**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_EXPRESSION``
     - [expression]
     - Altas feature များကိုစီစဉ်ရန် အသုံးပြုမည့် expression
   * - **Reverse sort order** (**ပြောင်းပြန်စီစဉ်မှု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_REVERSE``
     - [boolean]
     - စီစဉ်ထားမှုကို ပြောင်းပြန်လုပ်သင့်လား ဆုံးဖြတ်ပေးပါသည်။ စီစဉ်မှု expression တစ်ခုကိုအသုံးပြုထားသောအခါမျိုးတွင် ယခုနည်းလမ်းကို အသုံးပြုပါ။
   * - **Output filename expression** (**Output file အမည်အတွက် expression**)
     - ``FILENAME_EXPRESSION``
     - [expression]

       Default: 'output\_'||\@atlas_featurenumber
     - File အမည်များဖန်တီးရန်အတွက် အသုံးပြုမည့် expression
   * - **Output folder**
     - ``FOLDER``
     - [folder]
     - ဓာတ်ပုံများကိုထုတ်ပေးမည့် folder

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map layers to assign to unlocked map item(s)** (**Unlock (သော့မခတ်ထားသော) map item များတွင် သတ်မှတ်မည့် map layer များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYERS``
     - [enumeration] [layer]
     - Lock (သော့ခတ်ထားခြင်း) မလုပ်ထားသော map item များထဲတွင် ပြသရန် layer များ
   * - **Image format**
     - ``EXTENSION``
     - [enumeration]

       Default: png
     - ဖန်တီးထားသော output များ၏ file format ။ အသုံးပြုနိုင်သော format များ၏စာရင်းသည် OS သို့မဟုတ် ထည့်သွင်းထားသော driver များပေါ်တွင်မူတည်ပြီး ပြောင်းလဲပါသည်။
   * - **DPI**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: Not set (သတ်မှတ်မထားပါ)
     - [number]
     - Output file များ၏ DPI ။ သတ်မှတ်မထားလျှင် print layout setting များထဲရှိ တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Generate world file** (**World file ကိုဖန်တီးခြင်း**)
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - World file တစ်ခုကို ဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Export RDF metadata** (**RDF metadata ကိုထုတ်ခြင်း**)
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - RDF metadata (ခေါင်းစဉ်၊ ဖန်တီးသူ၊ ...) ကိုဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Enable antialiasing** (**Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပေးခြင်း**)
     - ``ANTIALIAS``
     - [boolean]

       Default: True
     - Antialiasing ကိုအသုံးပြုလို့ရအောင်ဖွင့်ပေးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Image file**
     - ``OUTPUT``
     - [file]
     - Altas layout ဖြင့် ဖန်တီးထားသော image file များ

Python code
............

**Algorithm ID**: ``native:atlaslayouttoimage``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisatlaslayouttomultiplepdf:

Export atlas layout as PDF (multiple files) (Altas layout ကို PDF အဖြစ်ထုတ်ခြင်း (file များစွာ))
-------------------------------------------------------------------------------------------------

Print layout ၏ atlas ကို PDF file များစွာအဖြစ် ထုတ်ပေးပါသည်။

လွှမ်းခြုံမှု layer တစ်ခုကိုသတ်မှတ်ထားလျှင် ယခု algorithm ထဲတွင် ဖော်ပြသည့် ရွေးချယ်ထားသော layout atlas setting များကို အစားထိုးပြင်ဆင်လိမ့်မည်ဖြစ်သည်။ ယခုကိစ္စတွင် ဘာမှမရှိသော စစ်ထုတ်မှု သို့မဟုတ် expression ဖြင့် စီစဉ်ထားမှုတို့သည် ၎င်း setting များကို ပိတ်ပစ်ပါမည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Atlas layout**
     - ``LAYOUT``
     - [layout]
     - Export ထုတ်မည့် layout
   * - **Coverage layer** (**လွှမ်းခြုံမှု layer**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``COVERAGE_LAYER``
     - [vector: any]
     - Atlas ကိုဖန်တီးရန် အသုံးပြုမည့် layer
   * - **Filter expression** (**စစ်ထုတ်ခြင်း expression**)
     - ``FILTER_EXPRESSION``
     - [expression]

     - Atlas feature များကိုစစ်ထုတ်ရန် အသုံးပြုမည့် expression
   * - **Sort expression** (**စီစဉ်မှု expression**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_EXPRESSION``
     - [expression]
     - Altas feature များကိုစီစဉ်ရန် အသုံးပြုမည့် expression
   * - **Reverse sort order** (**ပြောင်းပြန်စီစဉ်မှု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_REVERSE``
     - [boolean]
     - စီစဉ်ထားမှုကို ပြောင်းပြန်လုပ်သင့်လား ဆုံးဖြတ်ပေးပါသည်။ စီစဉ်မှု expression တစ်ခုကိုအသုံးပြုထားသောအခါမျိုးတွင် ယခုနည်းလမ်းကို အသုံးပြုပါ။
   * - **Output filename** (**Output file အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT_FILENAME``
     - [expression]
     - PDF output file များ၏ အမည်ပုံစံ
   * - **Output folder**
     - ``OUTPUT_FOLDER``
     - [folder]
     - Output PDF file များအတွက် သိမ်းထားမည့် folder။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map layers to assign to unlocked map item(s)** (**Unlock (သော့မခတ်ထားသော) map item များတွင် သတ်မှတ်မည့် map layer များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYERS``
     - [enumeration] [layer]
     - Lock (သော့ခတ်ထားခြင်း) မလုပ်ထားသော map item များထဲတွင် ပြသရန် layer များ
   * - **DPI**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: Not set (သတ်မှတ်မထားပါ)
     - [number]
     - Output file များ၏ DPI ။ သတ်မှတ်မထားလျှင် print layout setting များထဲရှိ တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Always export as vectors** (**Vector များအဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_VECTOR``
     - [boolean]

       Default: False
     - Vectorial data များကို vector များအဖြစ် ချန်ထားသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Always export as raster** (**Raster အဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_RASTER``
     - [boolean]

       Default: False
     - Raster အဖြစ်ပြောင်းလဲရန် map ထဲရှိ item များအားလုံးကိုတွန်းအားပေး လုပ်ဆောင်ပါသည်။ ယခု parameter သည် ``FORCE_VECTOR`` parameter ထက်ပိုပြီးဦးစားပေးခံရပါသည်။
   * - **Append georeference information** (**Georeference သတင်းအချက်အလက်များကို ချိတ်တွဲပေါင်းထည့်ခြင်း**)
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - World file တစ်ခုကို ဖန်တီးသင့်/အသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Export RDF metadata** (**RDF metadata များ export ထုတ်ခြင်း**)
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - RDF metadata (ခေါင်းစဉ်၊ ဖန်တီးသူ၊ ...) ကိုဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Disable tiled raster layer exports** (**Tile ပြုလုပ်ထားသော raster layer export ထုတ်ခြင်းများကို ပိတ်ထားခြင်း**)
     - ``DISABLE_TILED``
     - [boolean]

       Default: False
     - Raster ကို tile လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Simplify geometries to reduce output file size** (**Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို ရိုးရှင်းအောင်လုပ်ခြင်း**)
     - ``SIMPLIFY``
     - [boolean]

       Default: True
     - Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို simplify (ရိုးရှင်းအောင်) လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Text export** (**စာသား export ထုတ်ခြင်း**)
     - ``TEXT_FORMAT``
     - [enumeration]

       Default: 0
     - စာသားများကို လမ်းကြောင်း သို့မဟုတ် စာသား object များအဖြစ် ထုတ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Always export text as paths (recommended) (စာသားကို လမ်းကြောင်းများအဖြစ် အမြဲတမ်းထုတ်ခြင်း (အကြံပြုထားသော))
       * 1 - Always export texts as text objects (စာသားများကို စာသား object များအဖြစ် အမြဲတမ်းထုတ်ခြင်း)
   * - **Image compression** (**ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း**)
     - ``IMAGE_COMPRESSION``
     - [enumeration]

       Default: 0
     - ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း level နှင့် output များ print ထုတ်ခြင်း သို့မဟုတ် ပြင်ပ application များထဲတွင် နောက်ပိုင်းလုပ်ဆောင်မှုများအတွက် file သည် မည်မျှသင့်တော်နိုင်မည်ကို ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Lossy (JPEG)
       * 1 - Lossless

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **PDF file**
     - ``OUTPUT``
     - [file]
     - Export ထုတ်လိုက်သော atlas layout နှင့် သက်ဆိုင်သော PDF file

Python code
............

**Algorithm ID**: ``native:atlaslayouttomultiplepdf``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisatlaslayouttopdf:

Export atlas layout as PDF (single file) (Altas layout ကို PDF အဖြစ်ထုတ်ခြင်း (file တစ်ခုတည်း))
------------------------------------------------------------------------------------------------

Print layout တစ်ခု၏ atlas ကို PDF file တစ်ခုတည်းအဖြစ် ထုတ်ပေးပါသည်။

လွှမ်းခြုံမှု layer တစ်ခုကိုသတ်မှတ်ထားလျှင် ယခု algorithm ထဲတွင် ဖော်ပြသည့် ရွေးချယ်ထားသော layout atlas setting များကို အစားထိုးပြင်ဆင်လိမ့်မည်ဖြစ်သည်။ ယခုကိစ္စတွင် ဘာမှမရှိသော စစ်ထုတ်မှု သို့မဟုတ် expression ဖြင့် စီစဉ်ထားမှုတို့သည် ၎င်း setting များကို ပိတ်ပစ်ပါမည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Atlas layout**
     - ``LAYOUT``
     - [layout]
     - Export ထုတ်မည့် layout
   * - **Coverage layer** (**လွှမ်းခြုံမှု layer**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``COVERAGE_LAYER``
     - [vector: any]
     - Atlas ကိုဖန်တီးရန် အသုံးပြုမည့် layer
   * - **Filter expression** (**စစ်ထုတ်ခြင်း expression**)
     - ``FILTER_EXPRESSION``
     - [expression]
     - Atlas feature များကိုစစ်ထုတ်ရန် အသုံးပြုမည့် expression
   * - **Sort expression** (**စီစဉ်မှု expression**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_EXPRESSION``
     - [expression]
     - Altas feature များကိုစီစဉ်ရန် အသုံးပြုမည့် expression
   * - **Reverse sort order** (**ပြောင်းပြန်စီစဉ်မှု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SORTBY_REVERSE``
     - [boolean]

     - စီစဉ်ထားမှုကို ပြောင်းပြန်လုပ်သင့်လား ဆုံးဖြတ်ပေးပါသည်။ စီစဉ်မှု expression တစ်ခုကိုအသုံးပြုထားသောအခါမျိုးတွင် ယခုနည်းလမ်းကို အသုံးပြုပါ။
   * - **PDF file**
     - ``OUTPUT``
     - [file]

       Default: [Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])
     - Output file ၏အမည် (လမ်းကြောင်းအပါအဝင်)။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map layers to assign to unlocked map item(s)** (**Unlock (သော့မခတ်ထားသော) map item များတွင် သတ်မှတ်မည့် map layer များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYERS``
     - [enumeration] [layer]
     - Lock (သော့ခတ်ထားခြင်း) မလုပ်ထားသော map item များထဲတွင် ပြသရန် layer များ
   * - **DPI**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: Not set (သတ်မှတ်မထားပါ)
     - [number]
     - Output file များ၏ DPI ။ သတ်မှတ်မထားလျှင် print layout setting များထဲရှိ တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Always export as vectors** (**Vector များအဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_VECTOR``
     - [boolean]

       Default: False
     - Vectorial data များကို vector များအဖြစ် ချန်ထားသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Always export as raster** (**Raster အဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_RASTER``
     - [boolean]

       Default: False
     - Raster အဖြစ်ပြောင်းလဲရန် map ထဲရှိ item များအားလုံးကိုတွန်းအားပေး လုပ်ဆောင်ပါသည်။ ယခု parameter သည် ``FORCE_VECTOR`` parameter ထက်ပိုပြီးဦးစားပေးခံရပါသည်။
   * - **Append georeference information** (**Georeference သတင်းအချက်အလက်များကို ချိတ်တွဲပေါင်းထည့်ခြင်း**)
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - World file တစ်ခုကို ဖန်တီးသင့်/အသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Export RDF metadata** (**RDF metadata များ export ထုတ်ခြင်း**)
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - RDF metadata (ခေါင်းစဉ်၊ ဖန်တီးသူ၊ ...) ကိုဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Disable tiled raster layer exports** (**Tile ပြုလုပ်ထားသော raster layer export ထုတ်ခြင်းများကို ပိတ်ထားခြင်း**)
     - ``DISABLE_TILED``
     - [boolean]

       Default: False
     - Raster ကို tile လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Simplify geometries to reduce output file size** (**Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို ရိုးရှင်းအောင်လုပ်ခြင်း**)
     - ``SIMPLIFY``
     - [boolean]

       Default: True
     - Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို simplify (ရိုးရှင်းအောင်) လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Text export** (**စာသား export ထုတ်ခြင်း**)
     - ``TEXT_FORMAT``
     - [enumeration]

       Default: 0
     - စာသားများကို လမ်းကြောင်း သို့မဟုတ် စာသား object များအဖြစ် ထုတ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Always export text as paths (recommended) (စာသားကို လမ်းကြောင်းများအဖြစ် အမြဲတမ်းထုတ်ခြင်း (အကြံပြုထားသော))
       * 1 - Always export texts as text objects (စာသားများကို စာသား object များအဖြစ် အမြဲတမ်းထုတ်ခြင်း)
   * - **Image compression** (**ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း**)
     - ``IMAGE_COMPRESSION``
     - [enumeration]

       Default: 0
     - ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း level နှင့် output များ print ထုတ်ခြင်း သို့မဟုတ် ပြင်ပ application များထဲတွင် နောက်ပိုင်းလုပ်ဆောင်မှုများအတွက် file သည် မည်မျှသင့်တော်နိုင်မည်ကို ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Lossy (JPEG)
       * 1 - Lossless

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **PDF file**
     - ``OUTPUT``
     - [file]
     - Export ထုတ်လိုက်သော atlas layout နှင့် သက်ဆိုင်သော PDF file

Python code
............

**Algorithm ID**: ``native:atlaslayouttopdf``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisprintlayouttoimage:

Export print layout as image (Print layout ကို ဓာတ်ပုံတစ်ပုံအဖြစ် ထုတ်ခြင်း)
-----------------------------------------------------------------------------

Print layout ကို ဓာတ်ပုံတစ်ပုံအဖြစ် ထုတ်ပေးပါသည် (ဥပမာ- PNG သို့မဟုတ် JPEG ဓာတ်ပုံများ)။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Print layout** (**ပုံထုတ်အပြင်အဆင်**)
     - ``LAYOUT``
     - [layout]
     - Export ထုတ်မည့် layout
   * - **Image file**
     - ``OUTPUT``
     - [file]

       Default: [Save to temporary file])
     - Output file ၏အမည် (လမ်းကြောင်းအပါအဝင်)။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map layers to assign to unlocked map item(s)** (**Unlock (သော့မခတ်ထားသော) map item များတွင် သတ်မှတ်မည့် map layer များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYERS``
     - [enumeration] [layer]
     - Lock (သော့ခတ်ထားခြင်း) မလုပ်ထားသော map item များထဲတွင် ပြသရန် layer များ
   * - **DPI** (**Dot per inch**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: Not set (သတ်မှတ်မထားပါ)
     - [number]
     - Output file များ၏ DPI ။ သတ်မှတ်မထားလျှင် print layout setting များထဲရှိ တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Generate world file** (**World file ကိုဖန်တီးခြင်း**)
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - World file တစ်ခုကို ဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Export RDF metadata** (**RDF metadata ကိုထုတ်ခြင်း**)
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - RDF metadata (ခေါင်းစဉ်၊ ဖန်တီးသူ၊ ...) ကိုဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Enable antialiasing** (**Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပေးခြင်း**)
     - ``ANTIALIAS``
     - [boolean]

       Default: True
     - Antialiasing ကိုအသုံးပြုလို့ရအောင်ဖွင့်ပေးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Image file**
     - ``OUTPUT``
     - [file]
     - Export ထုတ်လိုက်သော print layout နှင့်သက်ဆိုင်သော image file

Python code
............

**Algorithm ID**: ``native:printlayouttoimage``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisprintlayouttopdf:

Export print layout as PDF (Print layout ကို PDF အဖြစ်ထုတ်ခြင်း)
-----------------------------------------------------------------

Print layout ကို PDF အဖြစ်ထုတ်ပေးပါသည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Print Layout**
     - ``LAYOUT``
     - [layout]
     - Export ထုတ်မည့် layout
   * - **PDF file**
     - ``OUTPUT``
     - [file]

       Default: [Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])
     - Output file ၏အမည် (လမ်းကြောင်းအပါအဝင်)။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map layers to assign to unlocked map item(s)** (**Unlock (သော့မခတ်ထားသော) map item များတွင် သတ်မှတ်မည့် map layer များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYERS``
     - [enumeration] [layer]
     - Lock (သော့ခတ်ထားခြင်း) မလုပ်ထားသော map item များထဲတွင် ပြသရန် layer များ
   * - **DPI**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: Not set (သတ်မှတ်မထားပါ)
     - [number]
     - Output file များ၏ DPI ။ သတ်မှတ်မထားလျှင် print layout setting များထဲရှိ တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Always export as vectors** (**Vector များအဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_VECTOR``
     - [boolean]

       Default: False
     - Vectorial data များကို vector များအဖြစ် ချန်ထားသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Always export as raster** (**Raster အဖြစ် အမြဲတမ်း export ထုတ်ခြင်း**)
     - ``FORCE_RASTER``
     - [boolean]

       Default: False
     - Raster အဖြစ်ပြောင်းလဲရန် map ထဲရှိ item များအားလုံးကိုတွန်းအားပေး လုပ်ဆောင်ပါသည်။ ယခု parameter သည် ``FORCE_VECTOR`` parameter ထက်ပိုပြီးဦးစားပေးခံရပါသည်။
   * - **Append georeference information** (**Georeference သတင်းအချက်အလက်များကို ချိတ်တွဲပေါင်းထည့်ခြင်း**)
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - World file တစ်ခုကို ဖန်တီးသင့်/အသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Export RDF metadata** (**RDF metadata များ export ထုတ်ခြင်း**)
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - RDF metadata (ခေါင်းစဉ်၊ ဖန်တီးသူ၊ ...) ကိုဖန်တီးသင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Disable tiled raster layer exports** (**Tile ပြုလုပ်ထားသော raster layer export ထုတ်ခြင်းများကို ပိတ်ထားခြင်း**)
     - ``DISABLE_TILED``
     - [boolean]

       Default: False
     - Raster ကို tile လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Simplify geometries to reduce output file size** (**Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို ရိုးရှင်းအောင်လုပ်ခြင်း**)
     - ``SIMPLIFY``
     - [boolean]

       Default: True
     - Output file အရွယ်အစားကိုလျော့ချရန် geometry များကို simplify (ရိုးရှင်းအောင်) လုပ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်
   * - **Text export** (**စာသား export ထုတ်ခြင်း**)
     - ``TEXT_FORMAT``
     - [enumeration]

       Default: 0
     - စာသားများကို လမ်းကြောင်း သို့မဟုတ် စာသား object များအဖြစ် ထုတ်သင့်/မသင့် ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Always export text as paths (recommended) (စာသားကို လမ်းကြောင်းများအဖြစ် အမြဲတမ်းထုတ်ခြင်း (အကြံပြုထားသော))
       * 1 - Always export texts as text objects (စာသားများကို စာသား object များအဖြစ် အမြဲတမ်းထုတ်ခြင်း)
   * - **Image compression** (**ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း**)
     - ``IMAGE_COMPRESSION``
     - [enumeration]

       Default: 0
     - ဓာတ်ပုံအရွယ်အစားချုံ့ခြင်း level နှင့် output များ print ထုတ်ခြင်း သို့မဟုတ် ပြင်ပ application များထဲတွင် နောက်ပိုင်းလုပ်ဆောင်မှုများအတွက် file သည် မည်မျှသင့်တော်နိုင်မည်ကို ဆုံးဖြတ်ပေးပါသည်။ ရရှိနိုင်သော ရွေးချယ်စရာများမှာ - 

       * 0 - Lossy (JPEG)
       * 1 - Lossless
   * - **Export layers as separate PDF files** (**Layer များကို သီးခြား PDF file များအဖြစ် ထုတ်ခြင်း**)
     - ``SEPARATE_LAYERS``
     - [boolean]

       Default: False
     - True ကိုထားလျှင် layout ထဲရှိ map item တစ်ခုချင်းစီ၏ layer တစ်ခုချင်းစီအတွက် သီးခြား PDF file တစ်ခုကို ဖန်တီးပေးပါလိမ့်မည်။ ထို့အပြင် အခြား ရှုပ်ထွေးသော layout item များအတွက် သီးခြား PDF file များကိုလည်း ဖန်တီးပေးနိုင်ပြီး layout ၏ သဘာဝကျသော atomic အစိတ်အပိုင်းများပါဝင်သော PDF file များကိုရရှိစေပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **PDF file**
     - ``OUTPUT``
     - [file]
     - Export ထုတ်လိုက်သော print layout နှင့်သက်ဆိုင်သည့် PDF file များ

Python code
............

**Algorithm ID**: ``native:printlayouttopdf``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractlabels:

Extract labels (အညွှန်းများ ဆွဲထုတ်ခြင်း)
------------------------------------------

သတ်မှတ်ထားသော extent နှင့် စကေးတွင် ပုံဖော်ပြသထားသော မြေပုံတစ်ခုမှ အညွှန်းအချက်အလက်များကို ဆွဲထုတ်ပေးပါသည်။

Map theme တစ်ခုရှိလျှင် ပုံဖော်ပြသထားသောမြေပုံကို ထို theme ၏ မြင်ရနိုင်စွမ်း (visibility) နှင့် သင်္ကေတဆိုင်ရာများနှင့်ယှဉ်တွဲပေးပါလိမ့်မည်။ ဗလာထားလျှင် project မှ မြင်နိုင်သော layer များအားလုံးကိုအသုံးပြုပါလိမ့်မည်။ ဆွဲထုတ်သော အညွှန်းအချက်အလက်များတွင် - တည်နေရာ (point geometry များအဖြစ်)၊ ဆက်စပ်သော layer အမည်နှင့် feature ID၊ အညွှန်းစာသား၊ လှည့်ထောင့် (ဒီဂရီဖြင့်၊ နာရီလက်တံပြောင်းပြန်)၊ မျဉ်းများစွာ အတန်းညီအောင် ညှိထားမှု နှင့် စာလုံးပုံစံဆိုင်ရာ အသေးစိတ်များ ပါရှိပါသည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map extent**
     - ``EXTENT``
     - [extent]
     - အညွှန်းများဆွဲထုတ်မည့် မြေပုံ၏ extent

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Map scale** (**မြေပုံစကေး**)
     - ``SCALE``
     - [scale]
     - ဆွဲထုတ်ထားသော အညွှန်းများကို ၎င်းတို့၏ လက်ရှိစကေးအတွင်းရှိ properties set အသုံးပြုပြီး ပုံဖော်ပြသပါမည်။
   * - **Map theme** (**မြေပုံ theme**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAP_THEME``
     - [maptheme]
     - အညွှန်းများဆွဲထုတ်မည့် layer များကို ပြသသည့် မြေပုံ theme တစ်ခု။ သတ်မှတ်မထားလျှင် လက်ရှိမြင်နေရသော layer များ၏အညွှန်းများကို ဆွဲထုတ်ပါသည်။
   * - **Include unplaced labels** (**နေရာချမထားသော အညွှန်းများ ပါဝင်စေခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INCLUDE_UNPLACED``
     - [boolean]

       Default: True
     - ထပ်နေသော အညွှန်းများအားလုံး (နေရာချမထားဘဲ ရှုပ်ထွေးအောင်ထပ်နေသော အညွှန်းများအပါအဝင်) ကိုဆွဲထုတ်သင့်/မသင့် သတ်မှတ်ပါ။ 
   * - **Extracted labels** (**ဆွဲထုတ်ထားသော အညွှန်းများ**)
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Extent (များ) အတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်နိုင်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map resolution (in DPI)** (**မြေပုံ ကြည်လင်ပြတ်သားမှု (DPI ဖြင့်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DPI``

       Default: 96.0
     - [number]
     -

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extracted labels** (**ဆွဲထုတ်ထားသော အညွှန်းများ**)
     - ``OUTPUT``
     - [vector: point]
     - ရယူထားသော အညွှန်းများကို ကိုယ်စားပြုသော point vector layer ။ Feature တစ်ခုချင်းစီတွင် ၎င်း၏ ရင်းမြစ် (layer၊ feature ID) ကို ခွဲခြားပေးသောအချက်အလက်များနှင့် သတ်မှတ်ထားသော အညွှန်း property များ (စာသား၊ စာလုံး၊ အရွယ်အစား၊ လှည့်ထောင့်၊ စသဖြင့်) ပါဝင်ပါသည်။ အညွှန်းတပ်ခြင်းအတွက် မူရင်း style နှင့် null symbol ကိုလည်း layer အတွက်အသုံးပြုပါသည်။

       .. warning:: အချို့သော ဖန်တီးထားသော field များသည် စာလုံးရေ ဆယ်လုံးထက်ပိုပါနေသောကြောင့် output များကိုသိမ်းဆည်းရန် ESRI shapefile format (:file:`.SHP`) ကိုအသုံးပြုခြင်းသည် layer ကို QGIS ထဲတွင်ထည့်သွင်းသောအခါ မမျှော်လင့်သော ပုံဖော်ပြသမှုများ ဖြစ်စေနိုင်ပါသည်။

Python code
............

**Algorithm ID**: ``native:extractlabels``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisprintlayoutmapextenttolayer:

Print layout map extent to layer (Layout မြေပုံနယ်ပယ်အကျယ်အဝန်းကို layer သို့ print ထုတ်ခြင်း)
-----------------------------------------------------------------------------------------------

မြေပုံ၏အရွယ်အစား (layout ယူနစ်ဖြင့်၊ :ref:`reference map <reference_map>` ကိုဆိုလိုပါသည်)၊ စကေးနှင့် လှည့်ထောင့် များကို သတ်မှတ်ပေးသော အချက်အလက်များဖြင့် print layout map item တစ်ခု၏ extent ပါဝင်သော polygon layer တစ်ခုကို ဖန်တီးပေးပါသည်။

Map item parameter ကိုသတ်မှတ်ထားလျှင် ကိုက်ညီသော မြေပုံ extent ကိုသာ ထုတ်ပေးမည်ဖြစ်ပါသည်။ သတ်မှတ်မထားလျှင် layout ရှိ မြေပုံ extent များအားလုံးကို ထုတ်ပေးမည်ဖြစ်ပါသည်။

Output CRS ကို အတိအကျသတ်မှတ်ပေးနိုင်ပါသည်။ သတ်မှတ်မပေးလျှင် မူရင်း မြေပုံ item CRS ကိုအသုံးပြုပါလိမ့်မည်။

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Print layout**
     - ``LAYOUT``
     - [enumeration]
     - လက်ရှိ project ထဲရှိ print layout တစ်ခု
   * - **Map item** (**မြေပုံ item**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAP``
     - [enumeration]

       Default: *All the map items (မြေပုံ item အားလုံး)* 
     - ဆွဲထုတ်လိုသော သတင်းအချက်အလက်များပါဝင်သော မြေပုံ item များ။ ဘာမှမပေးထားလျှင် မြေပုံ item အားလုံးကို လုပ်ဆောင်ပါသည်။
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Extent (များ) အတွက် output vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်နိုင်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overrride CRS** (**CRS ကို အစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS``
     - [crs]

       Default: *The layout CRS (Layout ၏ CRS)*
     - သတင်းအချက်အလက်များကို ဖော်ပြပေးမည့် layer အတွက် CRS ကိုရွေးချယ်ပါ။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Map height** (**မြေပုံအမြင့်**)
     - ``HEIGHT``
     - [number]
     - 
   * - **Extent** (**နယ်ပယ်အကျယ်အဝန်း**)
     - ``OUTPUT``
     - [vector: polygon]
     - Input layout map item (များ) ၏ extent များပါဝင်သော output polygon vector layer
   * - **Map rotation** (**မြေပုံလှည့်ခြင်း**)
     - ``ROTATION``
     - [number]
     - 
   * - **Map scale** (**မြေပုံ စကေး**)
     - ``SCALE``
     - [number]
     - 
   * - **Map width** (**မြေပုံအကျယ်**)
     - ``WIDTH``
     - [number]
     - 

Python code
............

**Algorithm ID**: ``native:printlayoutmapextenttolayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissetlayerstyle:

Set layer style (Layer style သတ်မှတ်ခြင်း)
-------------------------------------------

Layer တွင် ထောက်ပံ့ပေးထားသော style တစ်ခုအသုံးပြုပါသည်။ ၎င်း style ကို :file:`QML` file ဖြင့်သတ်မှတ်ရပါမည်။

Output အသစ်များဖန်တီးမပေးပါ - style ကို layer ဆီသို့ချက်ချင်းသတ်မှတ်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input Layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [layer]
     - Style အသုံးပြုလိုသော input layer
   * - **Style file**
     - ``STYLE``
     - [file]
     - Style ၏ ``.qml`` file သို့လမ်းကြောင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * -
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

     - သတ်မှတ်ထားသော style အသစ်ဖြင့် input layer ။ Layer အသစ်ကိုဖန်တီးမပေးပါ။

Python code
............

**Algorithm ID**: ``native:setlayerstyle``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistopologicalcoloring:

Topological coloring (Topology ဆိုင်ရာ အရောင်ခြယ်သခြင်း)
---------------------------------------------------------

လိုအပ်သာ အရောင်အရေအတွက်ကို အနည်းဆုံးဖြစ်အောင်လုပ်ဆောင်ပြီး ကပ်လျှက်ရှိသော polygon များသည် တူညီသောအရောင်အညွှန်းကို အသုံးမပြုစေသောနည်းဖြင့် polygon feature များကို အရောင်အညွှန်တစ်ခုသတ်မှတ်ပေးပါသည်။

အရောင်များသတ်မှတ်သောအခါ algorithm သည် အသုံးပြုမည့်နည်းလမ်းများ ရွေးချယ်နိုင်အောင် လုပ်ဆောင်ပေးပါသည်။

လိုအပ်လျှင် အနည်းဆုံး အရောင်အရေအတွက်ကို သတ်မှတ်ပေးနိုင်ပါသည်။ အရောင်အညွှန်း ကို **color_id** ဟုခေါ်သော attribute အသစ်တွင် သိမ်းဆည်းထားပေးပါသည်။

အောက်ပါဥပမာတွင် ရွေးချယ်ထားသော အရောင်လေးမျိုးဖြင့် algorithm ကိုပြသပေးပါသည်။ အရောင်အတန်းအစားတစ်ခုချင်းစီတွင် တူညီသော feature အရေအတွက် ရှိသည်ကို တွေ့မြင်နိုင်ပါသည်။

.. figure:: img/topological_color.png
  :align: center

  Topology ဆိုင်ရာ အရောင်များ ဥပမာ

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: polygon]
     - ထည့်သွင်းအသုံးပြုသော polygon layer
   * - **Minimum number of colors** (**အနည်းဆုံးအရောင်အရေအတွက်**)
     - ``MIN_COLORS``
     - [number]

       Default: 4
     - သတ်မှတ်ရန် အနည်းဆုံး အရောင်အရေအတွက်။ အနည်ဆုံး 1၊ အများဆုံး 1000။
   * - **Minimum distance between features** (**Featurer များကြား အနည်းဆုံးအကွာအဝေဂ**)
     - ``MIN_DISTANCE``
     - [number]

       Default: 0.0
     - အနီးနားမှ (မထိနေရပါ) feature များကို တူညီသောအရောင်များ သတ်မှတ်ခြင်းကို ကာကွယ်ပေးပါသည်။ အနည်းဆုံး 0.0။ 
   * - **Balance color assignment** (**မျှခြေအရောင်သတ်မှတ်ခြင်း**)
     - ``BALANCE``
     - [enumeration]

       Default: 0
     - ရွေးချယ်စရာများမှာ -

       * 0 --- By feature count (Feature အရေအတွက်အားဖြင့်)
         
		     အရောင် index တစ်ခုချင်းစီကိုသတ်မှတ်သော feature အရေအတွက်များကို မျှတစေရန် အရောင်များသတ်မှတ်စေပါသည်။ 
         
       * 1 --- By assigned area (သတ်မှတ်ထားသော ဧရိယာဖြင့်)
         
		     အရောင်တစ်ခုချင်းစီကို သတ်မှတ်သော feature များ၏ စုစုပေါင်း ဧရိယာ မျှတစေရန် အရောင်များ သတ်မှတ်ပေးပါသည်။ မြေပုံတစ်ခုကို အရောင်ခြယ်သောအခါ အရောင်တစ်ခုတည်းက ထင်ထင်ရှားရှားဖြင့် ဧရိယာအကြီးကြီး ပြသနေခြင်းကို ရှောင်ရှားရန် ဒီနည်းလမ်းသည် အသုံးဝင်ပါသည်။
         
       * 2 --- By distance between colors (အရောင်များကြား အကွာအဝေးဖြင့်)
         
		     အရောင်တူတူဖြစ်နေသော feature များကြား အကွာအဝေးကို အများဆုံးဖြစ်စေရန် အရောင်များသတ်မှတ်ပေးပါသည်။ မြေပုံတစ်ခွင်လုံးအတွက် အရောင်များ ညီညီညာညာ ပြန့်နှံ့စေရန်အတွက် ဒီနည်းလမ်းသည် အသုံးဝင်ပါသည်။

   * - **Colored** (**အရောင်ခြယ်ထားသော**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Create temporary layer] ([ယာယီ layer ဖန်တီးခြင်း])``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Colored** (**အရောင်ခြယ်ထားသော**)
     - ``OUTPUT``
     - [vector: polygon]
     - ပေါင်းထည့်ထားသော ``color_id`` column တစ်ခုပါဝင်သော polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:topologicalcoloring``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistransferannotationsfrommain:

Transfer annotations from main layer (အဓိက layer မှ မှတ်ချက်/မှတ်စာ များကိုရွှေ့ပြောင်းခြင်း)
----------------------------------------------------------------------------------------------

Project တစ်ခုထဲရှိ အဓိက annotation (မှတ်ချက်/မှတ်စာ) layer မှ :ref:`annotations <annotation_layer>` များအားလုံးကို annotation layer အသစ်တစ်ခုသို့ ရွှေ့ပြောင်းပေးပါသည်။ Layer အထပ် (Layer stack) ထဲတွင် item များနေရာချထားမှုကို ချိန်ညှိရွှေ့ပြောင်းနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **New layer name** (**Layer အသစ်အမည်**)
     - ``LAYER_NAME``
     - [string]

       Default: 'Annotations'
     - ဖန်တီးမည့် annotations layer ၏ အမည်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **New layer name** (**Layer အသစ်အမည်**)
     - ``OUTPUT``
     - [layer]
     - အဓိက annotation layer မှ item များပါဝင်သော layer တစ်ခု

Python code
............

**Algorithm ID**: ``native:transferannotationsfrommain``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
