Raster miscellaneous (Raster ဆိုင်ရာ သောင်းပြောင်းထွေလာ)
=========================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _gdaloverviews:

Build overviews (pyramids)  (ခြုံငုံကြည့်ရှုနိုင်သော overview များ တည်ဆောက်ခြင်း (pyramid များ))
-------------------------------------------------------------------------------------------------

Raster layer များ ပုံဖော်ကြည့်ပြသချိန်ကို မြန်ဆန်စေရန် ခြုံငုံကြည့်ရှုနိုင်သော overview pyramid များကိုဖန်တီးနိုင်ပါသည်။ Overview များဆိုသည်မှာ zoom level ပေါ်မူတည်ပြီး QGIS မှ အသုံးပြုသော မူရင်း data ၏ resolution နိမ့်သော data မိတ္တူများဖြစ်ကြပါသည်။

Algorithm ကို `GDAL addo utility <https://gdal.org/programs/gdaladdo.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Miscellaneous`

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Remove all existing overviews** (**ရှိနေပြီးသား overview များကို ဖယ်ပစ်ခြင်း**)
     - ``CLEAN``
     - [boolean]

       Default: False
     - Raster မှရှိနေပြီးသား overview များကိုဖယ်ပစ်ပါသည်။ သာမန်အားဖြင့် ၎င်းတို့ကို ဖယ်ထုတ်မပစ်ပါ။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overview levels** (**Overview အဆင့်များ**)
     - ``LEVELS``
     - [string]

       Default: '2 4 8 16'
     - Input raster layer ၏ မူရင်း resolution ဖြင့်တွက်ထုတ်ထားသော overview level အရေအတွက်ကို သတ်မှတ်ပေးပါသည်။ ဘာမှ သတ်မှတ်မပေးထားလျှင် သာမန်အားဖြင့် 4 levels ကို ယူသုံးပါလိမ့်မည်။
   * - **Resampling method** (**Resolution ပြင်ဆင်ခြင်း နည်းလမ်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``RESAMPLING``
     - [enumeration]

       Default: 0
     - သတ်မှတ်ထားသော resolution ပြင်ဆင်ခြင်း နည်းလမ်းဖြင့် overview ကိုတွက်ချက်ပေးပါသည်။ ဖြစ်နိုင်သော resolution ပြင်ဆင်ခြင်း နည်းလမ်းများမှာ -

       * 0 -- Nearest Neighbour (``nearest``)
       * 1 -- Average (``average``)
       * 2 -- Gaussian (``gauss``)
       * 3 -- Cubic Convolution (``cubic``)
       * 4 -- B-Spline Convolution (``cubicspline``)
       * 5 -- Lanczos Windowed Sinc (``lanczos``)
       * 6 -- Average MP (``average_mp``)
       * 7 -- Average in Mag/Phase Space (``average_magphase``)
       * 8 -- Mode (``mode``)
   * - **Overviews format** (**Overview များ၏ format**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FORMAT``
     - [enumeration]

       Default: 0
     - Overview များကို GTiff သို့မဟုတ် ERDAS Imagine file အဖြစ် အတွင်းထဲတွင် သို့မဟုတ် အပြင်ဘက်တွင် သိမ်းဆည်းထားနိုင်ပါသည်။ သာမန်အားဖြင့် overview များကို output raster ထဲတွင် သိမ်းဆည်းထားပါသည်။ ဖြစ်နိုင်သော format နည်းလမ်းများမှာ-

       * 0 -- Internal (if possible)
       * 1 -- External (GTiff .ovr)
       * 2 -- External (ERDAS Imagine .aux)
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
   * - **Pyramidized** (**ပိရမစ်ဖန်တီးထားသော**)
     - ``OUTPUT``
     - [raster]
     - Overview များဖြင့် output raster layer

Python code
............

**Algorithm ID**: ``gdal:overviews``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalbuildvirtualraster:

Build virtual raster (ပညတ်ချက်မဲ့ raster တစ်ခုဖန်တီးခြင်း)
-----------------------------------------------------------

GDAL မှလုပ်ဆောင်ပေးနိုင်သော input raster များစာရင်း၏ mosaic (ပုံအများကိုပေါင်းစပ်ထားခြင်း) တစ်ခုဖြစ်သော VRT (Virtual Dataset) တစ်ခုကို ဖန်တီးပေးပါသည်။ Mosaic တစ်ခုဖြင့် raster file များစွာကိုပေါင်းနိုင်ပါသည်။

Algorithm ကို `GDAL buildvrt utility <https://gdal.org/programs/gdalbuildvrt.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Miscellaneous`

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``INPUT``
     - [raster] [list]
     - GDAL မှလုပ်ဆောင်ပေးနိုင်သော raster layer များ
   * - **Resolution** (**ကြည်လင်ပြတ်သားမှု**)
     - ``RESOLUTION``
     - [enumeration]

       Default: 0
 
     - Mosaic ၏ output resolution ။ သာမန်အားဖြင့် raster file များ၏ပျမ်းမျှ resolution ကိုရွေးချယ်ပါလိမ့်မည်။ ရွေးချယ်စရာများမှာ -

       * 0 --- Average (``average``) (ပျမ်းမျှ)
       * 1 --- Highest (``highest``) (အမြင့်ဆုံး)
       * 2 --- Lowest (``lowest``) (အနိမ့်ဆုံး)
   * - **Place each input file into a separate band** (**Input file တစ်ခုချင်းစီကို သီးခြား band တစ်ခုစီထဲတွင် ထားခြင်း**)
     - ``SEPARATE``
     - [boolean]

       Default: False
     - 'True' ကိုရွေးချယ်ထားလျှင် raster file တစ်ခုချင်းစီသည် VRT band ထဲရှိ သီးခြားထပ်ထားသော band တစ်ခုထဲသို့သွားရန် သွားရန်သတ်မှတ်ပေးနိုင်ပါသည်။
   * - **Allow projection difference** (**Projection ခြားနားချက်ကို ခွင့်ပြုပေးခြင်း**)
     - ``PROJ_DIFFERENCE``
     - [boolean]

       Default: False
     - Input raster layer များ၏ projection မှရယူထားသော projection အမျိုးမျိုးကို output band တွင်ရရှိနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။
   * - **Virtual**
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
   * - **Add alpha mask band to VRT when source raster has none** (**ရင်းမြစ် raster သည်မည်သည့် band မှမရှိသောအခါ VRT တွင် alpha mask band ထည့်ပေါင်းခြင်း**)
     - ``ADD_ALPHA``
     - [boolean]

       Default: False
     - ရင်းမြစ် raster သည်မည်သည့် band မှမရှိသောအခါ VRT တွင် alpha mask band ထည့်ပေါင်းခြင်း။
   * - **Override projection for the output file** (**Output file အတွက် projection ကို အစားထိုးပြင်ဆင်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ASSIGN_CRS``
     - [crs]

       Default: None
     - Output file အတွက် projection ကို အစားထိုးပြင်ဆင်ပေးပါသည်။ Reprojection (Projection တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲခြင်း) မလုပ်ဆောင်ပါ။
   * - **Resampling algorithm** (**Resolution ပြင်ဆင်ခြင်း algorithm**)
     - ``RESAMPLING``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် resolution ပြင်ဆင်သည့် algorithm ။ ရွေးချယ်စရာ နည်းလမ်းများမှာ - 

       * 0 --- Nearest Neighbour (``nearest``)
       * 1 --- Bilinear (``bilinear``)
       * 2 --- Cubic Convolution (``cubic``)
       * 3 --- B-Spline Convolution (``cubicspline``)
       * 4 --- Lanczos Windowed Sinc (``lanczos``)
       * 5 --- Average (``average``)
       * 6 --- Mode (``mode``)
   * - **Nodata value(s) for input bands (space separated)** (**Input band များအတွက် nodata တန်ဖိုးများ (space ဖြင့်ခြားထားသော)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SRC_NODATA``
     - [string]

       Default: None
     - Input band များအတွက် space ဖြင့်ခြားထားသော Nodata တန်ဖိုးများ
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

   * - **Virtual**
     - ``OUTPUT``
     - [raster]
     - Output raster layer

Python code
............

**Algorithm ID**: ``gdal:buildvirtualraster``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgdal2tiles:

gdal2tiles
-----------

Tile (အကွက်) အသေးများနှင့် metadata တို့ပါဝင်သော လမ်းကြောင်းတစ်ခုကိုဖန်တီးပေးပါသည်၊ `OSGeo Tile Map Service Specification <https://wiki.osgeo.org/wiki/Tile_Map_Service_Specification>`_ အတိုင်းလုပ်ဆောင်ပါသည်။ `OpenGIS Web Map Tile Service Implementation Standard <https://www.ogc.org/standards/wmts>`_ တွင်လည်းကြည့်ရှုပါ။ Google Maps၊ OpenLayers နှင့် Leaflet များကိုအခြေခံထားသော viewer (ကြည့်ရှုနိုင်သည့်အရာ) များဖြင့် ရိုးရှင်းသော web စာမျက်နှာများကိုလည်း ဖန်တီးပေးပါသည်။ Web browser ထဲတွင် မိမိ၏မြေပုံကို on-line တွင်စူးစမ်းလေ့လာရန် web server ထဲသို့ ဖန်တီးထားသော လမ်းကြောင်းတစ်ခု ထည့်သွင်းပေးရန်သာ လိုအပ်ပါသည်။

အသုံးပြုနိုင်သော မြေပုံသည် ``EPSG:4326`` projection ကိုအသုံးပြုလျှင် ယခု algorithm သည် Google Earth (KML SuperOVerlay) အတွက် မဖြစ်မနေလိုအပ်သော medadata ကိုလည်း ဖန်တီးပေးပါသည်။

Tile ဖန်တီးစဉ်တွင် ESRI world file များနှင့် ထည့်မြှုပ်ထားသော georeferencing ကိုအသုံးပြုပါသည်။ သို့သော် ဓာတ်ပုံတစ်ပုံကို ကောင်းကောင်းမွန်မွန် georeference လုပ်ထားခြင်းမရှိပဲလည်း publish (ဖြန့်ဝေ) လုပ်နိုင်ပါသည်။


Algorithm ကို `GDAL gdal2tiles utility <https://gdal.org/programs/gdal2tiles.html>`_ မှ ရယူပါသည်။

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``INPUT``
     - [raster]
     - GDAL မှလုပ်ဆောင်ပေးနိုင်သော raster layer
   * - **Tile cutting profile**
     - ``PROFILE``
     - [enumeration]

       Default: 0
     - အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       * 0 --- Mercator (``mercator``)
       * 1 --- Geodetic (``geodetic``)
       * 2 --- Raster (``raster``)

   * - **Zoom levels to render** (**ပုံဖော်ကြည့်ရှုရန် zoom level များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ZOOM``
     - [string]

       Default: ''
     -
   * - **Web viewer to generate** (**ဖန်တီးရယူရန် Web viewer**)
     - ``VIEWER``
     - [enumerate]

       Default: 0
     - အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       * 0 --- All (``all``)
       * 1 --- GoogleMaps (``google``)
       * 2 --- OpenLayers (``openlayers``)
       * 3 --- Leaflet (``leaflet``)
       * 4 --- None (``none``)

   * - **Title of the map** (**မြေပုံ၏ ခေါင်းစဉ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TITLE``
     - [string]

       Default: ''
     -
   * - **Copyright of the map** (**မြေပုံ၏ မူပိုင်ခွင့်**)
     - ``COPYRIGHT``
     - [string]

       Default: ''
     -

   * - **Output directory** (**Output သိမ်းဆည့်မည့်နေရာ**)
     - ``OUTPUT``
     - [folder]

       Default: ``[Save to temporary folder] ([ယာယီ folder ထဲတွင် သိမ်းဆည်းပါ])``
     - Tile များအတွက် output folder ကိုသတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types**
          :end-before: **end_directory_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Resampling method** (**Resolution ပြင်ဆင်ခြင်းနည်းလမ်း**)
     - ``RESAMPLING``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် resolution ပြင်ဆင်ခြင်း algorithm။ ရွေးချယ်စရာများမှာ - 

       * 0 --- Average (``average``)
       * 1 --- Nearest neighbour (``near``)
       * 2 --- Bilinear (``bilinear``)
       * 3 --- Cubic (``cubic``)
       * 4 --- Cubic spline (``cubicspline``)
       * 5 --- Lanczos Windowed sinc (``lanczos``)
       * 6 --- Antialias (``antialias``)

   * - **The spatial reference system used for the source input data** (**ရင်းမြစ် input data အတွက် အသုံးပြုမည့် spatial reference system**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SOURCE_CRS``
     - [crs]

       Default: None
     -
   * - **Transparency value to assign to the input data** (**Input data တွင်သတ်မှတ်မည့် ဖောက်ထွင်းမြင်ရနိုင်မှုတန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA``
     - [number]

       Default: 0.0
     -
   * - **URL address where the generated tiles are going to be published** (**ဖန်တီးထားသော tile များကိုဖြန့်ဝေပေးမည့် URL လိပ်စာ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``URL``
     - [string]

       Default: ''
     -
   * - **Google Maps API key (http://code.google.com/apis/maps/signup.html)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GOOGLE_KEY``
     - [string]

       Default: ''
     - သင့် Google maps API key
   * - **Bing Maps API key (https://www.bingmapsportal.com/)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BING_KEY``
     - [string]

       Default: ''
     - သင့် Bing maps API key.
   * - **Generate only missing files** (**ပျောက်နေသော file များကိုသာ ဖန်တီးပါ**)
     - ``RESUME``
     - [boolean]

       Default: False
     -
   * - **Generate KML for Google Earth** (**Google Earth အတွက် KML ကိုဖန်တီးခြင်း**)
     - ``KML``
     - [boolean]

       Default: False
     -
   * - **Avoid automatic generation of KML files for EPSG:4326** (**EPSG:4326 အတွက် KML file များအလိုအလျှောက်ဖန်တီးမှုကို ရှောင်ရှားခြင်း**)
     - ``NO_KML``
     - [boolean]

       Default: False
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
   * - **Output directory** (**Output သိမ်းထားမည့်နေရာ**)
     - ``OUTPUT``
     - [folder]
     - Output folder (Tile များအတွက်)

Python code
............

**Algorithm ID**: ``gdal:gdal2tiles``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalmerge:

Merge (ပေါင်းခြင်း)
--------------------

Raster file များကို ရိုးရှင်းစွာ ပေါင်းပေးပါသည်။ Input raster တစ်ခုမှ pseudocolor table ကိုအသုံးပြုနိုင်ပြီး output raster အမျိုးအစားကို သတ်မှတ်နိုင်ပါသည်။ ဓာတ်ပုံများအားလုံးသည် ကိုဩဒိနိတ်စနစ် တူရပါမည်။

Algorithm ကို `GDAL merge utility <https://gdal.org/programs/gdal_merge.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Miscellaneous`

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``INPUT``
     - [raster] [list]
     - ထည့်သွင်းအသုံးပြုသော raster layer များ
   * - **Grab pseudocolor table from first layer** (**ပထမ layer မှ pseudocolor ဇယားကို ယူပါ**)
     - ``PCT``
     - [boolean]

       Default: False
     - အရောင်ခြယ်သခြင်းအတွက် အသုံးပြုမည့် ပထမ layer မှ pseudocolor ဇယား
   * - **Place each input file into a separate band** (**Input file တစ်ခုချင်းစီကို သီးခြား band တစ်ခုစီတွင် ထားခြင်း**)
     - ``SEPARATE``
     - [boolean]

       Default: False
     - Input file တစ်ခုချင်းစီကို သီးခြား band တစ်ခုစီတွင် ထားပေးပါသည်
   * - **Output data type** (**Output data အမျိုးအစား**)
     - ``DATA_TYPE``
     - [enumeration]

       Default: 5
     - Output raster file ၏ format ကိုသတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

   * - **Merged** (**ပေါင်းထားသော**)
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
   * - **Input pixel value to treat as "nodata"** (**"nodata" အဖြစ်လုပ်ဆောင်မည့် Input pixel တန်ဖိုး**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA_INPUT``
     - [number]

       Default: None
     - ဤ pixel တန်ဖိုးနှင့်တူသော ပေါင်းစပ်မည့် file များမှ pixel များကို လျစ်လျူရှုပေးပါသည်
   * - **Assign specified "nodata" value to output** (**Output တွင် "nodata" တန်ဖိုးကို သတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NODATA_OUTPUT``
     - [number]

       Default: None
     - Output band များတွင် nodata တန်ဖိုးကို သတ်မှတ်ပေးပါသည်
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
   * - **Merged** (**ပေါင်းထားသော**)
     - ``OUTPUT``
     - [raster]
     - Output raster layer

Python code
............

**Algorithm ID**: ``gdal:merge``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalpansharp:

Pansharpening (ကြည်လင်ပြတ်သားမှု ကောင်းမွန်အောင်လုပ်ဆောင်ခြင်း)
----------------------------------------------------------------

Pan-sharpening လုပ်ဆောင်မှုကို ဆောင်ရွက်ပေးပါသည်။ GeoTIFF ကဲ့သို့သော "classic" output dataset တစ်ခုကိုဖန်တီးနိုင်ပါသည် သို့မဟုတ် pan-sharpening လုပ်ဆောင်မှုကို ဖော်ပြသော VRT dataset တစ်ခုကို ဖန်တီးနိုင်ပါသည်။

`GDAL Pansharpen <https://gdal.org/programs/gdal_pansharpen.html>`_ တွင်ကြည့်ပါ။

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
   * - **Spectral dataset** (**ရောင်စဉ်လှိုင်း dataset**)
     - ``SPECTRAL``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော (spectral) raster layer
   * - **Panchromatic dataset**
     - ``PANCHROMATIC``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော (panchromatic) raster layer
   * - **Output**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output (ကြည်လင်ပြတ်သားအောင် sharpen လုပ်ထားသော) raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

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
   * - **Resampling algorithm** (**Resolution ပြင်ဆင်ခြင်း algorithm**)
     - ``RESAMPLING``

     - [enumeration]

       Default: 2
     - အသုံးပြုမည့် resolution ပြင်ဆင်သည့် algorithm ။ ရွေးချယ်စရာ နည်းလမ်းများမှာ - 

       * 0 --- Nearest Neighbour (``nearest``)
       * 1 --- Bilinear (``bilinear``)
       * 2 --- Cubic (``cubic``)
       * 3 --- Cubic Spline (``cubicspline``)
       * 4 --- Lanczos Windowed Sinc (``lanczos``)
       * 5 --- Average (``average``)

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
   * - **Output**
     - ``OUTPUT``
     - [raster]
     - Output (ကြည်လင်ပြတ်သားအောင် sharpen လုပ်ထားသော) raster layer

Python code
............

**Algorithm ID**: ``gdal:pansharp``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalrastercalculator:

Raster calculator (Raster ဂဏန်းတွက်စက်)
----------------------------------------

Numpy syntax အသုံးပြု၍ command ဖြင့်ရေးရသော raster calculator ။ Logical သင်္ကေတများ (ဥပမာ- >) အပါအဝင် (+) ၊ (-) ၊ (\*)၊ နှင့် (/) ကဲ့သို့သော numpy array များမှ လုပ်ဆောင်ပေးနိုင်သော အခြေခံ arithmetic ကိုမဆို အသုံးပြုပါသည်။ Input raster များအားလုံးသည် တူညီသော အကျယ်အဝန်းရှိရပါမည်၊ သို့သော် projection စစ်ဆေးမှုကိုတော့ လုပ်ဆောင်မည်မဟုတ်ပါ။

`GDAL Raster Calculator utility docs <https://gdal.org/programs/gdal_calc.html>`_ တွင်ကြည့်ပါ။

.. seealso:: :ref:`qgisrastercalculator`

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
   * - **Input layer A** (**ထည့်သွင်းအသုံးပြုသော layer A**)
     - ``INPUT_A``
     - [raster]
     - ပထမဆုံး ထည့်သွင်းအသုံးပြုသော raster layer (မဖြစ်မနေထည့်သွင်းရန်လိုအပ်ပါသည်)
   * - **Number of raster band for A** (**A အတွက် raster band နံပါတ်**)
     - ``BAND_A``
     - [raster band]
     - Input layer A အတွက် band (မဖြစ်မနေထည့်သွင်းရန်လိုအပ်ပါသည်)
   * - **Input layer B** (**ထည့်သွင်းအသုံးပြုသော layer B**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT_B``
     - [raster]

       Default: None
     - ဒုတိယ ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Number of raster band for B** (**B အတွက် raster band နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BAND_B``
     - [raster band]
     - Input layer B အတွက် band
   * - **Input layer C** (**ထည့်သွင်းအသုံးပြုသော layer C**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT_C``
     - [raster]

       Default: None
     - တတိယ ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Number of raster band for C** (**C အတွက် raster band နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BAND_C``
     - [raster band]
     - Input layer C အတွက် band
   * - **Input layer D** (**ထည့်သွင်းအသုံးပြုသော layer D**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT_D``
     - [raster]

       Default: None
     - စတုတ္ထ ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Number of raster band for D** (**D အတွက် raster band နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BAND_D``
     - [raster band]
     - Input layer D အတွက် band
   * - **Input layer E** (**ထည့်သွင်းအသုံးပြုသော layer E**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT_E``
     - [raster]

       Default: None
     - ပဥ္စမ ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Number of raster band for E** (**E အတွက် raster band နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BAND_E``
     - [raster band]
     - Input layer E အတွက် band
   * - **Input layer F** (**ထည့်သွင်းအသုံးပြုသော layer F**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT_F``
     - [raster]
     - ဆဌမ ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Number of raster band for F** (**F အတွက် raster band နံပါတ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BAND_F``
     - [raster band]

       Default: None
     - Input layer F အတွက် band
   * - **Calculation in gdalnumeric syntax using +-/\* or any numpy array functions (i.e. logical_and())** (**(+-/\*) သို့မဟုတ် numpy array functions (ဥပမာ- logical_and()) ကိုအသုံးပြုပြီး gdalnumeric syntax ထဲတွင် တွက်ချက်ခြင်း**)
     - ``FORMULA``
     - [string]

       Default: ''
     - တွက်ချက်ခြင်း formula ။ ဥပမာများမှာ -

       * ``A*(A>0)`` --- A ၏တန်ဖိုးသည် 0 ထက်ကြီးလျှင် raster A ၏ တန်ဖိုးကို output ထုတ်ပေးပါသည်။ ထိုသို့မဟုတ်လျှင် 0 ကို output ထုတ်ပေးမည်ဖြစ်သည်။
       * ``A*(A>0 and A>B)``--- A ၏တန်ဖိုးသည် 0 ထက်ပိုကြီးပြီး B ၏တန်ဖိုးထက်လည်းပိုကြီးနေလျှင် ထို A ၏ တန်ဖိုးကို output ထုတ်ပေးပါသည်။ ထိုသို့မဟုတ်လျှင် 0 ကို output ထုတ်ပေးမည်ဖြစ်သည်။
       * ``A*logical_or(A<=177,A>=185)`` --- A <= 177 သို့မဟုတ် A >= 185 ဖြစ်လျှင် A ၏ တန်ဖိုးကို output ထုတ်ပေးပါသည်။ ထိုသို့မဟုတ်လျှင် 0 ကို output ထုတ်ပေးမည်ဖြစ်သည်။
       * ``sqrt(A*A+B*B)`` --- A နှစ်ထပ်ကိန်းတန်ဖိုးနှင့် B နှစ်ထပ်ကိန်းတန်ဖိုးများ၏ ပေါင်းလာဒ်၏ square root တန်ဖိုးကို ထုတ်ပေးပါသည်။

   * - **Set output nodata value** (**Output nodata တန်ဖိုးကို သတ်မှတ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``NO_DATA``
     - [number]

       Default: None
     - Nodata အတွက်အသုံးပြုမည့် တန်ဖိုး
   * - **Output extent** (**Output အကျယ်အဝန်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``INPUT``
     - [extent]

     - Output raster ၏ ကိုယ်တိုင်သတ်မှတ်သော အကျယ်အဝန်း။ GDAL 3.3 အထက်ဖြင့်သာလုပ်ဆောင်ပါသည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Output raster type** (**Output raster အမျိုးအစား**)
     - ``RTYPE``
     - [enumeration]

       Default: 5
     - Output raster file ၏ data အမျိုးအစားကို သတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရာများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

   * - **Calculated** (**တွက်ချက်ထားသော**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output (တွက်ထုတ်ထားသော) raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

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
   * - **Calculated** (**တွက်ထုတ်ထားသော**)
     - ``OUTPUT``
     - [raster]
     - Output (တွက်ထုတ်ထားသော) raster layer

Python code
............

**Algorithm ID**: ``gdal:rastercalculator``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalgdalinfo:

Raster သတင်းအချက်အလက် (Raster information)
-------------------------------------------

Gdalinfo program သည် GDAL မှလုပ်ဆောင်ပေးနိုင်သော raster dataset အကြောင်း သတင်းအချက်အလက်မျိုးစုံကို စာရင်းပြုစုပေးပါသည်။

Algorithm ကို `GDAL info utility <https://gdal.org/programs/gdalinfo.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Miscellaneous`

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Force computation of the actual min/max values for each band** (**Band တစ်ခုချင်းစီအတွက် တကယ်လက်ရှိ အနည်းဆုံး/အများဆုံး တန်ဖိုးများတွက်ချက်ခြင်းကို တွန်းအားပေး လုပ်ဆောင်ခြင်း**)
     - ``MIN_MAX``
     - [boolean]

       Default: False
     - Dataset ထဲရှိ band တစ်ခုချင်းစီအတွက် တကယ်လက်ရှိ အနည်းဆုံး/အများဆုံး တန်ဖိုးများတွက်ချက်ခြင်းကို တွန်းအားပေး လုပ်ဆောင်ပါသည်။
   * - **Read and display image statistics (force computation if necessary)** (**ဓာတ်ပုံစာရင်းအင်းကိန်းဂဏန်းများကို ဖတ်ခြင်းနှင့် ပြသခြင်း (လိုအပ်လျှင် တွန်းအားပေးတွက်ချက်နိုင်ပါသည်)**)
     - ``STATS``
     - [boolean]

       Default: False
     - ဓာတ်ပုံစာရင်းအင်းကိန်းဂဏန်းများကို ဖတ်ခြင်းနှင့် ပြသခြင်းများ လုပ်ဆောင်ပေးပါသည်။ ဓာတ်ပုံတစ်ခုထဲတွင် စာရင်းအင်းကိန်းဂဏန်းများကို သိမ်းဆည်းမထားလျှင် တွန်းအားပေးတွက်ချက်ခြင်းကို လုပ်ဆောင်ပါသည်။
   * - **Suppress GCP info** (**GCP သတင်းအချက်အလက်ကို ချုံ့ထားခြင်း**)
     - ``NO_GCP``
     - [boolean]

       Default: False
     - Ground control point (မြေပြင်ထိန်းချုပ်မှတ်) များစာရင်း ပြသခြင်းကို ချုံ့ထားပေးပါသည်။ L1B AVHRR သို့မဟုတ် HDF4 MODIS ကဲ့သို့ထောင်ချီသော GCP ပမာဏအများကြီးပါသော dataset များအတွက် အသုံးဝင်ပါသည်။
   * - **Suppress metadata info** (**metdata သတင်းအချက်အလက်ကို ချုံ့ထားခြင်း**)
     - ``NO_METADATA``
     - [boolean]

       Default: False
     - Metadata ပြသခြင်းကို ချုံ့ထားပေးပါသည်။ အချို့သော dataset များသည် metadata စာသားများ များစွာပါဝင်နိုင်ပါသည်။
   * - **Layer information** (**Layer သတင်းအချက်အလက်**)
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output အတွက် HTML file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

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
   * - **Layer information** (**Layer သတင်းအချက်အလက်**)
     - ``OUTPUT``
     - [html]
     - Input raster layer အကြောင်း သတင်းအချက်အလက်များပါဝင်သော HTML file

Python code
............

**Algorithm ID**: ``gdal:gdalinfo``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalretile:

Retile (Tile ပြန်လုပ်ခြင်း)
----------------------------

Input tile များအစုတစ်ခုကို tile များပြန်လုပ်ပေးပါသည်။ Input tile များအားလုံးကို ကိုဩဒိနိတ်စနစ်တစ်ခုတည်းဖြင့် georeference လုပ်ရမည်ဖြစ်ပြီး band အရေအတွက်လည်း ကိုက်ညီရပါမည်။ Pyramid level များကို လိုအပ်လျှင် ဖန်တီးထားနိုင်ပါသည်။

Algorithm ကို `GDAL Retile utility <https://gdal.org/programs/gdal_retile.html>`_ မှ ရယူပါသည်။

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
   * - **Input files** (**ထည့်သွင်းအသုံးပြုသော file များ**)
     - ``INPUT``
     - [raster] [list]
     - ထည့်သွင်းအသုံးပြုသော raster file များ
   * - **Tile width** (**Tile အကျယ်**)
     - ``TILE_SIZE_X``
     - [number]

       Default: 256
     - Pixel ဖြင့် tile များ၏အကျယ် (အနည်းဆုံး 0)
   * - **Tile height** (**Tile အမြင့်**)
     - ``TILE_SIZE_Y``
     - [number]

       Default: 256
     - Pixel ဖြင့် tile များ၏အမြင့် (အနည်းဆုံး 0)
   * - **Overlap in pixels between consecutive tiles** (**ကပ်လျှက်ရှိသော tile နှစ်ခုကြား pixel များကိုထပ်ခြင်း**)
     - ``OVERLAP``
     - [number]

       Default: 0
     -
   * - **Number of pyramid levels to build** (**တည်ဆောက်ရမည့် pyramid level အရေအတွက်**)
     - ``LEVELS``
     - [number]

       Default: 1
     - အနည်းဆုံး- 0
   * - **Output directory** (**Output သိမ်းထားမည့်နေရာ**)
     - ``OUTPUT``
     - [folder]

       Default: ``[Save to temporary folder] ([ယာယီ folder ထဲတွင် သိမ်းဆည်းပါ])``
     - Tile များအတွက် output folder ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types**
          :end-before: **end_directory_output_types**

   * - **CSV file containing the tile(s) georeferencing information** (**Tile များကို georeference ပြုလုပ်သော အချက်အလက်များပါဝင်သည့် CSV file**)
     - ``OUTPUT_CSV``
     - [file]

       Default: ``[Skip output] ([Output များကိုကျော်ပစ်ပါ])``
     - Tile များအတွက် output file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

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
   * - **Source coordinate reference system** (**ရင်းမြစ် ကိုဩဒိနိတ်ရည်ညွှန်းစနစ်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SOURCE_CRS``
     - [crs]

       Default: None
     -
   * - **Resampling method** (**Resolution ပြင်ဆင်ခြင်း နည်းလမ်း**)
     - ``RESAMPLING``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် resolution ပြင်ဆင်သည့် algorithm ။ ရွေးချယ်စရာ နည်းလမ်းများမှာ - 

       * 0 --- Nearest Neighbour (``nearest``)
       * 1 --- Bilinear (``bilinear``)
       * 2 --- Cubic (``cubic``)
       * 3 --- Cubic Spline (``cubicspline``)
       * 4 --- Lanczos Windowed Sinc (``lanczos``)

   * - **Column delimiter used in the CSV file** (**CSV file ထဲတွင် အသုံးပြုထားသော column ခွဲခြားကန့်သတ်သည့်အရာ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DELIMITER``
     - [string]

       Default: ';'
     - Tile များ georeferencing လုပ်ထားသော အချက်အလက်များပါဝင်သည့် CSV file ထဲတွင် အသုံးပြုသည့် delimiter
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

       Default: 5
     - Output raster file ၏ format ကိုသတ်မှတ်ပေးပါသည်။ ရွေးချယ်စရားများမှာ -

       .. include:: ../algs_include.rst
          :start-after: **raster_data_types**
          :end-before: **end_raster_data_types**

   * - **Build only the pyramids** (**Pyramid များကိုသာ တည်ဆောက်ခြင်း**)
     - ``ONLY_PYRAMIDS``
     - [boolean]

       Default: False
     -
   * - **Use separate directory for each tile row** (**Tile row တစ်ခုချင်းစီအတွက် သီးခြား လမ်းကြောင်းကို အသုံးပြုခြင်း**)
     - ``DIR_FOR_ROW``
     - [boolean]

       Default: False
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
   * - **Output directory** (**Output သိမ်းဆည်းရန်နေရာ**)
     - ``OUTPUT``
     - [folder]
     - Tile များအတွက် output folder
   * - **CSV file containing the tile(s) georeferencing information** (**Tile များကို georeference လုပ်ထားသော သတင်းအချက်အလက်များပါဝင်သည့် CSV file**)
     - ``OUTPUT_CSV``
     - [file]
     - Tile များအတွက် georeferencန လုပ်ထားသော သတင်းအချက်အလက်များပါဝင်သည့် CSV file

Python code
............

**Algorithm ID**: ``gdal:retile``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaltileindex:

Tile index (Tile အညွှန်းကိန်း)
-------------------------------

Input raster file တစ်ခုချင်းစီအတွက် file နာမည်ပါဝင်သော attribute တစ်ခုနှင့် raster ကို အနားသတ်ပေးသော polygon geometry တစ်ခုတို့ပါဝင်သော vector layer တစ်ခုဖန်တီးပေးပါသည်။ ဤ output သည် raster tileindex တစ်ခုအဖြစ် Mapserver နှင့် အသုံးပြုရန် သင့်တော်ပါသည်။

Algorithm ကို `GDAL Tile Index utility <https://gdal.org/programs/gdaltindex.html>`_ မှ ရယူပါသည်။

**Default menu** - :menuselection:`Raster --> Miscellaneous`

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
   * - **Input files** (**ထည့်သွင်းအသုံးပြုသော file များ**)
     - ``LAYERS``
     - [raster] [list]
     - ထည့်သွင်းအသုံးပြုသော raster file များ။ File များစွာလည်း ဖြစ်နိုင်ပါသည်။
   * - **Field name to hold the file path to the indexed rasters** (**Indexed raster များဆီသို့ file လမ်းကြောင်းကို ထိန်းသိမ်းထားရန် field အမည်**)
     - ``PATH_FIELD_NAME``
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - [string]

       Default: 'location' ('တည်နေရာ')
     - Indexed raster များဆီသို့ file လမ်းကြောင်းကို ထိန်းသိမ်းထားရန် output field အမည်
   * - **Store absolute path to the indexed rasters** (**Indexed raster များထဲတွင် ပကတိလမ်းကြောင်းကို ထည့်သွင်းသိမ်းထားခြင်း**)
     - ``ABSOLUTE_PATH``
     - [boolean]

       Default: False
     - Raster file သို့ ပကတိလမ်းကြောင်းကို tile index file ထဲတွင် သိမ်းထား/မထား သတ်မှတ်ပေးပါသည်။ သာမန်အားဖြင့် raster file အမည်များကို command ထဲတွင် သတ်မှတ်ပေးသည့်အတိုင်း အတိအကျသိမ်းဆည်းပေးပါမည်။
   * - **Skip files with different projection reference** (**Projection reference မတူသော file များကိုကျော်ပစ်ပါ**)
     - ``PROJ_DIFFERENCE``
     - [boolean]

       Default: False
     - Tile index ထဲတွင် ထည့်သွင်းထားပြီးဖြစ်သော file များနှင့် projection တူသော file များကိုသာ ထည့်သွင်းပါမည်။ သာမန်အားဖြင့် projection ကိုမစစ်ဆေးဘဲ input အားလုံးကို လက်ခံပါသည်။
   * - **Tile index** (**Tile အညွှန်းကိန်း**)
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Index ရေးဆွဲမည့် polygon vector layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Transform geometries to the given CRS** (**အသုံးပြုထားသော CRS သို့ geometry များကိုပြောင်းလဲခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TARGET_CRS``
     - [crs]
     - Input file များ၏ geometry များကို သတ်မှတ်ထားသော ကိုဩဒိနိတ်စနစ်သို့ ပြောင်းလဲပေးပါမည်။ သာမန်အားဖြင့် input raster များ၏ ကိုဩဒိနိတ်စနစ်အတိုင်း ရိုးရှင်းသည့် ထောင့်မှန်စတုဂံ polygon များကို ဖန်တီးပေးပါသည်။
   * - **The name of the field to store the SRS of each tile** (**Tile တစ်ခုချင်းစီ၏ SRS ကိုသိမ်းဆည်းရန် column ၏အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CRS_FIELD_NAME``
     - [string]

     - Tile တစ်ခုချင်းစီ၏ SRS ကိုသိမ်းဆည်းရန် column ၏အမည်
   * - **The format in which the CRS of each tile must be written** (**Tile တစ်ခုချင်းစီ၏ CRS ကို ရေးသားရမည့် format**)
     - ``CRS_FORMAT``
     - [enumeration]

       Default: 0
     - CRS အတွက် format ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       * 0 -- Auto (``AUTO``)
       * 1 -- Well-known text (``WKT``)
       * 2 -- EPSG (``EPSG``)
       * 3 -- Proj.4 (``PROJ``)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Tile index**
     - ``OUTPUT``
     - [vector: polygon]
     - Tile index ဖြင့် polygon vector layer

Python code
............

**Algorithm ID**: ``gdal:tileindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalviewshed:

Viewshed
---------

အသုံးပြုသူသတ်မှတ်ထားသော point တစ်ခုအတွက် `Wang2000 <https://gdal.org/programs/gdal_viewshed.html#wang2000>`_ ထဲတွင် သတ်မှတ်ထားသော နည်းလမ်းကိုအသုံးပြုပြီး input raster DEM တစ်ခုမှ viewshed raster တစ်ခုကိုတွက်ထုတ်ပေးပါသည်။

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
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]

       Default: 1
     - မြေမျက်နှာသွင်ပြင်အနိမ့်အမြင့် အဖြစ်အသုံးပြုမည့် band နံပါတ်
   * - **Observer location** (**ကြည့်ရှုရမည့် တည်နေရာ**)
     - ``OBSERVER``
     - [point]

     - Observer ၏တည်နေရာ
   * - **Observer height** (**ကြည့်ရှုရမည့် အမြင့်**)
     - ``OBSERVER_HEIGHT``
     - [number]

       Default: 1.0
     - DEM ယူနစ်များဖြင့် observer ၏အမြင့်
   * - **Target height** (**ကြည့်ရှုမည့်နေရာ အမြင့်**)
     - ``TARGET_HEIGHT``
     - [number]


       Default: 1.0
     - DEM ယူနစ်များဖြင့် ကြည့်ရှုမည့် element ၏ အမြင့်
   * - **Maximum distance from observer to compute visibility** (**မြင်ရနိုင်စွမ်းကို တွက်ချက်ရန် observer မှ အဝေးဆုံးအကွာအဝေး**)
     - ``MAX_DISTANCE``
     - [number]

       Default: 100.0
     - DEM ယူနစ်များဖြင့် မြင်ရနိုင်စွမ်းကို တွက်ချက်ရန် observer မှ အဝေးဆုံးအကွာအဝေး
   * - **Output** (**ရလာဒ်**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output raster layer ။ အောက်ပါတို့မှ တစ်ခုခုဖြစ်ပါသည်-

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
   * - **Output** (**ရလာဒ်**)
     - ``OUTPUT``
     - [raster]
     - Viewshed ကိုပြသသော raster layer

Python code
............

**Algorithm ID**: ``gdal:viewshed``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
