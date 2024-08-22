Raster projections (Raster ပုံရိပ်ချစနစ်များ)
==============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdalassignprojection:

Assign projection (Projection သတ်မှတ်ခြင်း)
--------------------------------------------

Raster dataset တစ်ခုကို ကိုဩဒိနိတ်စနစ်တစ်ခု သတ်မှတ်ပေးပါသည်။

Algorithm ကို `GDAL edit utility <https://gdal.org/programs/gdal_edit.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Projections`

Parameter များ
...............

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT_LAYER``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Desired CRS** (**လိုချင်သော CRS**)
     - ``CRS``
     - [crs]
     - Output layer ၏ projection (CRS)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer with projection** (**Projection ပါသော layer**)
     - ``OUTPUT``
     - [raster]
     - Projection အသစ်အချက်အလက်များဖြင့် output raster layer

Python code
............

**Algorithm ID**: ``gdal:assignprojection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalextractprojection:

Extract projection (Projection ဆွဲထုတ်ခြင်း)
---------------------------------------------

Raster file တစ်ခု၏ projection ကိုဆွဲထုတ်ပေးပြီး ၎င်းကို :file:`.wld` extension ဖြင့် *world* file တစ်ခုထဲတွင်ရေးပေးပါသည်။

Algorithm ကို `GDAL srsinfo utility <https://gdal.org/programs/gdalsrsinfo.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Projections`

Parameter များ
...............

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **Input file** (**ထည့်သွင်းအသုံးပြုသော file**)
      - ``INPUT_LAYER``
      - [raster]
      - ထည့်သွင်းအသုံးပြုသော raster ။ Algorithm သည် raster file လမ်းကြောင်းကို ဖန်တီးထားသော :file:`.wld` file ၏တည်နေရာအဖြစ် အသုံးပြုသောကြောင့် raster layer သည် file အခြေခံသော အမျိုးအစားဖြစ်ရပါမည်။ File မဟုတ်သော raster layer ကိုအသုံးပြုလျှင် အမှား/ပြဿနာ တစ်ခုခု ဖြစ်စေနိုင်ပါသည်။
   *  - **Create also .prj file** (**.prj file ကိုဖန်တီးခြင်း**)
      - ``PRJ_FILE_CREATE``
      - [boolean]

        Default: False
      - ၎င်းကိုဖွင့်ထားပေးလျှင် projection သတင်းအချက်အလက်ပါသော :file:`.prj` file တစ်ခုကိုလည်း ဖန်တီးပေးပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   *  - **World file**
      - ``WORLD_FILE``
      - [file]
      - Raster file အတွက် transformation parameters (ပြောင်းလဲခြင်း parameter များ) ပါသော :file:`.wld` extension ဖြင့် စာသား file ။
   *  - **ESRI Shapefile prj file**
      - ``PRJ_FILE``
      - [file]
      - CRS ကိုဖော်ပြသော :file:`.prj` extension ဖြင့် စာသား file ။ :guilabel:`Create also .prj file` ကို False (အမှား) အဖြစ်ထားလျှင် ``None`` ဖြစ်ပါလိမ့်မည်။

Python code
............

**Algorithm ID**: ``gdal:extractprojection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalwarpreproject:

Warp (reproject) (Projection တစ်ခုမှ တစ်ခုသို့ပြောင်းခြင်း)
------------------------------------------------------------

Raster layer တစ်ခုကို အခြား Coordinate Reference System (CRS) တစ်ခုသို့ပြောင်းလဲပေးပါသည်။ ထွက်လာမည့် file ၏ resolution နှင့် resolution ပြင်ဆင်ခြင်း နည်းလမ်းများကို ရွေးချယ်နိုင်ပါသည်။

