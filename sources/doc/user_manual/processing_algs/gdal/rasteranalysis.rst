Raster analysis (Raster များဆန်းစစ်လေ့လာခြင်း)
===============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc-columns


.. _gdalaspect:

Aspect (မျက်နှာမူရာအရပ်)
-------------------------

GDAL လုပ်ဆောင်ပေးနိုင်သော မည်သည့် မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster ပုံမှမဆို aspect map (မျက်နှာမူရာအရပ်ပြမြေပုံ) တစ်ခုထုတ်ယူဖန်တီးပေးပါသည်။ Aspect ဆိုသည်မှာ slope (လျောစောက်) တစ်ခုမျက်နှာလှည့်ထားသော သံလိုက်အိမ်မြှောင်၏ ဦးတည်ရာဖြစ်ပါသည်။ Pixel များသည် မြောက်ဘက်မှ azimuth ဘက်ကို ညွှန်ပြနေသော ဒီဂရီတန်ဖိုး 0-360° ကြားတွင် ရှိပါလိမ့်မည်။ ကမ္ဘာ့မြောက်ဘက်ခြမ်းတွင် slope များသည် မကြာခဏဆိုသလို အရိပ်များပါနေတတ်ပြီး (azimuth တန်ဖိုးနည်းသော 0°-90° ထိ) တောင်ဘက်ခြမ်းတွင် နေရောင်ဖြာကျမှု ပိုများပါသည် (azimuth တန်ဖိုးပိုများသော 180°-270° ထိ)။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာပြင်အနိမ့်အမြင့် အဖြစ်အသုံးပြုမည့် band နံပါတ်
   * - **Return trigonometric angle instead of azimuth** (**Azimuth အစား trigonometric ထောင့်ကို ပြန်ထုတ်ပေးပါ**)
     - ``TRIG_ANGLE``
     - [boolean]

       Default: False
     - Trigonometric ထောင့် ကိုဖွင့်ပြီးအသုံးပြုချင်းသည် ကဏ္ဍအမျိုးမျိုးထွက်လာစေပါသည် - 0° (အရှေ့) ၊ 90° (မြောက်) ၊ 180° (အနောက်) ၊ 270° (တောင်)
   * - **Return 0 for flat instead of -9999** (**-9999 အစား 0 ကိုပြန်ထုတ်ပေးပါ**)
     - ``ZERO_FLAT``
     - [boolean]

       Default: False
     - ဒီ option ကိုဖွင့်ထားလျှင် မြေပြန့်ဖြစ်နေသော ဧရိယာများပေါ်ရှိ -9999 တန်ဖိုးအတွက် 0 တန်ဖိုးကို အစားထိုးပေးပါသည်
   * - **Compute edges** (**ထောင့်စွန်းများကိုတွက်ထုတ်ပါ**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster မှ edge (ထောင့်စွန်းများ) များကိုထုတ်ပေးပါသည်။
   * - **Use Zevenbergen&Thorne formula instead of the Horn's one** (**Horm formula အစား Zevenbergen&Thorne formula ကိုအသုံးပြုပါ**)
     - ``ZEVENBERGEN``
     - [boolean]

       Default: False
     - ချောမွေ့သော မျက်နှာပြင်များအတွက် Zevenbergen&Thorne formula ကိုဖွင့်ထားပြီးအသုံးပြုပါ
   * - **Aspect**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - Output raster layer သည် အောက်ပါတို့ထဲမှ တစ်ခုခု ဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile များကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုလိုက်လုပ်ဆောင်ခြင်း (Batch process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Aspect**
     - ``OUTPUT``
     - [raster]
     - ဒီဂရီထောင့်တန်ဖိုးများဖြင့် output raster

Python code
............

**Algorithm ID**: ``gdal:aspect``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalcolorrelief:

Color relief (အရောင်ဖြင့် အနိမ့်အမြင့်ထင်ရှားမှု)
--------------------------------------------------

GDAL လုပ်ဆောင်ပေးနိင်သော မည်သည့် မြေမျက်နှာပြင်အနိမ့်အမြင့် raster မှမဆို color relief map (အရောင်ဖြင့် အနိမ့်အမြင့်ထင်ရှားမှုမြေပုံ) တစ်ခုကို ဖန်တီးပေးပါသည်။ Color relief မြေပုံများကို မြေမျက်နှာပြင်အနိမ့်အမြင့်ကို ဖော်ပြရန်အတွက် အသုံးပြုကြပါသည်။ Algorithm သည် မြေမျက်နှာပြင်အနိမ့်အမြင့် နှင့် စာသားအခြေခံ အရောင်ပြင်ဆင်ခြင်း file များမှ တွက်ထုတ်ထားသော တန်ဖိုးများဖြင့် band လေးခုပါသော raster ကို ဖန်တီးပေးပါသည်။ သာမန်အားဖြင့် အသုံးပြုထားသော အမြင့်တန်ဖိုးများအတွင်း အရောင်များကိုရောနှောအသုံးပြုပြီး လှပသော ရောင်စုံ အနိမ့်အမြင့်ပြ မြေပုံတစ်ခုကို ရရှိစေပါသည်။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

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
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာပြင်အနိမ့်အမြင့် အဖြစ်အသုံးပြုမည့် band နံပါတ်
   * - **Compute edges** (**Edge များကိုတွက်ထုတ်ပါ**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့် raster မှ edge များကိုတွက်ထုတ်ပေးပါသည်။
   * - **Color configuration file** (**အရောင်ပြင်ဆင်သတ်မှတ်ခြင်း file**)
     - ``COLOR_TABLE``
     - [file]
     - စာသားအခြေခံ အရောင်ပြင်ဆင်သတ်မှတ်ခြင်း file
   * - **Matching mode** (**ယှဉ်တွဲခြင်း mode**)
     - ``MATCH_MODE``
     - [enumeration]

       Default: 2
     - အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

	     * 0 --- အတိအကျ တူသောအရောင်ကို အသုံးပြုပါ
	     * 1 --- အနီးစပ်ဆုံး RGBA quadruples ကိုအသုံးပြုပါ
	     * 2 --- ပြေပြစ်စွာရောနှောထားသော အရောင်များကို အသုံးပြုပါ

   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - [string]
     - ``OPTIONS``

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - အခြား GDAL command line ရွေးချယ်စရာများကို ပေါင်းထည့်ခြင်း
   * - **Color relief**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])`` 
     - ထွက်လာမည့် raster layer မှာ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Color relief**
     - ``OUTPUT``
     - [raster]
     - Band လေးခုပါသော output raster တစ်ခု

Python code
............

**Algorithm ID**: ``gdal:colorrelief``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalfillnodata:

Fill nodata (Nodata များကို ဖြည့်သွင်းခြင်း)
---------------------------------------------

No data တန်ဖိုးများပါရှိနေသော raster နယ်ပယ်များကို Edge များမှ အလိုအလျှောက်တွက်ထုတ်ခြင်းအားဖြင့် ဖြည့်ပေးပါသည်။ Inverse distance weighting (IDW) နည်းလမ်းကို အသုံးပြုပြီး ပတ်ဝန်းကျင်မှ pixel တန်ဖိုးများဖြင့် no-data region များအတွက် တန်ဖိုးများကို တွက်ထုတ်ပါသည်။ အလိုအလျှောက်တွက်ထုတ်ပြီးသောအခါ ရလာဒ်များကို ချောမွေ့အောင် လုပ်ဆောင်ပေးပါသည်။ Input သည် GDAL ကိုအသုံးပြုနိုင်သော မည်သည့် raster layer မဆို ဖြစ်နိုင်ပါသည်။ ၎င်း algorithm သည် သင့်တင့်စွာဆက်တိုက်ပြောင်းလဲနေသော raster များ၏ လွတ်နေတာ region များကို အလိုအလျှောက်တွက်ထုတ်ခြင်းအတွက် သင့်တော်ပါသည် (ဥပမာ- မြေမျက်နှာပြင် အနိမ့်အမြင့် model များ)။ ပုံမှန်မဟုတ်ပဲ ပြောင်းလဲနေသော ဓာတ်ပုံများထဲမှာ အပေါက်အသေးလေးများနှင့် အက်ကြောင်းများကို ဖြည့်ရန်အတွက်လည်း သင့်တော်ပါသည် (ဥပမာ- ကောင်းကင်ဓာတ်ပုံများ)။ Point ကျဲပါးသော data မှ raster ကိုအလိုအလျှောက်တွက်ထုတ်ခြင်းအတွက် များစွာ ကောင်းမွန်မည်မဟုတ်ပါ။

Algorithm ကို `GDAL fillnodata utility <https://gdal.org/programs/gdal_fillnodata.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - အလုပ်လုပ်ဆောင်မည့် band။ Nodata တန်ဖိုးများကို 0 ဖြင့် ကိုယ်စားပြုရပါမည်။
   * - **Maximum distance (in pixels) to search out for values to interpolate** **(အလိုအလျှောက်တွက်ထုတ်ရန်အတွက် တန်ဖိုးများကို ရှာမည့် အများဆုံးအကွာအဝေး (pixel ဖြင့်)**
     - ``DISTANCE``
     - [number]

       Default: 10
     - အလိုအလျှောက်တွက်ထုတ်ရန်အတွက် တန်ဖိုးများကိုရှာရန် အရပ်မျက်နှာအားလုံးတွင် ရှာဖွေမည့် pixel အရေအတွက်
   * - **Number of smoothing iterations to run after the interpolation** (**အလိုအလျှောက်တွက်ထုတ်ပြီးနောက် လုပ်ဆောင်မည့် အချောသတ်ခြင်း အရေအတွက်**)
     - ``ITERATIONS``
     - [number]

       Default: 0
     - အလိုအလျှောက်တွက်ထုတ်ခြင်း၏ ရလာဒ်များကို ချောမွေ့အောင် လုပ်ဆောင်သည့် 3x3 စစ်ထုတ်မှု၏ အရေအတွက်
   * - **Do not use default validity mask for the input band** (**ထည့်သွင်းအသုံးပြုသော band များအတွက် မူရင်း validity mask ကိုအသုံးမပြုခြင်း**)
     - ``NO_MASK``
     - [boolean]

       Default: False
     - အသုံးပြုသူ သတ်မှတ်ထားသော validity mask ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပါ
   * - **Validity mask**
     - ``MASK_LAYER``
     - [raster]
     - ဖြည့်ရမည့် area ကို သတ်မှတ်သည့် raster layer
   * - **Filled**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - ထွက်လာမည့် raster layer ၏ သီးခြားသတ်မှတ်ချက်မှာ အောက်ပါတို့မှ တစ်ခုခု ဖြစ်ပါမည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - GDAL command line ရွေးချယ်စရာ အပိုများကို ပေါင်းထည့်ခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Filled** (**ဖြည့်သွင်းထားပြီးသော**)
     - ``OUTPUT``
     - [raster]
     - Output raster

Python code
............

**Algorithm ID**: ``gdal:fillnodata``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgriddatametrics:

Grid (Data metrics)
--------------------

သတ်မှတ်ထားသော window နှင့် output grid ဂျီဩမေတြီ များကိုအသုံးပြုပြီး data metrics အချို့ကို တွက်ထုတ်ပေးပါသည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

.. seealso:: `GDAL grid tutorial <https://gdal.org/tutorials/gdal_grid_tut.html>`_

Parameter များ
...............

Basic parameters (အခြေခံ parameter များ )
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point layer**
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Data metric to use** (**အသုံးပြုမည့် Data Metric**)
     - ``METRIC``
     - [enumeration]

       Default: 0
     - အောက်ပါတို့ထဲမှ တစ်ခု-

       * 0 --- အနည်းဆုံး၊ grid node search ellipse ထဲတွင် တွေ့ရသော အနည်းဆုံးတန်ဖိုး
       * 1 --- အများဆုံး၊ grid node search ellipse ထဲတွင် တွေ့ရသော အများဆုံးတန်ဖိုး
       * 2 --- အပိုင်းအခြား၊ grid node search ellipse ထဲတွင် တွေ့ရသော အနည်းဆုံးနှင့် အများဆုံးတန်ဖိုးများအကြား ခြားနားမှု
       * 3 --- အရေအတွက်၊ grid node search ellipse ထဲတွင်တွေ့ရသော data point အရေအတွက်
       * 4 --- ပျမ်းမျှ အကွာအဝေး၊ grid node search ellipse ထဲတွင်တွေ့ရသော grid node (search ellipse ၏ ဗဟို) နှင့် data point များအားလုံးအကြားက ပျမ်းမျှအကွာအဝေး
       * 5 --- အမှတ်များအကြား ပျမ်းမျှအကွာအဝေး၊ grid node search ellipse ထဲတွင်တွေ့ရသော data point များအကြား ပျမ်းမျှအကွာအဝေး။ Ellipse ထဲရှိ အမှတ်နှစ်ခုအကြား အကွာအဝေးကို တွက်ထုတ်ပြီး အကွာအဝေးအားလုံး၏ ပျမ်းမျှကို grid node တန်ဖိုးအဖြစ် သတ်မှတ်ပါသည်။

   * - **The first radius of search ellipse** (**Search ellipse ၏ ပထမ radius**)
     - ``RADIUS_1``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ပထမ radius (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် X ဝင်ရိုးဖြစ်ပါသည်)
   * - **The second radius of search ellipse** (**Search ellipse ၏ ဒုတိယ radius**)
     - ``RADIUS_2``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ဒုတိယ radius (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် Y ဝင်ရိုးဖြစ်ပါသည်)
   * - **Angle of search ellipse rotation in degrees (counter clockwise)** (**ဒီဂရီဖြင့် search ellipse လှည့်ပတ်မှုထောင့် (နာရီလက်တံပြောင်းပြန်)**)
     - ``ANGLE``
     - [number]

       Default: 0.0
     - Ellipse လည့်ပတ်မှုထောင့် (ဒီဂရီဖြင့်)။ နာရီလက်တံပြောင်းပြန်လှည့်သော ellipse။
   * - **Minimum number of data points to use** (**အသုံးပြုမည့် data point အနည်းဆုံးအရေအတွက်**)
     - ``MIN_POINTS``
     - [number]

       Default: 0.0
     - ပျမ်းမျှခြင်းပြုလုပ်ရန် အနည်းဆုံး Data point အရေအတွက်။ Grid node ထဲတွင် ထို point အရေအတွက် ထက်လျော့နည်းနေလျှင် ဗလာ (empty) ဟု ယူဆပြီး NODATA maker ဖြင့် ဖြည့်ပါမည်။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်သွင်းရန် No data အမှတ်အသားများ
   * - **Interpolated (data metrics)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ချက်ထားသော (data metrics)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော output raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**Column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းအတွက် column
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။  အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ပေါင်းထည့်ခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated (data metrics)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ပေးသော data metrics**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများဖြင့် output raster

Python code
............

**Algorithm ID**: ``gdal:griddatametrics``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgridinversedistancenearestneighbor:

Grid (IDW with nearest neighbor searching)
-------------------------------------------

Nearest neighbor နည်းလမ်းကို ပေါင်းစပ်ထားသော Power gridding တစ်ခုသို့ Inverse Distance ကို တွက်ချက်ပေးပါသည်။ Data point အများဆုံးအရေအတွက်ကို အသုံးပြုရန် လိုအပ်သောအခါ အသုံးပြုရန် ဖြစ်ပါသည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှ ရယူပါသည်။

.. seealso:: `GDAL grid tutorial <https://gdal.org/tutorials/gdal_grid_tut.html>`_

Parameter များ
...............

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point layer** (**အမှတ် layer**)
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Weighting power** (**အလေးပေးမှုအား**)
     - ``POWER``
     - [number]

       Default: 2.0
     - အလေးပေးမှုအား
   * - **Smoothing** (**ချောမွေ့အောင်လုပ်ခြင်း**)
     - ``SMOOTHING``
     - [number]

       Default: 0.0
     - ချော့မွေ့အောင်လုပ်ဆောင်ပေးသော parameter
   * - **The radius of the search circle** (**ရှာဖွေသောစက်ဝိုင်း၏ အချင်းဝက်**)
     - ``RADIUS``
     - [number]

       Default: 1.0
     - ရှာဖွေသောစက်ဝိုင်း၏ အချင်းဝက်
   * - **Maximum number of data points to use** (**အသုံးပြုမည့် data point အများဆုံးအရေအတွက်**)
     - ``MAX_POINTS``
     - [number]

       Default: 12
     - ၎င်းအရေအတွက်ထက် ပိုများသော point များကိုမရှာပါနှင့်။
   * - **Minimum number of data points to use** (**အသုံးပြုမည့် data point အနည်းဆုံးအရေအတွက်**)
     - ``MIN_POINTS``
     - [number]

       Default: 0
     - ပျမ်းမျှခြင်းပြုလုပ်ရန် အနည်းဆုံး data points အရေအတွက်။ ထိုပမာဏထက်နည်းသော point များဖြစ်လျှင် grid node ကို ဗလာ (empty) အနေဖြင့် မှတ်ယူမည်ဖြစ်ပြီး NODATA အမှတ်အသား ဖြင့် ဖြည့်မည်ဖြစ်သည်။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်ရန် No data အမှတ်အသား။
   * - **Interpolated (IDW with NN search)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (NN search ဖြင့် IDW)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါသည်])``
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများဖြင့် ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းအတွက် column
   * - **Additional creation options**  (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။  အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
	   
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပါ။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (NN search ဖြင့် IDW)**
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသောတန်ဖိုးများဖြင့် ရလာဒ် raster

Python code
............

**Algorithm ID**: ``gdal:gridinversedistancenearestneighbor``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgridinversedistance:

Grid (Inverse distance to a power)
-----------------------------------

Inverse Distance to a Power gridding နည်းလမ်းသည် ပျမ်းမျှအလေးပေး interpolator တစ်ခုဖြစ်ပါသည်။

Data point တိုင်း၏ တည်နေရာတန်ဖိုးများနှင့် output grid ဂျီဩမေတြီ များပါဝင်သော ပြန့်ကျဲနေသော data တန်ဖိုးများဖြင့် input array များကို ထည့်သွင်းပေးရပါမည်။ Output grid ထဲတွင် ထည့်သွင်းပေးထားသော တည်နေရာအတွက် အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်သောတန်ဖိုးကို ယခု function မှတွက်ချက်ပေးပါလိမ့်မည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

.. seealso:: `GDAL grid tutorial <https://gdal.org/tutorials/gdal_grid_tut.html>`_


Parameter များ
...............

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
   * - **Point layer** (**အမှတ် layer**)
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Weighting power** (**အလေးပေးမှုအား**)
     - ``POWER``
     - [number]

       Default: 2.0
     - အလေးပေးမှုအား
   * - **Smothing** (**ချောမွေ့အောင်လုပ်ခြင်း**)
     - ``SMOOTHING``
     - [number]

       Default: 0.0
     - ချောမွေ့အောင်လုပ်ပေးသော parameter
   * - **The first radius of search ellipse** (**Search ellipse ၏ ပထမ အချင်းဝက်**)
     - ``RADIUS_1``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ပထမ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် X ဝင်ရိုးဖြစ်သည်)
   * - **The second radius of search ellipse** (**Search ellipse ၏ ဒုတိယ အချင်းဝက်**)
     - ``RADIUS_2``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ဒုတိယ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် Y ဝင်ရိုးဖြစ်သည်)
   * - **Angle of search ellipse rotation in degrees (counter clockwise)** (**ဒီဂရီဖြင့် search ellipse လှည့်ပတ်မှုထောင့် (နာရီလက်တံပြောင်းပြန်)**)
     - ``ANGLE``
     - [number]

       Default: 0.0
     - ဒီဂရီဖြင့် ellipse လှည့်ပတ်မှုထောင့်။ နာရီလက်တံပြောင်းပြန်လှည့်သော ellipse။
   * - **Maximum number of data points to use** (**အသုံးပြုမည့် data point အများဆုံးအရေအတွက်**)
     - ``MAX_POINTS``
     - [number]

       Default: 0
     - ၎င်းအရေအတွက်ထက် ပိုသော point များကိုမရှာပါ
   * - **Minimum number of data points to use** (**အသုံးပြုမည့် data point အနည်းဆုံးအရေအတွက်**)
     - ``MIN_POINTS``
     - [number]

       Default: 0
     - ပျမ်းမျှခြင်းပြုလုပ်ရန် အသုံးပြုမည့် အနည်းဆုံး data point အရေအတွက်။ ထိုပမာဏထက်နည်းသော point များဖြစ်လျှင် grid node ကို ဗလာ (empty) အနေဖြင့် မှတ်ယူမည်ဖြစ်ပြီး NODATA အမှတ်အသား ဖြင့် ဖြည့်မည်ဖြစ်သည်။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်သွင်းရန် No data အမှတ်အသားများ
   * - **Interpolated (IDW)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (IDW)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file]`` (``[ယာယီ file အဖြစ်သိမ်းဆည်းပါသည်]``)
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော ရလာဒ် raster ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**Column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်း (interpolation) အတွက် column
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block  အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပါ။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated (IDW)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (IDW)**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသောတန်ဖိုးများဖြင့် ရလာဒ် raster

