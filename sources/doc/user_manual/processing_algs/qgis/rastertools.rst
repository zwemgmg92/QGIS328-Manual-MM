Raster tools (Raster ဆိုင်ရာ ကိရိယာများ)
=========================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisrasterize:

Convert map to raster (မြေပုံအား raster သို့ ပြောင်းလဲခြင်း)
-------------------------------------------------------------

Map canvas content (မြေပုံ canvas အကြောင်းအရာ) ၏ raster ဓာတ်ပုံတစ်ခုကို ဖန်တီးပေးပါသည်။

Layer တစ်ခုချင်းစီအတွက် သတ်မှတ်ထားသော style တစ်ခုနှင့်အတူ ကြိုတင်သတ်မှတ်ထားသည့် layer များအစု တစ်ခုကို render (ပုံဖော်ပြသခြင်း) ပြုလုပ်ရန် :ref:`map theme <map_themes>` (မြေပုံခေါင်းစဉ်) တစ်ခုကို ရွေးချယ်နိုင်ပါသည်။

တနည်းအားဖြင့်၊ map theme (မြေပုံခေါင်းစဉ်) ကို သတ်မှတ်မထားပါက single layer တစ်ခုကို ရွေးချယ်နိုင်ပါသည်။

အကယ်၍ map theme (မြေပုံခေါင်းစဉ်) သို့မဟုတ် layer တစ်ခုကိုမျှသတ်မှတ်ထားခြင်းမရှိပါက လက်ရှိ မြေပုံ content (အကြောင်းအရာ) ကိုသာ ပုံဖော်ပြသခြင်း (render) ပြုလုပ်မည်ဖြစ်ပါသည်။ ထည့်သွင်းထားသည့် အနိမ့်ဆုံး အကျယ်အဝန်းနယ် (minimum extent) ကို tile အရွယ်အစား အများအပြားအဖြစ် အတွင်းပိုင်း (internal) တွင် တိုးချဲ့ (extend) ပေးသွားမည်ဖြစ်ပါသည်။ 

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Minimum extent to render (xmin, xmax, ymin, ymax)** **(ပုံဖော်ပြသခြင်းပြုလုပ်ရန်အတွက် အနိမ့်ဆုံး အကျယ်အဝန်းနယ် (xmin ၊ xmax ၊ ymin ၊ ymax))**
     - ``EXTENT``
     - [extent]
     - Output (ရလာဒ်) raster layer ၏ အကျယ်အဝန်းနယ် (extent) ကို သတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် internal အရ တိုးချဲ့ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Tile size** (Tile အရွယ်အစား)
     - ``TILE_SIZE``
     - [number]
       
       Default: 1024
     - Output raster layer ၏ tile ၏ အရွယ်အစား။ အနိမ့်ဆုံးတန်ဖိုးသည် 64 ဖြစ်ပါသည်။
   * - **Map units per pixel** **(Pixel တစ်ခုစီအလိုက် မြေပုံယူနစ်များ)** 
     - ``MAP_UNITS_PER_PIXEL``
     - [number]
       
       Default: 100.0
     - Pixel အရွယ်အစား (မြေပုံယူနစ်များဖြင့်)။ အနိမ့်ဆုံးတန်ဖိုး - 0.0
   * - **Make background transparent** **(နောက်ခံကို ဖောက်ထွင်းမြင်ရအောင်ပြုလုပ်ပါ)**
     - ``MAKE_BACKGROUND_TRANSPARENT``
     - [boolean]
        
       Default: False
     - ဖောက်ထွင်းမြင်ရသည့်နောက်ခံ (transparent background) တစ်ခုဖြင့် မြေပုံအား export ပြုလုပ်ခြင်းကို ခွင့်ပြုပေးပါသည်။ အကယ်၍ ``True`` သို့ သတ်မှတ်ထားပါက RGBA (RGB အစား) image တစ်ခုကို ရရှိမည်ဖြစ်ပါသည်။     
   * - **Map theme to render** **(ပုံဖော်ပြသမည့် မြေပုံ theme)**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``MAP_THEME``
     - [enumeration]
     - ပုံဖော်ပြသခြင်းအတွက် ရှိနေပြီးသား :ref:`map theme <map_themes>` တစ်ခုကို အသုံးပြုပါ။
   * - **Single layer to render** **(ပုံဖော်ပြသရန်အတွက် single layer)**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``LAYER``
     - [enumeration]
     - ပုံဖော်ပြသခြင်းပြုလုပ်ရန်အတွက် single layer တစ်ခုကို ရွေးချယ်ပါ။
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]`` (ယာယီဖိုင်သို့ သိမ်းဆည်းပါသည်)
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT``
     - [raster]
     - Output raster layer  