Algorithm ကို `GDAL warp utility <https://gdal.org/programs/gdalwarp.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Projections`

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
     - Projection ပြောင်းလဲမည့် input raster layer
   * - **Source CRS** (**ရင်းမြစ် CRS**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SOURCE_CRS``
     - [crs]
     - Input raster layer ၏ CRS ကိုသတ်မှတ်ပေးပါသည်။
   * - **Target CRS** (**ဖြစ်စေလိုသော CRS**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_CRS``
     - [crs]

       Default: ``EPSG:4326``
     - Output layer ၏ CRS
   * - **Resampling method to use** (**အသုံးပြုမည့် resolution ပြင်ဆင်ခြင်း နည်းလမ်း**)
     - ``RESAMPLING``
     - [enumeration]

       Default: 0
     - Resolution ပြင်ဆင်ခြင်းနည်းလမ်းအတွက် အသုံးပြုမည့် pixel တန်ဖိုး။ ရွေးချယ်စရာများမှာ - 

       * 0 --- Nearest neighbour
       * 1 --- Bilinear
       * 2 --- Cubic
       * 3 --- Cubic spline
       * 4 --- Lanczos windowed sinc
       * 5 --- Average
       * 6 --- Mode
       * 7 --- Maximum
       * 8 --- Minimum
       * 9 --- Median
       * 10 --- First quartile
       * 11 --- Third quartile
   * - **Nodata value for output bands** (**Output band များအတွက် Nodata တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: None
     - Output band များအတွက် nodata တန်ဖိုး သတ်မှတ်ပေးပါသည်။ တန်ဖိုးသတ်မှတ်မထားလျှင် nodata တန်ဖိုးများကို မူရင်း dataset မှ ကူးယူပါမည်။
   * - **Output file resolution in target georeferenced units** (**Target Georeference ပြုလုပ်ထားသော unit များဖြင့် output file ၏ resolution**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_RESOLUTION``
     - [number]

       Default: None
     - Projection ပြောင်းလဲထားသော ရလာဒ်၏ output file resolution ကို သတ်မှတ်ပေးပါသည်။
   * - **Reprojected** (**Projection ပြောင်းလဲထားသော**)
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
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 0
     - Output raster file ၏ format ကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types_extended**
          :end-before: **end_raster_data_types_extended**

   * - **Georeferenced extents of output file to be created** (**ဖန်တီးမည့် output file ၏ georeference လုပ်ထားသော အကျယ်အဝန်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_EXTENT``
     - [extent]

     - ဖန်တီးမည့် output file ၏ georeference လုပ်ထားသော အကျယ်အဝန်းကို သတ်မှတ်ပေးပါသည် (သာမန်အားဖြင့် :guilabel:`Target CRS` ထဲတွင်ရှိပါသည်။ သီးခြားသတ်မှတ်ထားလျှင် :guilabel:`CRS of the target raster extent` ထဲတွင်ရှိပါသည်)။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **CRS of the target raster extent** (**ဖြစ်စေလိုသော raster အကျယ်အဝန်း၏ CRS**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_EXTENT_CRS``
     - [crs]
     - Output file ၏ အကျယ်အဝန်းအတွက် အသုံးပြုထားသော ကိုဩဒိနိတ်များကို နားလည်စေရန် CRS ကိုသတ်မှတ်ပေးပါသည်။ Output dataset ၏ ဖြစ်စေလိုသော CRS နှင့် မရှုပ်ထွေးရန်လိုအပ်ပါသည်။ ၎င်းသည်သုံးရလွယ်ကူပါသည်၊ ဥပမာ- output ကိုဩဒိနိတ်ကို geodetic long/lat CRS တစ်ခုဖြင့် သိပါသော်လည်း projected ကိုဩဒိနိတ်စနစ်တစ်ခုဖြင့် ရလာဒ်ကို အလိုရှိသောအခါ။
   * - **Use multithreaded warping implementation** (**Multithreaded warpping လုပ်ဆောင်ချက်ကိုအသုံးပြုခြင်း**)
     - ``MULTITHREADING``
     - [boolean]

       Default: False
     - ဓာတ်ပုံအစုများကို လုပ်ဆောင်ရန် thread နှစ်ခုကို အသုံးပြုပြီး input/output လုပ်ဆောင်မှုများကို တပြိုင်တည်းလုပ်ဆောင်ပါသည်။ တွက်ထုတ်ခြင်းသည် multithread မဟုတ်ပါ။
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
   * - **Reprojected** (**Projection ပြောင်းလဲထားသော**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Projection ပြောင်းလဲထားသော output raster layer

Python code
............

**Algorithm ID**: ``gdal:warpreproject``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