Python code
............

**Algorithm ID**: ``gdal:gridinversedistance``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgridlinear:

Grid (Linear)
--------------

Linear (အဖြောင့်) နည်းလမ်းသည် point cloud ၏ Delaunay traingulation (တြိဂံဖွဲ့တိုင်းတာခြင်း) နည်းလမ်းဖြင့် တွက်ချက်ပြီး linear အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းကို လုပ်ဆောင်ပါသည်။ Triangulation ၏ မည်သည့်တြိဂံထဲတွင် အမှတ်ရှိနေလဲဆိုသည်ကို ရှာဖွေပြီး တြိဂံအတွင်းရှိ barycentric ကိုဩဒိနိတ်များမှ linear အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းကို လုပ်ဆောင်ပါသည်။ အမှတ်သည် မည်သည့် တြိဂံအတွင်းတွင်မှ မရှိနေလျှင် အချင်းဝက်ပေါ်မူတည်ပြီး algorithm သည် အနီးဆုံးအမှတ်၏ တန်ဖိုး သို့မဟုတ် NODATA တန်ဖိုးကို အသုံးပြုပါလိမ့်မည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှရယူပါသည်။

Parameter များ
...............

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
   * - **Point layer** (**အမှတ် layer**)
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **Search distance** (**ရှာဖွေမှု အကွာအဝေး**)
     - ``RADIUS``
     - [number]

       Default: -1.0
     - အကယ်၍ အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်း အတွက်အသုံးပြုမည့် အမှတ်သည် Delaunay triangulation ၏ တြိဂံထဲတွင် အံဝင်ဂွင်ကျမဖြစ်လျှင် အနီးဆုံး neighbour တစ်ခုကိုရှာဖွေရန် ထိုအများဆုံးရှာဖွေမှုအကွာအဝေးကို အသုံးပြုပါမည် သို့မဟုတ် nodata ကိုအသုံးပြုပါမည်။ ``-1`` အဖြစ်သတ်မှတ်လျှင် ရှာဖွေသောအကွာအဝေးမှာ အကန့်အသတ်မဲ့ ဖြစ်သွားပါသည်။ ``0`` အဖြစ်သတ်မှတ်လျှင် no data တန်ဖိုးကို အသုံးပြုပါမည်။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်သွင်းရန် No data အမှတ်အသားများ
   * - **Interpolated (Linear)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (Linear)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါသည်]``)
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော ရလာဒ် raster ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**Column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းအတွက် column
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကိုသတ်မှတ်ပါ။ ရွေးချယ်စရာနည်းလမ်းများမှာ - 

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated (Linear)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (Linear)**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော output raster