Python code
............

**Algorithm ID**: ``native:rasterize``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfillnodata:

Fill NoData cells (NoData cell များကို ဖြည့်ခြင်း)
---------------------------------------------------

Input (ထည့်သွင်းအသုံးပြုသော) raster ထဲရှိ NoData တန်ဖိုးများကို ရွေးချယ်ထားသည့်တန်ဖိုး (chosen value) တစ်ခုသို့ ပြန်လည်သတ်မှတ်ခြင်း (Reset) ပြုလုပ်ပေးပါသည်။ NoData pixel များမပါရှိသည့် raster dataset ကို ရရှိစေမည်ဖြစ်ပါသည်။

Algorithm သည် input raster data အမျိုးအစားကို အလေးပေးစဉ်းစားပါသည်။ ဥပမာ- integer raster တစ်ခုတွင်လုပ်ဆောင်သောအခါ floating point fill value (ဒဿမကိန်း အဖြည့်တန်ဖိုး) သည် ဖြတ်တောက်ခြင်း (truncated) ခံရမည်ဖြစ်ပါသည်။

.. figure:: img/fill_nodata.png
  :align: center

  Raster တစ်ခု၏ NoData တန်ဖိုးများကိုဖြည့်ခြင်း (မီးခိုးရောင်ဖြင့်)

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input raster** **(ထည့်သွင်းအသုံးပြုသော raster)**
     - ``INPUT``
     - [raster]
     - Process (လုပ်ငန်းစဉ်) လုပ်ဆောင်မည့် raster
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [number]

       Default: 1
     - Raster ၏ band (လှိုင်းအလွှာ)
   * - **Fill value** **(အဖြည့်တန်ဖိုး)**
     - ``FILL_VALUE``
     - [number]

       Default: 1.0
     - NoData pixel များအတွက် အသုံးပြုမည့်တန်ဖိုးကို သတ်မှတ်ပါသည်။
   * - **Output raster** **(ရလာဒ် raster)**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]`` (ယာယီဖိုင်သို့ သိမ်းဆည်းပါ။)
     - Output raster ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Output layer** **(ရလာဒ် layer)**
     - ``OUTPUT``
     - [raster]
     - Data ဖြည့်ထားသော cell များပါဝင်သည့် output raster layer

Python code
............

**Algorithm ID**: ``native:fillnodata``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistilesxyzdirectory:

Generate XYZ tiles (Directory) (XYZ tile (လမ်းညွှန်) များကို ထုတ်လုပ်ခြင်း)
----------------------------------------------------------------------------

လက်ရှိ QGIS project ကို အသုံးပြုပြီး raster “XYZ” tile များကို individual (သီးခြား) image များအဖြစ် directory structure (hierarchy အရ ရှိသည့် folder များထဲရှိ ဖိုင်များ၏ ဖွဲ့စည်းတည်ဆောက်ပုံ) တစ်ခုထဲသို့ ထုတ်လုပ်ပေးပါသည်။ 

စိတ်ကြိုက်ရွေးချယ်မှုအရ ထုတ်လုပ်ထားသည့် tile များ (generated tiles) ကို အသုံးပြုပြီး Leaflet (web mapping application များတည်ဆောက်ရန်အသုံးပြုသည့် open source JavaScript library) HTML output file  တစ်ခုကို မြေပုံ layer တစ်ခုအဖြစ် ဖန်တီးနိုင်ပါသည်။
 
Parameters (သတ်မှတ်ချက်များ)
.............................

