Raster conversion (Raster များကို ပြောင်းလဲခြင်း)
==================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdalgdal2xyz:

gdal2xyz
---------

Raster data များကို XYZ ASCII file format အဖြစ်ပြောင်းလဲပေးပါသည်။

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
     - ပြောင်းလဲရန် raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: Input layer ၏ ပထမဆုံး band
   
     - Raster သည် band များစွာပါလျှင် ကိုယ်ပြောင်းလဲချင်သော band တစ်ခုကိုရွေးချယ်ပါ။
   * - **Source nodata** (**မူလ nodata**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA_INPUT``
     - [number]

       Default: None
     - "nodata" (GDAL >= 3.7) အဖြစ်လုပ်ဆောင်မည့် input pixel တန်ဖိုး။
   * - **Destination nodata** (**နောက်ဆုံးရလာဒ် nodata**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA_OUTPUT``
     - [number]

       Default: None
     - သတ်မှတ် "nodata" တန်ဖိုးကို Output (GDAL >= 3.7) တွင် သတ်မှတ်ပေးပါသည်။
   * - **Do not output nodata values** (**Nodata တန်ဖိုးများ ထုတ်မပေးပါ**)
     - ``SKIP_NODATA``
     - [boolean]

       Default: False
     - "Nodata" တန်ဖိုးများ (GDAL >= 3.3) ကိုထုတ်မပေးပါ။
   * - **Output comma-separated values** (**Comma ဖြင့်ခွဲခြားထားသော တန်ဖိုးများကို ထုတ်ပေးပါ**)
     - ``CSV``
     - [boolean]

       Default: False
     - Output file သည် comma-separated values (csv) အမျိုးအစား ဖြစ်သင့်/မသင့် သတ်မှတ်ပေးပါသည်။
   * - **XYZ ASCII file**
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **XYZ ASCII file**
     - ``INPUT``
     - [table]
     - Raster band မှ ထုတ်ပေးသော တန်ဖိုးများပါဝင်သည့် ဇယား file။

Python code
............

**Algorithm ID**: ``gdal:gdal2xyz``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalpcttorgb:

PCT to RGB
-----------

8 bit အရောင်ခြယ်ဓာတ်ပုံတစ်ခုအား 24 bit RGB ဓာတ်ပုံတစ်ခုအဖြစ်သို့ ပြောင်းပေးပါသည်။ ၎င်းသည် input file မှ pseudocolor band တစ်ခုအား လိုချင်သော format ဖြင့် RGB file တစ်ခုအဖြစ်သို့ ပြောင်းလဲပေးပါလိမ့်မည်။

Algorithm ကို `GDAL pct2rgb utility <https://gdal.org/programs/pct2rgb.html>`_ မှ ရယူထားပါသည်။

**Default menu** - :menuselection:`Raster --> Conversion`

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
     - ထည့်သွင်းအသုံးပြုသော 8 bit raster ဓာတ်ပုံ 
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: Input layer ၏ ပထမဆုံး band
   
     - Raster သည် band များစွာပါလျှင် ကိုယ်ပြောင်းလဲချင်သော band တစ်ခုကိုရွေးချယ်ပါ။

   * - **Generate a RGBA file** (**RGBA file တစ်ခုကို ဖန်တီးခြင်း**)
     - ``RGBA``
     - [boolean]

       Default: False
     - Output file သည် RGBA အမျိုးအစား ဖြစ်သင့်/မသင့် ဆိုသည်ကို သတ်မှတ်ပေးပါသည်။
   * - **PCT to RGB**
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output file ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **PCT to RGB**
     - ``OUTPUT``
     - [raster]
     - 24 bit RGB raster ဓာတ်ပုံ	 

Python code
............

**Algorithm ID**: ``gdal:pcttorgb``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalpolygonize:

Polygonize (raster to vector) (Polygon အဖြစ်ပြောင်းလဲခြင်း (raster မှ vector သို့))
------------------------------------------------------------------------------------

Raster ထဲရှိ pixel တန်ဖိုးတူပြီး ချိတ်ဆက်နေသော pixel များအားလုံးအတွက် vector polygon များ ဖန်တီးပေးပါသည်။ Polygon ၏ pixel တန်ဖိုးကို ညွှန်ပေးသော attribute တစ်ခုစီဖြင့် polygon တစ်ခုစီတိုင်းကို ဖန်တီးပေးပါသည်။

Algorithm ကို `GDAL polygonize utility <https://gdal.org/programs/gdal_polygonize.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Conversion`

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

       Default: Input layer ၏ ပထမဆုံး band
     - Raster သည် band များစွာပါလျှင် ကိုယ်ပြောင်းလဲချင်သော band တစ်ခုကိုရွေးချယ်ပါ။
   * - **Name of the field to create** (**ဖန်တီးမည့် column ၏ အမည်**)
     - ``FIELD``
     - [string]

       Default: 'DN'
     - ချိတ်ဆက်ထားသောအပိုင်းများ၏ attribute များအတွက် column နာမည်ကို သတ်မှတ်ပေးပါသည်။
   * - **Use 8-connectedness** (**၈ ခု ချိတ်ဆက်မှုကို အသုံးပြုပါ**)
     - ``EIGHT_CONNECTEDNESS``
     - [boolean]

       Default: False
     - သတ်မှတ်မထားလျှင် raster cell များသည် ချိတ်ဆက်ထားမှု (*၄ ခု ချိတ်ဆက်မှု*) အဖြစ်ယူဆရန် ဘုံ နယ်နမိတ်တစ်ခုရှိရပါမည်။ သတ်မှတ်ထားလျှင် ထိစပ်နေသော raster cell များကို ချိတ်ဆက်ထားသည်ဟု ယူဆပါသည် (*၈ ခု ချိတ်ဆက်မှု*)
   * - **Vectorized** (**Vector ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output (polygon) vector layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -
 
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
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းပေးပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vectorized** (**Vector ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [vector: polygon]
     - Output vector layer

Python code
............

**Algorithm ID**: ``gdal:polygonize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrearrange_bands:

Rearrange bands (Band များကို ပြန်လည်စီစဉ်ခြင်း)
-------------------------------------------------

အသုံးပြုထားသော raster layer တစ်ခုမှ ရွေးချယ်ထားသော band များကိုအသုံးပြုပြီး raster အသစ်တစ်ခု ဖန်တီးပေးပါသည်။ အသစ်ဖန်တီးလိုက်သော raster အတွက် band များကိုပြန်လည်စီစဉ်နိုင်အောင် algorithm မှလုပ်ဆောင်ပေးပါသည်။

Algorithm ကို `GDAL translate utility <https://gdal.org/programs/gdal_translate.html>`_ မှ ရယူပါသည်။

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
   * - **Selected band(s)** (**ရွေးချယ်ထားသော band များ**)
     - ``BANDS``
     - [raster band] [list]

       Default: None
     - Raster အသစ်တစ်ခုဖန်တီးရန်အတွက် အသုံးပြုမည့် ပြန်လည်စီစဉ်ထားသည့် band များစာရင်း
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]

       Default:  ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output raster ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Output data type** (**ရလာဒ် data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 0
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types_extended**
          :end-before: **end_raster_data_types_extended**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]
     - ပြန်လည်စီစဉ်ထားသော band များဖြင့် output raster layer

Python code
............

**Algorithm ID**: ``gdal:rearrange_bands``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrgbtopct:

RGB to PCT
-----------

24 bit RGB ဓာတ်ပုံတစ်ခုကို 8 bit ဓာတ်ပုံတစ်ခုအဖြစ်ပြောင်းလဲပေးပါသည်။ လျှော့ချထားသော RGB histrogram တစ်ခုပေါ်တွင် median cut algorithm ကိုအသုံးပြုပြီး ထည့်သုံးထားသော RGB ဓာတ်ပုံအတွက် အကောင်းဆုံး pseudo-color ဇယားတစ်ခုကို တွက်ထုတ်ပေးပါသည်။ ထို့နောက် ၎င်းသည် အရောင်ဇယားကိုအသုံးပြုပြီး ဓာတ်ပုံကို pseudo-colored ဓာတ်ပုံအဖြစ် ပြောင်းလဲပေးပါသည်။ Output ဓာတ်ပုံ၏ အမြင်ပိုင်းအရည်အသွေးကို မြှင့်တင်ရန်အတွက် ဤပြောင်းလဲခြင်းသည် Floyd-Steinberg dithering (error diffusion) ကိုအသုံးပြုပါသည်။

Raster မြေပုံတစ်ခုကိုအတန်းအစားခွဲပြီး အတန်းအစားအရေအတွက်ကို လျှော့ချချင်လျှင် ဤ algorithm ကိုအသုံးပြုပြီး ဓာတ်ပုံကို အရွယ်အစား လျှော့ချရန် အသုံးဝင်ပါသည်။

Algorithm ကို `GDAL rgb2pct utility <https://gdal.org/programs/rgb2pct.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Conversion`

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
     - ထည့်သွင်းအသုံးပြုသော (RGB) raster layer
   * - **Number of colors**
     - ``NCOLORS``
     - [number]

       Default: 2
     - ရလာဒ် ဓာတ်ပုံတွင် ပါဝင်မည့် အရောင်အရေအတွက်။ 2-256 အတွင်းရှိ တန်ဖိုးတစ်ခု ဖြစ်နိုင်ပါသည်။
   * - **RGB to PCT**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output raster ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **RGB to PCT**
     - ``OUTPUT``
     - [raster]
     - Output raster layer

Python code
............

**Algorithm ID**: ``gdal:rgbtopct``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaltranslate:

Translate (convert format) (ဘာသာပြန်ခြင်း (format ပြောင်းလဲခြင်း))
-------------------------------------------------------------------

Raster data များကို format အမျိုးမျိုးပြောင်းလဲပေးပါသည်။

Algorithm ကို `GDAL translate utility <https://gdal.org/programs/gdal_translate.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Conversion`

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Override the projection of the output file** (**Output file ၏ projection ကို အစားထိုးရေးသားခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_CRS``
     - [crs]
     - Output file အတွက် projection တစ်ခုကို သတ်မှတ်ခြင်း
   * - **Assign a specified nodata value to output bands** (**Output band များအတွက် nodata တန်ဖိုးများကို သတ်မှတ်ပါ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: Not set (သတ်မှတ်မထားပါ)
     - Output raster ထဲတွင် nodata အတွက် အသုံးပြုမည့် တန်ဖိုးကိုသတ်မှတ်ပေးပါသည်
   * - **Copy all subdatasets of this file to individual output files** (**ဤ file မှ subdataset များအားလုံးကို output file တစ်ခုချင်းစီသို့ ကူးထည့်ခြင်း**)
     - ``COPY_SUBDATASETS``
     - [boolean]

       Default: False
     - Subdataset များအတွက် သီးခြား file တစ်ခုချင်းစီကို ဖန်တီးခြင်း
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output (ဘာသာပြန်ထားသော) raster layer ၏ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Additional command-line parameters** (**ထပ်ဆောင်း command-line parameter များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``EXTRA``
     - [string]

       Default: None
     - ထပ်ဆောင်း GDAL command line ရွေးချယ်စရာများကို ထည့်ပေါင်းခြင်း
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 0
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types_extended**
          :end-before: **end_raster_data_types_extended**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Converted** (**ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]
     - Output (ဘာသာပြန်ထားသော) raster layer

Python code
............

**Algorithm ID**: ``gdal:translate``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