Python code
............

**Algorithm ID**: ``gdal:gridlinear``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgridaverage:

Grid (Moving average)
----------------------

Moving Average သည် ရိုးရှင်းသော data ကိုပျမ်းမျှခြင်း လုပ်ဆောင်ပေးသည့် algorithm ဖြစ်ပါသည်။ ၎င်းသည် တန်ဖိုးများကိုရှာဖွေရန် elliptic form ၏ ရွေ့လျှားနေသော window တစ်ခုကိုအသုံးပြုပြီး window အတွင်းရှိ data point များအားလုံးကို ပျမ်းမျှခြင်း ပြုလုပ်ပေးပါသည်။ သတ်မှတ်ထောင့်တစ်ခုဖြင့် search ellipse ကိုလှည့်နိုင်ပြီး ellipse ၏ ဗဟိုသည် grid node တွင်တည်ရှိပါသည်။ ပျမ်းမျှပြုလုပ်ရန် အသုံးပြုမည့် အနည်းဆုံး data points အရေအတွက်ကို သတ်မှတ်ပေးနိုင်ပြီး window ထဲတွင် လုံလောက်သော point များမရှိလျှင် grid node ကို ဗလာ (empty) အနေဖြင့် မှတ်ယူမည်ဖြစ်ပြီး NODATA အမှတ်အသား ဖြင့် ဖြည့်မည်ဖြစ်သည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