Basic parameters (အခြေခံသတ်မှတ်ချက်များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extent (xmin, xmax, ymin, ymax)** **(အကျယ်အဝန်းနယ် (xmin ၊ xmax ၊ ymin ၊ ymax))**
     - ``EXTENT``
     - [extent]
     - Tile များ၏ အကျယ်အဝန်းနယ် (extent) ကိုသတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် internal အရ တိုးချဲ့ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Minimum zoom** **(အနိမ့်ဆုံး zoom)**
     - ``ZOOM_MIN``
     - [number]

       Default: 12
     - အနိမ့်ဆုံး 0၊ အမြင့်ဆုံး 25
   * - **Maximum zoom** **(အမြင့်ဆုံး zoom)**
     - ``ZOOM_MAX``
     - [number]

       Default: 12
     - အနိမ့်ဆုံး 0၊ အမြင့်ဆုံး 25
   * - **DPI** **(Dot per inch)**
     - ``DPI``
     - [number]

       Default: 96
     - အနိမ့်ဆုံး 48၊ အမြင့်ဆုံး 600
   * - **Background color** **(နောက်ခံအရောင်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BACKGROUND_COLOR``
     - [color]

       Default: QColor(0, 0, 0, 0)
     - Tile များအတွက် နောက်ခံအရောင်ကို ရွေးချယ်ပါ။
   * - **Enable antialiasing** **(Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပေးခြင်း)**
     - ``ANTIALIAS``
     - [boolean]

       Default: True
     - Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကို ဖွင့်သင့်/မဖွင့်သင့် ဆုံးဖြတ်ပေးပါသည်။ 
   * - **Tile format**
     - ``TILE_FORMAT``
     - [enumeration]

       Default: 0
     - အောက်ပါတို့ထဲမှတစ်ခုဖြစ်ပါသည်-

       * 0 --- PNG
       * 1 --- JPG

   * - **Quality (JPG only)** **(အရည်အသွေး (JPG သာ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``QUALITY``
     - [number]

       Default: 75
     - အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 100
   * - **Metatile size** **(Metatile အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``METATILESIZE``
     - [number]

       Default: 4
     - XYZ tile များကို ထုတ်လုပ်သည့်အခါတွင် စိတ်ကြိုက် metatile အရွယ်အစားကို သတ်မှတ်ပါ။ ကြီးမားသည့် တန်ဖိုးများသည် memory ကို ပိုအသုံးပြုခြင်းဖြင့် tile များအား ပုံဖော်ပြသခြင်းကို မြန်ဆန်စေမည်ဖြစ်ပြီး ကောင်းမွန်သည့်အညွှန်းတပ်ခြင်း (better labelling) (အညွှန်းမပါရှိဘဲ ကွာဟချက်နည်းပါးသော) ကို ရရှိစေမည်ဖြစ်ပါသည်။ အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 20
   * - **Tile width** **(Tile အကျယ်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TILE_WIDTH``
     - [number]

       Default: 256
     - အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 4096
   * - **Tile height** **(Tile အမြင့်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TILE_HEIGHT``
     - [number]

       Default: 256
     - အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 4096
   * - **Use inverted tile Y axis (TMS conventions)** **(ပြောင်းပြန်ဖြစ်သော tile Y axis (TMS အစုအဝေးများ) ကို အသုံးပြုပါ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TMS_CONVENTION``
     - [boolean]

       Default: False
     - 
   * - **Output directory** **(ရလာဒ်များကိုသိမ်းဆည်းမည့်နေရာ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT_DIRECTORY``
     - [folder]

       Default: ``[Save to temporary folder]``
     - Output directory (tile များအတွက်) ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types_skip**
          :end-before: **end_directory_output_types_skip**

   * - **Output html (Leaflet)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT_HTML``
     - [html]

       Default: ``[Save to temporary file]``
     - Output HTML file ၏ သီးသန့်သတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

Advanced parameters (အဆင့်မြင့်သတ်မှတ်ချက်များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
|330|

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Leaflet HTML output title** **(Leaflet HTML ရလာဒ်ခေါင်းစဉ်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``HTML_TITLE``
     - [string]

       Default: Not set (သတ်မှတ်ထားခြင်းမရှိပါ)
     - Leaflet HTML output file အတွက် အသုံးပြုမည့် HTML <title>-tag 
   * - **Leaflet HTML output attribution** **(Leaflet HTML ရလာဒ် ထည့်သွင်းချက်များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``HTML_ATTRIBUTION``
     - [string]

       Default: Not set (သတ်မှတ်ထားခြင်းမရှိပါ)
     - Leaflet HTML output file အတွက်အသုံးပြုသည့် စိတ်ကြိုက်ဖန်တီးထားသော မြေပုံဆိုင်ရာထည့်သွင်းချက်များ။ HTML link များလည်းဖြစ်နိုင်ပါသည်။ 
   * - **Include OpenStreetMap basemap in Leaflet HTML output** **(Leaflet HTML output ထဲတွင် OpenStreetMap basemap ကို ထည့်သွင်းပါ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``HTML_OSM``
     - [boolean]

       Default: False
     - Leaflet HTML output file ထဲတွင် OpenStreetMap basemap layer တစ်ခု (ရင်းမြစ်- https://tile.openstreetmap.org) တစ်ခုကို ထည့်သွင်းထားပါသည်။ သင့်လျော်သော မြေပုံဆိုင်ရာထည့်သွင်းချက်များကို အလိုအလျောက်ထည့်သွင်းမည်ဖြစ်သည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output directory** **(ရလာဒ်များကိုသိမ်းဆည်းမည့်နေရာ)**
     - ``OUTPUT_DIRECTORY``
     - [folder]
     - ရလာဒ်များကိုသိမ်းဆည်းမည့်နေရာ (tile များအတွက်)
   * - **Output html (Leaflet)**
     - ``OUTPUT_HTML``
     - [html]
     - Output HTML (Leaflet) file

Python code
............

**Algorithm ID**: ``qgis:tilesxyzdirectory``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistilesxyzmbtiles:

Generate XYZ tiles (MBTiles) (XYZ tile (MBTiles) များကို ထုတ်လုပ်ခြင်း)
------------------------------------------------------------------------

လက်ရှိ QGIS project ကို အသုံးပြုပြီး raster “XYZ” tile များကို “MBTiles” format ဖြင့် single file တစ်ခုအဖြစ် ထုတ်လုပ်ပေးပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extent (xmin, xmax, ymin, ymax)** **(အကျယ်အဝန်းနယ် (xmin ၊ xmax ၊ ymin ၊ ymax))**
     - ``EXTENT``
     - [extent]
     - Tile များ၏ အကျယ်အဝန်းနယ် (extent) ကိုသတ်မှတ်ပေးပါသည်။ ၎င်းသည် tile အရွယ်အစား အများအပြားအဖြစ် internal အရ တိုးချဲ့ပေးသွားမည်ဖြစ်ပါသည်။ ရရှိနိုင်သော နည်းလမ်းများမှာ-

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Minimum zoom** **(အနိမ့်ဆုံး zoom)**
     - ``ZOOM_MIN``
     - [number]

       Default: 12
     - အနိမ့်ဆုံး 0၊ အမြင့်ဆုံး 25
   * - **Maximum zoom** **(အမြင့်ဆုံး zoom)**
     - ``ZOOM_MAX``
     - [number]

       Default: 12
     - အနိမ့်ဆုံး 0၊ အမြင့်ဆုံး 25
   * - **DPI** **(Dot per inch)**
     - ``DPI``
     - [number]

       Default: 96
     - အနိမ့်ဆုံး 48၊ အမြင့်ဆုံး 600
   * - **Background color** **(နောက်ခံအရောင်)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``BACKGROUND_COLOR``
     - [color]

       Default: QColor(0, 0, 0, 0)
     - Tile များအတွက် နောက်ခံအရောင် (background color) ကိုရွေးချယ်ပါ။ 
   * - **Enable antialiasing** **(Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကိုအသုံးပြုနိုင်အောင် ဖွင့်ပေးခြင်း)**
     - ``ANTIALIAS``
     - [boolean]

       Default: True
     - Antialiasing (မညီမညာမှုများကို ဖယ်ရှာပေးသောနည်းလမ်း) ကို ဖွင့်သင့်/မဖွင့်သင့် ဆုံးဖြတ်ပေးပါသည်။ 
   * - **Tile format**
     - ``TILE_FORMAT``
     - [enumeration]

       Default: 0
     - အောက်ပါတို့ထဲမှတစ်ခုဖြစ်ပါသည်-

       * 0 --- PNG
       * 1 --- JPG

   * - **Quality (JPG only)** **(အရည်အသွေး (JPG သာ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``QUALITY``
     - [number]

       Default: 75
     - အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 100
   * - **Metatile size** **(Metatile အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``METATILESIZE``
     - [number]

       Default: 4
     - XYZ tile များကို ထုတ်လုပ်သည့်အခါတွင် စိတ်ကြိုက် metatile အရွယ်အစားကို သတ်မှတ်ပါ။ ကြီးမားသည့် တန်ဖိုးများသည် memory ကို ပိုအသုံးပြုခြင်းဖြင့် tile များအား ပုံဖော်ပြသခြင်းကို မြန်ဆန်စေမည်ဖြစ်ပြီး ကောင်းမွန်သည့်အညွှန်းတပ်ခြင်း (better labelling) (အညွှန်းမပါရှိဘဲ ကွာဟချက်နည်းပါးသော) ကို ရရှိစေမည်ဖြစ်ပါသည်။ အနိမ့်ဆုံး 1၊ အမြင့်ဆုံး 20
   * - **Output file (for MBTiles)** **(ရလာဒ် file (MBTiles အတွက်))**
     - ``OUTPUT_FILE``
     - [file]

       Default : ``[Save to temporary file]``
     - Output file ၏ သီးသန့်သတ်မှတ်ချက် (Specification)။  အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output file (for MBTiles)** **(ရလာဒ် file (MBTiles အတွက်))**
     - ``OUTPUT_FILE``
     - [file]
     - Output file

Python code
............

**Algorithm ID**: ``qgis:tilesxyzmbtiles``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |330| replace:: ``NEW in 3.30``
