Raster extraction (Raster ထဲမှ ဆွဲထုတ်ခြင်း)
=============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdalcliprasterbyextent:

Clip raster by extent (နယ်ပယ်အကျယ်အဝန်းတစ်ခုဖြင့် raster ကိုဖြတ်ခြင်း)
-----------------------------------------------------------------------

GDAL မှလုပ်ဆောင်ပေးနိုင်သော မည်သည့် raster file ကိုမဆို သတ်မှတ်ပေးသည့်အတိုင်းအတာ အကျယ်အဝန်းတစ်ခုဖြင့် ဖြတ်ထုတ်ပေးပါသည်။

Algorithm ကို `GDAL translate utility <https://gdal.org/programs/gdal_translate.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Extraction`

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
     - ထည့်သွင်းအသုံးပြုသော raster
   * - **Clipping extent** (**ဖြတ်ထုတ်မည့်အကျယ်အဝန်း**)
     - ``EXTENT``
     - [extent]

     - Output raster အတွက်အသုံးပြုသင့်သော အကျယ်အဝန်း။ Output တွင် သတ်မှတ်ထားသော ဘောင်အတွင်းရှိ pixel များသာ ပါဝင်လာပါမည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Override the projection for the output file** (**Output file အတွက် projection ကို အစားထိုးပြင်ဆင်ခြင်း**)
     - ``OVERCRS``
     - [boolean]

       Default: False
     - အမှန်ခြစ် ခြစ်ထားလျှင် output file သည် input layer ၏ CRS ကို အသုံးပြုပါသည်။
   * - **Assign a specified nodata value to output bands** (**Output band များကို nodata တန်ဖိုးတစ်ခု သတ်မှတ်ပေးခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: None
     - Output raster ထဲတွင် nodata တန်ဖိုးများအတွက် ထည့်သွင်းသင့်သော တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးပါသည်။
   * - **Clipped (extent)** (**ဖြတ်ထုတ်ထားသောအကျယ်အဝန်း**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output raster layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile များကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုလိုက်လုပ်ဆောင်ခြင်း (Batch process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
   
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 0
     - Output raster file ၏ format ကို သတ်မှတ်ပေးပါသည်။
       ရွေးချယ်စရာများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types_extended**
          :end-before: **end_raster_data_types_extended**

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
   * - **Clipped (extent)** (**ဖြတ်ထုတ်ထားသော (နယ်ပယ်အကျယ်အဝန်း)**)
     - ``OUTPUT``
     - [raster]
     - သတ်မှတ်ပေးသည့်အတိုင်းအတာ အကျယ်အဝန်းတစ်ခုဖြင့် ဖြတ်ထုတ်ထားသော output raster layer

Python code
............

**Algorithm ID**: ``gdal:cliprasterbyextent``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalcliprasterbymasklayer:

Clip raster by mask layer (Raster ကို ဖုံးအုပ် layer ဖြင့် ဖြတ်ထုတ်ခြင်း) 
---------------------------------------------------------------------------

GDAL မှလုပ်ဆောင်ပေးနိုင်သော မည်သည့် raster file ကိုမဆို vector mask (အဖုံးအအုပ်) layer တစ်ခုဖြင့် ဖြတ်ထုတ်ပေးပါသည်။

Algorithm ကို `GDAL warp utility <https://gdal.org/programs/gdalwarp.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Extraction`

Parameter များ
...............

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 20 20 30
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster
   * - **Mask layer** (**အဖုံးအအုပ် layer**)
     - ``MASK``
     - [vector: polygon]
     - Raster ကိုဖြတ်ထုတ်ခြင်းအတွက် vector mask
   * - **Source CRS** (**ရင်းမြစ် CRS**)
     - ``SOURCE_CRS``
     - [crs]
     - Input raster အတွက် အသုံးပြုမည့် coordinate reference ကို သတ်မှတ်ပေးပါသည်
   * - **Target CRS**
     - ``TARGET_CRS``
     - [crs]
     - Mask layer အတွက် အသုံးပြုမည့် coofdinate reference ကို သတ်မှတ်ပေးပါသည်
   * - **Target extent** (**လိုချင်သော အကျယ်အဝန်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_EXTENT``
     - [extent]

     - ဖန်တီးမည့် output file ၏ အကျယ်အဝန်း၊ အသုံးပြုနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Assign a specified nodata value to output bands** (**Output band များအတွက် nodata တန်ဖိုးတစ်ခုကို သတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: None
     - Output raster ထဲတွင် nodata တန်ဖိုးများအတွက် ထည့်သွင်းသင့်သော တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးပါသည်။
   * - **Create an output alpha band** (**Output alpha band တစ်ခုကိုဖန်တီးခြင်း**)
     - ``ALPHA_BAND``
     - [boolean]

       Default: False (မှား)
     - ရလာဒ်အတွက် alpha band တစ်ခုကို ဖန်တီးပေးပါသည်။ Alpha band တွင် pixel များ၏ အလင်းဖောက်မြင်နိုင်စွမ်း တန်ဖိုးများပါဝင်ပါသည်။
   * - **Match the extent of the clipped raster to the extent of the mask layer** (**ဖြတ်ထုတ်မည့် raster ၏အကျယ်အဝန်းကို mask layer ၏ အကျယ်အဝန်းနှင့် ကိုက်ညီအောင်လုပ်ခြင်း**)
     - ``CROP_TO_CUTLINE``
     - [boolean]

       Default: True
     - အမှန်ခြစ် ခြစ်ထားလျှင် vector layer အကျယ်အဝန်းကို output raster အတွက် အသုံးပြုပါမည်။
   * - **Keep resolution of input raster** (**Input raster ၏ ကြည်လင်ပြတ်သားမှုကိုထိန်းထားခြင်း**)
     - ``KEEP_RESOLUTION``
     - [boolean]

       Default: False
     - Output raster ၏ resolution သည်ပြောင်းလဲမသွားပါ
   * - **Set output file resolution** (**Output file resolution ကိုသတ်မှတ်ခြင်း**)
     - ``SET_RESOLUTION``
     - [boolean]

       Default: False
     - Output resolution (pixel တစ်ခု၏ အရွယ်အစား) ကို သတ်မှတ်သင့်ပါသည်
   * - **X Resolution to output bands** (**Output band များ၏ X Resolution**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``X_RESOLUTION``
     - [number]

       Default: None
     - Output raster ထဲရှိ pixel များ၏ အကျယ် (အနံ)
   * - **Y Resolution to output band** (**Output band ၏ Y Resolution**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``Y_RESOLUTION``
     - [number]

       Default: None
     - Output raster ထဲရှိ pixel များ၏ အမြင့် (အထက်အောက်အလျား)
   * - **Use multithreaded warping implementation** (**Multithread warping လုပ်ဆောင်ချက်ကို အသုံးပြုခြင်း**)
     - ``MULTITHREADING``
     - [boolean]

       Default: False
     - ဓာတ်ပုံအစုအစည်းများကို လုပ်ဆောင်ပေးရန် thread နှစ်ခုကိုအသုံးပြုပြီး input/output လုပ်ဆောင်မှုများကို တပြိုင်တည်းလုပ်ဆောင်ပါသည်။ တွက်ချက်ခြင်းသည် multithread မဟုတ်ပါ။
   * - **Clipped (mask)** (**ဖြတ်ထုတ်ထားသော (အဖုံးအအုပ်)**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])````
     - Output raster layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -
 
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
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးမှုနည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: ''
     - Raster ဖန်တီးခြင်းကို ထိန်းချုပ်သော ဖန်တီးခြင်းနည်းလမ်းများကို ပိုမိုပေါင်းထည့်ရန် (အရောင်၊ block အရွယ်အစား၊ file ချုံ့ခြင်း)။ လွယ်ကူစေရန် ကြိုတင်သတ်မှတ်ထားသော profile များကိုအသုံးပြုနိုင်ပါသည် (:ref:`GDAL driver options section <gdal_createoptions>` တွင်ကြည့်ပါ)။ အစုလိုက်လုပ်ဆောင်ခြင်း (Batch process) နှင့် Model Designer - နည်းလမ်းများစွာကို pipe character (``|``) ဖြင့်ပိုင်းခြားထားပါသည်။
	   
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 0
     - Output raster file ၏ format ကိုသတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types_extended**
          :end-before: **end_raster_data_types_extended**

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
   * - **Clipped (mask)** (**ဖြတ်ထုတ်ထားသော (အဖုံးအအုပ်)**)
     - ``OUTPUT``
     - [raster]
     - Vector layer ဖြင့် ဖြတ်ထုတ်ထားသော output raster layer

Python code
............

**Algorithm ID**: ``gdal:cliprasterbymasklayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalcontour:

Contour (ကွန်တို)
------------------

GDAL မှလုပ်ဆောင်ပေးနိုင်သော မည်သည့် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster မှမဆို ကွန်တိုလိုင်းများကို ဖန်တီးထုတ်ယူပေးပါသည်။

Algorithm ကို `GDAL contour utility <https://gdal.org/programs/gdal_contour.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Extraction`

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
     - ထည့်သွင်းအသုံးပြုသော raster
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - ကွန်တိုဖန်တီးယူမည့် raster band
   * - **Interval between contour lines** (**ကွန်တိုမျဉ်း နှစ်ခုအကြား အကွာအဝေး**)
     - ``INTERVAL``
     - [number]

       Default: 10.0
     - အသုံးပြုထားသော မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster ထဲရှိ ယူနစ်ဖြင့် ကွန်တိုမျဉ်း နှစ်ခုကြားက အကွာအဝေးကို သတ်မှတ်ပေးပါသည် (အနည်းဆုံးတန်ဖိုးမှာ 0 ဖြစ်ပါသည်)
   * - **Attribute name (if not set, no elevation attribute is attached)** (**Attribute အမည် (သတ်မှတ်မထားလျှင် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် attribute ပါလာမည် မဟုတ်ပါ)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD_NAME``
     - [string]

       Default: 'ELEV'
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် ကိုထည့်သွင်းရမည့် attribute အတွက် အမည်တစ်ခုပေးပါသည်။
   * - **Offset from zero relative to which to interpret intervals** (**ကြားအကွာအဝေးများကို နားလည်အောင်ရှင်းပြပေးရန် သုညမှ အရွေ့အကွာအဝေး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OFFSET``
     - [number]

       Default: 0.0
     -
   * - **Contours** (**ကွန်တိုများ**)
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])````
     - Output vector layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Produce 3D vector** (**သုံးဘက်မြင် vector ကိုဖန်တီးခြင်း**)
     - ``CREATE_3D``
     - [boolean]

       Default: False
     - နှစ်ဘက်မြင်အစား သုံးဘက်မြင် vector များကို တွန်းအားပေး ဖန်တီးပါသည်။ Vertex (မျဉ်းအဆစ်) တိုင်းတွင် အနိမ့်အမြင့် တန်ဖိုးများပါဝင်ပါသည်။
   * - **Treat all raster values as valid** (**Raster တန်ဖိုးများအားလုံးကို valid အဖြစ် လုပ်ဆောင်ပါ**)
     - ``IGNORE_NODATA``
     - [boolean]

       Default: False
     - Dataset ထဲရှိ nodata တန်ဖိုးများအားလုံးကို လျစ်လျှူရှုပေးပါသည်။
   * - **Input pixel value to treat as "nodata"** (**"nodata" အဖြစ်လုပ်ဆောင်မည့် Input pixel တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: None
     - Output raster ထဲတွင် nodata တန်ဖိုးများအတွက် ထည့်သွင်းသင့်သော တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း။ သက်ဆိုင်သော GDAL အသုံးပြုမှု မှတ်တမ်းကို ရည်ညွှန်းပါ။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Contours** (**ကွန်တိုများ**)
     - ``OUTPUT``
     - [vector: line]
     - ကွန်တိုမျဉ်းများဖြင့် output vector layer

Python code
............

**Algorithm ID**: ``gdal:contour``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalcontour_polygon:

Contour Polygons (ကွန်တို polygon များ)
----------------------------------------

GDAL မှလုပ်ဆောင်ပေးနိုင်သော မည်သည့် မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster မှမဆို ကွန်တို polygon များဖန်တီးထုတ်ယူပေးပါသည်။

Algorithm ကို `GDAL contour utility <https://gdal.org/programs/gdal_contour.html>`_ မှ ရယူပါသည်။

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
     - ထည့်သွင်းအသုံးပြုသော raster
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - ကွန်တိုဖန်တီးယူမည့် raster band
   * - **Interval between contour lines** (**ကွန်တိုမျဉ်း နှစ်ခုအကြား အကွာအဝေး**)
     - ``INTERVAL``
     - [number]

       Default: 10.0
     - အသုံးပြုထားသော မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster ထဲရှိ ကွန်တိုမျဉ်း နှစ်ခုကြား အကွာအဝေးကို သတ်မှတ်ပေးပါသည် (အနည်းဆုံးတန်ဖိုးမှာ 0 ဖြစ်ပါသည်)
   * - **Offset from zero relative to which to interpret intervals** (**ကြားအကွာအဝေးများကို နားလည်အောင်ရှင်းပြပေးရန် သုညမှ အရွေ့အကွာအဝေး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OFFSET``
     - [number]

       Default: 0.0
     -
   * - **Attribute name for minimum elevation of contour polygon** (**ကွန်တို polygon ၏ အနိမ့်ဆုံး မြေမျက်နှာပြင်အတွက် Attribute အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD_NAME_MIN``
     - [string]

       Default: 'ELEV_MIN'
     - ကွန်တို polygon ၏ အနိမ့်ဆုံး မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် ကိုထည့်သွင်းရမည့် attribute အတွက် အမည်တစ်ခုပေးပါသည်။ အနိမ့်ဆုံးတန်ဖိုးကို သတ်မှတ်မပေးလျှင် အနိမ့်အမြင့် attribute ပါလာမည် မဟုတ်ပါ။
   * - **Attribute name for maximum elevation of contour polygon** (**ကွန်တို polygon ၏ အမြင့်ဆုံး မြေမျက်နှာပြင်အတွက် Attribute အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD_NAME_MAX``
     - [string]

       Default: 'ELEV_MAX'
     - ကွန်တို polygon ၏ အမြင့်ဆုံး မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် ကိုထည့်သွင်းရမည့် attribute အတွက် အမည်တစ်ခုပေးပါသည်။ အမြင့်ဆုံးတန်ဖိုးကို သတ်မှတ်မပေးလျှင် အနိမ့်အမြင့် attribute ပါလာမည် မဟုတ်ပါ။
 
   * - **Contours** (**ကွန်တိုများ**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])````
     - Output vector layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Produce 3D vector** (**သုံးဘက်မြင် vector ဖန်တီးခြင်း**)
     - ``CREATE_3D``
     - [boolean]

       Default: False
     - နှစ်ဘက်မြင်အစား သုံးဘက်မြင် vector များကို တွန်းအားပေး ဖန်တီးပါသည်။ Vertex (မျဉ်းအဆစ်) တိုင်းတွင် အနိမ့်အမြင့် တန်ဖိုးများပါဝင်ပါသည်။
	 
   * - **Treat all raster values as valid** (**Raster တန်ဖိုးများအားလုံးကို valid အဖြစ်လုပ်ဆောင်ခြင်း**)
     - ``IGNORE_NODATA``
     - [boolean]

       Default: False
     - Dataset ထဲရှိ nodata တန်ဖိုးများအားလုံးကို လျစ်လျှူရှုပေးပါသည်။
   * - **Input pixel value to treat as "nodata"** (**"nodata" အဖြစ်လုပ်ဆောင်မည့် Input pixel တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: None
     - Output raster ထဲတွင် nodata တန်ဖိုးများအတွက် ထည့်သွင်းသင့်သော တန်ဖိုးတစ်ခုကို သတ်မှတ်ပေးပါသည်။
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း။ သက်ဆိုင်သော GDAL အသုံးပြုမှု မှတ်တမ်းကို ရည်ညွှန်းပါ။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Contours** (**ကွန်တိုများ**)
     - ``OUTPUT``
     - [vector: polygon]
     - ကွန်တို polygon များဖြင့် output vector layer

Python code
............

**Algorithm ID**: ``gdal:contour_polygon``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