.. seealso:: `GDAL grid tutorial <https://gdal.org/tutorials/gdal_grid_tut.html>`_

Parameter များ
...............

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
   * - **Point layer** (**အမှတ် layer**)
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **The first radius of search ellipse** (**Search ellipse ၏ ပထမ အချင်းဝက်**)
     - ``RADIUS_1``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ပထမ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် X ဝင်ရိုးဖြစ်သည်)
   * - **The second radius of search ellipse** (**Search ellipse ၏ ဒုတိယ အချင်းဝက်**)
     - ``RADIUS_2``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ဒုတိယ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် Y ဝင်ရိုးဖြစ်သည်)
   * - **Angle of search ellipse rotation in degrees (counter clockwise)** (**ဒီဂရီဖြင့် search ellipse လှည့်ပတ်မှုထောင့် (နာရီလက်တံပြောင်းပြန်)**)
     - ``ANGLE``
     - [number]

       Default: 0.0
     - ဒီဂရီဖြင့် ellipse လှည့်ပတ်မှုထောင့်။ နာရီလက်တံပြောင်းပြန်လှည့်သော ellipse။
   * - **Minimum number of data points to use** (**အသုံးပြုမည့် data point အနည်းဆုံးအရေတွက်**)
     - ``MIN_POINTS``
     - [number]

       Default: 0
     - ပျမ်းမျှခြင်းပြုလုပ်ရန် အသုံးပြုမည့် အနည်းဆုံး data point အရေအတွက်။ ထိုပမာဏထက်နည်းသော point များဖြစ်လျှင် grid node ကို ဗလာ (empty) အနေဖြင့် မှတ်ယူမည်ဖြစ်ပြီး NODATA အမှတ်အသား ဖြင့် ဖြည့်မည်ဖြစ်သည်။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်သွင်းရန် No data အမှတ်အသားများ
   * - **Interpolated (moving average)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (moving average)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file]`` (``[ယာယီ file အဖြစ်သိမ်းဆည်းပါသည်]``)
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော ရလာဒ် raster ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -
 
       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**Column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းအတွက် column
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကိုသတ်မှတ်ပါ။ ရွေးချယ်စရာနည်းလမ်းများမှာ - 

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated (moving average)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (moving average)**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော output raster

Python code
............

**Algorithm ID**: ``gdal:gridaverage``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgridnearestneighbor:

Grid (Nearest neighbour)
-------------------------

Nearest Neighbour နည်းလမ်းသည် မည်သည့် အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်း သို့မဟုတ် ချော့မွေ့ခြင်းကို လုပ်ဆောင်မပေးပါ၊ Grid node search ellipse ထဲတွင်တွေ့ရသော အနီးဆုံး point ၏ တန်ဖိုးကိုယူပြီး ၎င်းကို ရလာဒ်အဖြစ်ပြန်ထုတ်ပေးပါသည်။ မည်သည့် point မှမတွေ့လျှင် သတ်မှတ်ထားသော NODATA တန်ဖိုးကို ပြန်ထုတ်ပေးပါသည်။

Algorithm ကို `GDAL grid utility <https://gdal.org/programs/gdal_grid.html>`_ မှရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

.. seealso:: `GDAL grid tutorial <https://gdal.org/tutorials/gdal_grid_tut.html>`_

Parameter များ
...............

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
   * - **Point layer** (**အမှတ် layer**)
     - ``INPUT``
     - [vector: point]
     - ထည့်သွင်းအသုံးပြုသော point vector layer
   * - **The first radius of search ellipse** (**Search ellipse ၏ ပထမ အချင်းဝက်**)
     - ``RADIUS_1``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ပထမ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် X ဝင်ရိုးဖြစ်သည်)
   * - **The second radius of search ellipse** (**Search ellipse ၏ ဒုတိယ အချင်းဝက်**)
     - ``RADIUS_2``
     - [number]

       Default: 0.0
     - Search ellipse ၏ ဒုတိယ အချင်းဝက် (လှည့်ထောင့်မှာ 0 ဖြစ်လျှင် Y ဝင်ရိုးဖြစ်သည်)
   * - **Angle of search ellipse rotation in degrees (counter clockwise)** (**ဒီဂရီဖြင့် search ellipse လှည့်ပတ်မှုထောင့် (နာရီလက်တံပြောင်းပြန်)**)
     - ``ANGLE``
     - [number]

       Default: 0.0
     - ဒီဂရီဖြင့် ellipse လှည့်ပတ်မှုထောင့်။ နာရီလက်တံပြောင်းပြန်လှည့်သော ellipse။
   * - **Nodata**
     - ``NODATA``
     - [number]

       Default: 0.0
     - ဗလာ point များကို ဖြည့်သွင်းရန် No data အမှတ်အသားများ
   * - **Interpolated (Nearest neighbour)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (Nearest neighbour)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file]`` (``[ယာယီ file အဖြစ်သိမ်းဆည်းပါသည်]``)
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော ရလာဒ် raster ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -
 
       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Z value from field** (**Column မှ အမြင့် Z တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Z_FIELD``
     - [tablefield: numeric]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ခြင်းအတွက် column
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကိုသတ်မှတ်ပါ။ ရွေးချယ်စရာနည်းလမ်းများမှာ - 

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated (Nearest neighbour)** (**အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော (Nearest neighbour)**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော output raster

Python code
............

**Algorithm ID**: ``gdal:gridnearestneighbor``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalhillshade:

Hillshade (တောင်အရိပ်)
-----------------------

အရိပ်ပုံသဏ္ဍာန်များပါသော raster တစ်ခုကိုထုတ်ပေးပါသည်။ မြေမျက်နှာသွင်ပြင်ကို မြင်သာအောင်ပြရန်အတွက် အလွန်အသုံးဝင်ပါသည်။ ဒေါင်လိုက်နှင့် အလျားလိုက် ဖြစ်နေသော ယူနစ်များအကြား ကွာခြားမှုများအတွက်မြင်သာစေရန် Azimuth နှင့် အလင်းရောင်ထိုးပေးသောအမြင့်၊ ဒေါင်လိုက် ချဲ့ကား (exaggeration) factor တစ်ခုနှင့် စကေးချိန်ညှိ (scaling) factor တစ်ခုတို့ကို သတ်မှတ်ပေးနိုင်ပါသည်။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့် raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်နှင့်ပတ်သက်သော အချက်အလက်များပါဝင်သည့် band
   * - **Z factor (vertical exaggeration)** (**Z factor (ဒေါင်လိုက် ချဲ့ကားခြင်း)**)
     - ``Z_FACTOR``
     - [number]

       Default: 1.0
     - Factor သည် ရလာဒ် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ပြ raster ၏ အမြင့်ကို ဆတိုး ချဲ့ကားပေးပါသည်။
   * - **Scale (ratio of vert. units to horiz.)**
     - ``SCALE``
     - [number]

       Default: 1.0
     - ဒေါင်လိုက် ယူနစ်များနှင့် အလျားလိုက်ယူနစ်များ၏ အချိုး
   * - **Azimuth of the light** (**အလင်းထိုးပေးရာအရပ်**)
     - ``AZIMUTH``
     - [number]

       Default: 315.0
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ပြ raster ပေါ်မှာကျရောက်သော အလင်းထိုးရာအရပ်ကို ဒီဂရီဖြင့် သတ်မှတ်ပေးပါသည်။ Raster ၏အပေါ်ထိပ်တည့်တည့်မှ လာလျှင် တန်ဖိုးသည် 0 ဖြစ်ပြီး အရှေ့ဘက်မှ လာလျှင် 90 ဖြစ်ပါသည်။
   * - **Altitude of the light** (**အလင်း၏အမြင့်**)
     - ``ALTITUDE``
     - [number]

       Default: 45.0
     - အလင်း၏အမြင့်ကို ဒီဂရီဖြင့် သတ်မှတ်ပါ။ အလင်းသည် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster ၏ အပေါ်ဘက်မှ လာလျှင် 90 ဖြစ်ပြီး မျက်နှာပြင်ကို ကပ်ပြီးထိုးလျှင် 0 ဖြစ်ပါသည်။
   * - **Compute edges** (**Edge များကို တွက်ချက်ခြင်း**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster မှ edge များကို ထုတ်ပေးပါသည်။
   * - **Use Zevenbergen&Thorne formula (instead of the Horn's one)** (**Horn formula အစား Zevenbergen&Thorne formula ကိုအသုံးပြုပါ**)
     - ``ZEVENBERGEN``
     - [boolean]

       Default: False
     - ချောမွေ့သော မြေမျက်နှာပြင်များအတွက် Zevenbergen&Thorne formula ကိုဖွင့်ပြီးအသုံးပြုပါသည်။
   * - **Combined shading** (**ပေါင်းစပ်ထားသော အရိပ်များ**)
     - ``COMBINED``

     - [boolean]

       Default: False
     - 
   * - **Multidirectional shading** (**အဘက်ဘက်မှ အရိပ်ထိုးခြင်း**)
     - ``MULTIDIRECTIONAL``
     - [boolean]

       Default: False
     - 
   * - **Hillshade**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

အဆင့်မြင့် parameter များ (Advanced parameters)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Hillshade** (**တောင်အရိပ်**)
     - ``OUTPUT``
     - [raster]
     - အလိုအလျှောက်ဖြည့်သွင်းတွက်ထုတ်ထားသောတန်ဖိုးများပါဝင်သော output raster

Python code
............

**Algorithm ID**: ``gdal:hillshade``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalnearblack:

Near black (အနက်ရောင်နီးပါး)
-----------------------------

အနက်/အဖြူ နီးပါးဖြစ်နေသော ပုံအစွန်အဖျားများကို အနက် အဖြစ်ပြောင်းလဲပေးပါသည်။

Algorithm သည် ဓာတ်ပုံတစ်ပုံလုံးကို scan ဖတ်ပြီး collar တဝိုက်က အနက်၊ အဖြူ နီးပါးဖြစ်နေသော pixel များနှင့် အခြားအရောင်များရှိသော pixel များကို အနက် သို့မဟုတ် အဖြူအဖြစ်သို့ ပြောင်းလဲပေးပါသည်။ Mosaicking ပြုလုပ်သောအချိန်တွင် အရောင်ပါသော pixel များကို ဖောက်ထွင်းမြင်ရနိုင်ရန်အတွက် lossy နည်းလမ်းဖြင့် ချုံ့ထားသော ကောင်းကင်ဓာတ်ပုံများကို ပြင်ဆင်ရန် အသုံးပြုပါသည်။

Algorithm ကို `GDAL nearblack utility <https://gdal.org/programs/nearblack.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **How far from black (white)** (**အဖြူ/အမဲ မှ မည်မျှ ကွာဝေးပါသလဲ**)
     - ``NEAR``
     - [number]

       Default: 15
     - အနက်၊ အဖြူ သို့မဟုတ် အခြားအရောင်များမှ pixel တန်ဖိုးများ ဘယ်လောက်ဝေးကွာနိုင်သလဲ ဆိုသည်ကို ရွေးချယ်ပြီး အနီးနား အနက်၊ အဖြူ သို့မဟုတ် အခြားအရောင်အဖြစ် ယူဆပါသည်။
   * - **Search for nearly white pixels instead of nearly black** (**အနက်နီးပါးအစား အဖြူနီးပါးဖြစ်နေသော pixel များကိုရှာဖွေပါ**)
     - ``WHITE``
     - [boolean]

       Default: False
     - အနက်ရောင် pixel များအစား အဖြူရောင်နီးပါး ဖြစ်နေသော pixel များ (255) ကိုရှာပါ
   * - **Nearblack** (**အနက်ရောင်နီးပါး**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])````
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Nearblack** (**အနက်ရောင်နီးပါး**)
     - ``OUTPUT``
     - [raster]
     - ရလာဒ် raster

Python code
............

**Algorithm ID**: ``gdal:nearblack``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalproximity:

Proximity (raster distance) (အနီးအဝေးပြမှု (raster အကွာအဝေး))
--------------------------------------------------------------

Pixel တစ်ခုချင်းစီ၏ ဗဟိုမှ Target (အသုံးပြုမည့်) pixel အဖြစ်သတ်မှတ်သော အနီးဆုံး pixel ၏ဗဟိုသို့  အကွာအဝေးကို ညွှန်ပြသော raster proximity မြေပုံတစ်ခုကို ထုတ်ပေးပါသည်။ Raster pixel တန်ဖိုးသည် target pixel တန်ဖိုးများထဲတွင် ရှိနေသော source raster ထဲရှိ အရာများသည် target pixel များဖြစ်ကြပါသည်။

Algorithm ကို `GDAL proximity utility <https://gdal.org/programs/gdal_proximity.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် နှင့်ပတ်သက်သော အချက်အလက်များပါဝင်သည့် band
   * - **A list of pixel values in the source image to be considered target pixels** (**Target pixel များအဖြစ်ယူဆမည့် source image ထဲရှိ pixel တန်ဖိုးများစာရင်းတစ်ခု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``VALUES``
     - [string]

       Default: ''
     - Target pixle များအဖြစ် ယူဆမည့် source image ထဲရှိ target pixel တန်ဖိုးများစာရင်း။ သတ်မှတ်မပေးထားလျှင် သုညမဟုတ်သော pixel များအားလုံးကို target pixel များအဖြစ် ယူဆပါလိမ့်မည်။
   * - **Distance units** (**အကွာအဝေးယူနစ်များ**)
     - ``UNITS``
     - [enumeration]

       Default: 1
     - တွက်ထုတ်ထားသော အကွာအဝေးများသည် pixel ထဲတွင်ရှိသင့်သလား သို့မဟုတ် georeference လုပ်ထားသော ကိုဩဒိနိတ်ထဲတွင် ရှိသင့်သလား ညွှန်ပြပေးပါသည်။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 --- Georeference လုပ်ထားသော ကိုဩဒိနိတ်များ
       * 1 --- Pixel ကိုဩဒိနိတ်များ

   * - **The maximum distance to be generated** (**ဖန်တီးယူမည့် အဝေးဆုံးအကွာအဝေး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAX_DISTANCE``
     - [number]

       Default: 0.0
     - ထုတ်ပေးမည့် အဝေးဆုံးအကွာအဝေး။ ၎င်းအကွာအဝေးထက်ပိုဝေးသော pixel များအတွက် nodata တန်ဖိုးကို အသုံးပြုပါလိမ့်မည်။ Nodata တန်ဖိုးကိုထည့်ပေးမထားလျှင် output band ကို ၎င်း၏ nodata တန်ဖိုးအတွက် မေးမြန်းတောင်းဆိုပါလိမ့်မည်။ Output band သည် nodata တန်ဖိုးမရှိလျှင် 65536 တန်ဖိုးကိုအသုံးပြုပါလိမ့်မည်။ *အကွာအဝေးယူနစ်များ* ၏တန်ဖိုးအတိုင်း အကွာအဝေးကို တွက်ထုတ်ပေးပါသည်။
   * - **Value to be applied to all pixels that are within the maxdist of target pixels** (**Target pixel များ၏ အဝေးဆုံးအကွာအဝေးအတွင်းရှိ pixel များအားလုံးတွင် အသုံးချရန်တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``REPLACE``
     - [number]

       Default: 0.0
     - အကွာအဝေးတန်ဖိုးတစ်ခုအစား target pixel များမှ (target pixel များအပါအဝင်) အဝေးဆုံးအကွာအဝေးထက် ပိုနီးသော pixel များအားလုံးကို အသုံးချပေးမည့် တန်ဖိုးကို သတ်မှတ်ပေးပါသည်။
   * - **Nodata value to use for the destination proximity raster** (**Destination proximity raster အတွက်အသုံးပြုမည့် Nodata တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: 0.0
     - ရလာဒ် raster အတွက်အသုံးပြုမည့် Nodata တန်ဖိုးများကို သတ်မှတ်ပါ။
   * - **Proximity map**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။

   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type**  (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - ရလာဒ် raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Proximity map** (**အနီးအဝေးပြမြေပုံ**)
     - ``OUTPUT``
     - [raster]
     - Output raster

Python code
............

**Algorithm ID**: ``gdal:proximity``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalroughness:

Roughness (ကြမ်းတမ်းမှု)
-------------------------

မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် မှ တွက်ထုတ်ထားသော တန်ဖိုးများပါဝင်သော band တစ်ခုတည်းပါသော raster တစ်ခုကို ထုတ်ပေးပါသည်။ Roughness (ကြမ်းတမ်းမှု) သည် မျက်နှာပြင်၏ မညီမညာမှု ဒီဂရီ ဖြစ်ပါသည်။ အလယ်ဗဟို pixel နှင့် ၎င်းပတ်ဝန်းကျင်မှ cell များ၏ အကြီးမားဆုံး inter-cell ခြားနားမှုဖြင့် roughness ကိုတွက်ထုတ်ပါသည်။ Roughness သည် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် data များကို လေ့လာဆန်းစစ်ရာတွင် အသုံးပြုနိုင်ပြီး မြစ်မျက်နှာပြင်ဆိုင်ရာ၊ ရာသီဥတုနှင့် ပထဝီအနေအထားများအတွက် ထွက်ထုတ်ရာတွင် အသုံးဝင်ပါသည်။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် အဖြစ် အသုံးပြုမည့် band နံပါတ်
   * - **Compute edges** (**Edge များကိုတွက်ချက်ခြင်း**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster မှ edge များကိုထုတ်ပေးပါသည်။
   * - **Roughness** (**ကြမ်းတမ်းမှု**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
	   

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Roughness**
     - ``OUTPUT``
     - [raster]
     - Band တစ်ခုတည်းပါသော ရလာဒ် roughness raster။ -9999 တန်ဖိုးကို nodata တန်ဖိုးအဖြစ် အသုံးပြုပါသည်။

Python code
............

**Algorithm ID**: ``gdal:roughness``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalsieve:

Sieve
------

ကန့်သတ်အရွယ်အစားထက် ပိုသေးငယ်သော raster polygon များကို ဖယ်ထုတ်ပြီး အနီးအနားရှိ အကြီးဆုံး polygon ၏ pixel တန်ဖိုးဖြင့် အစားထိုးပါသည်။ Raster map တွင် သေးငယ်သောဧရိယာများ များစွာပါဝင်သောအခါတွင် အသုံးဝင်ပါသည်။

Algorithm ကို `GDAL sieve utility <https://gdal.org/programs/gdal_sieve.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Threshold** (**သတ်မှတ်တန်ဖိုး**)
     - ``THRESHOLD``
     - [number]

       Default: 10
     - ၎င်း အရွယ်အစားထက် ပိုသေးငယ်သော raster polygon များကိုသာ ဖယ်ထုတ်မည်ဖြစ်ပါသည်။
   * - **Use 8-connectedness** (**၈ခု ချိတ်ဆက်မှုကို အသုံးပြုခြင်း**)
     - ``EIGHT_CONNECTEDNESS``
     - [boolean]

       Default: False
     - ၄ ခုချိတ်ဆက်မှုအစား ၈ ခုချိတ်ဆက်မှုကို အသုံးပြုပါသည်။
   * - **Do not use the default validity mask for the input band** (**Input band အတွက် မူရင်း validity mask ကိုအသုံးမပြုခြင်း**)
     - ``NO_MASK``
     - [boolean]

       Default: False
     - 
   * - **Validity mask**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MASK_LAYER``
     - [raster]
     - မူရင်းကိုအသုံးပြုမည့်အစား validity mask ကိုအသုံးပြုခြင်း
   * - **Sieved**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Sieved**
     - ``OUTPUT``
     - [raster]
     - Output raster layer

Python code
............

**Algorithm ID**: ``gdal:sieve``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalslope:

Slope (လျှောစောက်)
-------------------

GDAL အသုံးပြုနိုင်သော မည်သည့် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့်ပြ raster မှမဆို slope map တစ်ခုကို ထုတ်ပေးပါသည်။ Slope ဆိုသည်မှာ ရေပြင်ညီမျက်နှာပြင်မှ စောင်းနေသော ထောင့်ကိုဆိုလိုပါသည်။ မိမိအသုံးပြုလိုသော slope ၏အမျိုးအစားကို သတ်မှတ်နိုင်သော နည်းလမ်းများရှိပါသည် - slope ဒီဂရီ သို့မဟုတ် slope ရာခိုင်နှုန်း။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် နှင့်ပတ်သက်သော အချက်အလက်များပါဝင်သည့် band
   * - **Ratio of vertical units to horizontal** (**ဒေါင်လိုက်ယူနစ်များနှင့် ရေပြင်ညီမျက်နှာပြင်မှ ယူနစ်များ၏ အချိုး**)
     - ``SCALE``
     - [number]

       Default: 1.0
     - ဒေါင်လိုက်ယူနစ်များနှင့် ရေပြင်ညီမျက်နှာပြင်မှ ယူနစ်များ၏ အချိုး
   * - **Slope expressed as percent (instead of degrees)** (**ဒီဂရီအစား ရာခိုင်နှုန်းဖြင့်ဖော်ပြသော slope**)
     - ``AS_PERCENT``
     - [boolean]

       Default: False
     - ဒီဂရီအစား slope ကို ရာခိုင်နှုန်းဖြင့်ဖော်ပြခြင်း
   * - **Compute edges** (**အစွန်း များကိုတွက်ချက်ခြင်း**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster မှ edge (အစွန်း) များကိုထုတ်ပေးပါသည်။
   * - **Use Zevenbergen&Thorne formula (instead of the Horn's one)** (**Horm formula အစား Zevenbergen&Thorne formula ကိုအသုံးပြုပါ**)
     - ``ZEVENBERGEN``
     - [boolean]

       Default: False
     - မျက်နှာပြင်ကိုချောမွေ့စေခြင်းအတွက် Zevenbergen&Thorne formula ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပေးပါသည်။
   * - **Slope**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Slope** (**လျှောစောက်**)
     - ``OUTPUT``
     - [raster]
     - Output raster

Python code
............

**Algorithm ID**: ``gdal:slope``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaltriterrainruggednessindex:

Terrain Ruggedness Index (TRI) (မြေမျက်နှာသွင်ပြင်ကြမ်းတမ်းမှုပြအညွှန်း)
-------------------------------------------------------------------------

မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် မှ တွက်ချက်ထားသောတန်ဖိုးများပါဝင်သော band တစ်ခုတည်းပါသော raster တစ်ခုကို ထုတ်ပေးပါသည်။ TRI ဆိုသည်မှာ အလယ်ဗဟို pixel နှင့် ၎င်းပတ်ဝန်းကျင်မှ pixel များအကြား ပျမ်းမျှခြားနားချက်ကို သတ်မှတ်သော Terrain Ruggedness Index ဖြစ်ပါသည်။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် အဖြစ်အသုံးပြုမည့် band နံပါတ်။
   * - **Compute edges** (**အစွန်း များကိုတွက်ချက်ခြင်း**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster မှ edge (အစွန်း) များကိုထုတ်ပေးပါသည်။
   * - **Terrain Ruggedness Index**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
	   

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Terrain Ruggedness Index**
     - ``OUTPUT``
     - [raster]
     - ကြမ်းတမ်းမှုပြ raster ကို ရလာဒ်ထုတ်ပေးပါသည်။ -9999 တန်ဖိုးကို nodata တန်ဖိုးအဖြစ် အသုံးပြုပါသည်။

Python code
............

**Algorithm ID**: ``gdal:triterrainruggednessindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaltpitopographicpositionindex:

Topographic Position Index (TPI) (မြေမျက်နှာသွင်ပြင်တည်နေရာပြအညွှန်း)
----------------------------------------------------------------------

မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် မှ တွက်ချက်ထားသောတန်ဖိုးများပါဝင်သော band တစ်ခုတည်းပါသော raster တစ်ခုကို ထုတ်ပေးပါသည်။ TPI ဆိုသည်မှာ အလယ်ဗဟို pixel နှင့် ၎င်းပတ်ဝန်းကျင်မှ pixel များအကြား ခြားနားချက်ကို သတ်မှတ်သော Topographic Position Index ဖြစ်ပါသည်။

Algorithm ကို `GDAL DEM utility <https://gdal.org/programs/gdaldem.html>`_ မှ ရယူပါသည်။

**Default menu**: :menuselection:`Raster --> Analysis`

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် တန်ဖိုးများအတွက် အသုံးပြုမည့် band နံပါတ်။
   * - **Compute edges** (**Edge များကိုတွက်ချက်ခြင်း**)
     - ``COMPUTE_EDGES``
     - [boolean]

       Default: False
     - မြေမျက်နှာပြင်အနိမ့်အမြင့်ပြ raster မှ edge များကိုထုတ်ပေးပါသည်။
   * - **Terrain Ruggedness Index**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းပေးပါသည်])``
     - ရလာဒ် raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile ကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုအဖွဲ့လိုက်လုပ်ဆောင်ခြင်း (Batch Process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
 

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Terrain Ruggedness Index**
     - ``OUTPUT``
     - [raster]
     - Output raster

Python code
............

**Algorithm ID**: ``gdal:tpitopographicpositionindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
