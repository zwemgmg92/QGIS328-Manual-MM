.. _qgis.documentation.features:

******************************
Features (အသွင်အပြင်များ)
******************************

.. only:: html

   .. contents::
      :local:

QGIS ၏ အဓိက feature များနှင့် plugin များဖြင့် ပထဝီဝင်သတင်းအချက်အလက်စနစ် (GIS) လုပ်ဆောင်ချက်များစွာကိုဆောင်ရွက်နိုင်မည်ဖြစ်ပါသည်။  
Locator bar ထည့်သွင်းထားသောကြောင့် လုပ်ဆောင်ချက်များ (function) ၊ dataset များနှင့် အခြားအရာများကိုအလွယ်တကူရှာဖွေနိုင်ပါသည်။

Feature များ နှင့် plugin များကို ယေဘူယျအနေဖြင့် အမျိုးအစား ၆မျိုးခွဲခြား၍ အောက်တွင်အကျဉ်းချုပ်ဖော်ပြထားပါသည်။
အကျဉ်းချုပ်၏နောက်တွင် ပေါင်းစပ်ထားသော Python console အကြောင်းအား ပဏာမဖော်ပြထားပါသည်။

View data (ဒေတာများအား ကြည့်ရှုခြင်း)
--------------------------------------

QGIS တွင် vector  data နှင့် raster data များကို (2D သို့မဟုတ် 3D) internal format (QGIS အတွင်းအသုံးပြုနိုင်သည့်ပုံစံ) သို့မဟုတ် common format (အသုံးများသောပုံစံ)  အဖြစ်ပြောင်းလဲရန်မလိုဘဲ 
နှစ်သက်ရာ format အမျိုးမျိူးနှင့် projection (ပုံရိပ်ချခြင်း) အမျိူးမျိူးတို့ဖြင့် ပေါင်းစပ်ကြည့်ရှုနိုင်ပါသည်။
အသုံးပြုနိုင်သည့် format များမှာ-

*  Spatially-enabled tables (တည်နေရာ၊ အကျယ်၊ အကွာအဝေးများပါဝင်သောဇယားများ)၊ PostGIS၊ SpatiaLite နှင့် MS SQL Spatial၊ Oracle Spatial ကဲ့သို့ database များမှ မြင်ကွင်းများနှင့် 
   ထည့်သွင်းထားသည့် OGR (OpenGIS simple feature Reference) library မှထောက်ပံ့ပေးသော GeoPackage၊ ESRI Shapefile၊ MapInfo၊ SDTS၊ GML နှင့်အခြားအရာများစွာကဲ့သို့သော vector file များ။
   :ref:`label_workingvector` section တွင်ကြည့်ပါ။
*  ထည့်သွင်းထားသည့် GDAL (Geospatial Data Abstraction Library) library မှထောက်ပံ့ပေးသည့် 
   GeoTIFF ၊ ERDAS IMG ၊ ArcInfo ၊ ASCII GRID ၊ JPEG ၊ PNG နှင့် အခြားများစွာသော အလားတူ Raster နှင့် imagery (ဓာတ်ပုံဆိုင်ရာ) format များ။
   :ref:`working_with_raster` section တွင်ကြည့်ပါ။
*  Mesh data (TINs နှင့် ပုံမှန် grids များကိုထောက်ပံ့ပေးပါတယ်) :ref:`label_meshdata` တွင်ကြည့်ပါ။
*  Vector tiles (Vector အကွက်များ)
*  GRASS raster ဖိုင်နှင့် GRASS databases မှ vector data  (တည်နေရာ/mapset)
   :ref:`sec_grass` section တွင်ကြည့်ပါ။
*  WMS ၊ WMTS ၊ WCS ၊ WFS နှင့် WFS-T ကဲ့သို့သော OGC Web Services များမှ အွန်လိုင်း spatial data များ။
   :ref:`working_with_ogc` section တွင်ကြည့်ပါ။
   
   QGIS authentication infrastructure ၏အကူအညီဖြင့် web service များနှင့် အခြားရင်းမြစ်များအသုံးပြုရာတွင်လိုအပ်သော 
   user name/password ၊ အသိအမှတ်ပြုလက်မှတ်များ (certificates) နှင့် key များကို စီမံနိုင်မည်ဖြစ်ပါသည်။
*  Spreadsheet များ (ODS / XLSX)

Temporal (အချိန်နှင့်ပတ်သက်သည့်) data များလည်း အသုံးပြုနိုင်ပါသည်။


Explore data and compose maps (Data များစူးစမ်းရှာဖွေခြင်းနှင့် မြေပုံများပြင်ဆင်ရေးဆွဲခြင်း)
----------------------------------------------------------------------------------------------

အသုံးပြုရလွယ်ကူသည့် Graphical User Interface (အသုံးပြုတဲ့အချိန်မှာ မျက်နှာပြင်တွင်ပေါ်နေတဲ့ tool များနှင့် တခြားအရာများ မြင်ရမှုအခြေအနေ) ကိုအသုံးပြုထားသည့်အတွက်
မြေပုံများအလွယ်တကူပြင်ဆင်ရေးဆွဲနိုင်မည်ဖြစ်ပြီး spatial data များကို အပြန်အလှန် စူးစမ်းရှာဖွေနိုင်မည်ဖြစ်ပါသည်။
Graphical User Interface (GUI) ထဲတွင်ပါဝင်သည့် အသုံးဝင်သော tool များမှာ-

* QGIS browser (ဖိုင်များကို ခေါ်ယူအသုံးပြုနိုင်သည့် browser)
* On-the-fly reprojection
* 2D and 3D map rendering (2D နှင့် 3D မြေပုံ render ပြုလုပ်ခြင်း)
* DB Manager (Database Manager)
* Print layout (Layout အမျိုးမျိုးနှင့် ပရင့်ထုတ်နိုင်ခြင်း)
* Report (အစီရင်ခံစာ)
* Overview panel (ခြုံငုံကြည့်ရှုနိုင်သည့် panel)
* Spatial bookmarks
* Annotation tools (မှတ်စာရေးသားသည့် tool များ)
* Identify/select features (features များကို ဖော်ထုတ်/ရွေးမှတ်ခြင်း)
* Edit/view/search attributes (Attributes များကို တည်းဖြတ်ပြင်ဆင်/ကြည့်ရှု/ရှာဖွေနိုင်ခြင်း)
* Data-defined feature labeling (Feature များအား အညွှန်းတပ်ခြင်း) 
* Data-defined vector and raster symbology tools (အချက်အလက်များဖော်ပြသတ်မှတ်၍ vector နှင့် raster သင်္ကေတများပြသသည့် tool များ)
* Atlas map composition with graticule layers (Graticule layers များနှင့် မြေပုံစီးရီးများဖွဲ့စည်းရေးဆွဲခြင်း)
* North arrow, scale bar and copyright label for maps (မြေပုံများရေးဆွဲရာတွင် ထည့်သွင်းနိုင်မည့် မြောက်အရပ်ပြမြှား၊ စကေးနှင့် မူပိုင်ခွင့်စာသားများ)
* Support for saving and restoring projects (Project များကို သိမ်းဆည်းခြင်းနှင့် ပြန်လည်ရယူခြင်း)


Create, edit, manage and export data (Data များကို ဖန်တီးခြင်း၊ တည်းဖြတ်ပြင်ဆင်ခြင်း၊ စီမံခြင်းနှင့် ထုတ်ယူခြင်း)
------------------------------------------------------------------------------------------------------------------

Vector layer နှင့် raster layer များကို အမျိုးမျိုးသော ဖိုင် format ပုံစံများဖြင့် ဖန်တီးခြင်း၊ တည်းဖြတ်ပြင်ဆင်ခြင်း၊ စီမံခြင်းနှင့် ထုတ်ယူခြင်းများကို လုပ်ဆောင်နိုင်မည်ဖြစ်ပါသည်။
QGIS တွင်ပါဝင်သည်များမှာ-

* Vector ဖိုင်များကို Digitizing (Basemap ကိုအခြေခံပြီး Point၊ Line၊ Polygon များရေးဆွဲခြင်း) လုပ်နိုင်သည့် tool များ ပါရှိခြင်း
* GRASS vector layer များနှင့် အမျိုးမျိုးသော ဖိုင် format များကို  ဖန်တီး၊ ပြင်ဆင်နိုင်စွမ်းရှိခြင်း
* Vector ဖိုင် များနှင့် image များအား geocode ပြုလုပ်နိုင်မည့် Georeferencer tool ပါရှိခြင်း 
* GPX formatကို ထည့်သွင်းခြင်းနှင့် ထုတ်ယူခြင်း ပြုလုပ်နိုင်ပြီး  အခြား GPS formatများအား  GPX အဖြစ်သို့ပြောင်းလဲပေးနိုင်သော သို့မဟုတ် GPS ယူနစ်တစ်ခုသို့ တိုက်ရိုက် down/upload ပြုလုပ်နိုင်သည့် GPS toolများပါရှိခြင်း (Linux တွင် usb အား  GPS ကိရိယာများစာရင်းတွင်ထည့်သွင်းပြီးသားဖြစ်ပါသည်)
* OpenStreetMap (OSM) မှ data များကို  visualize လုပ်ရန်နှင့် ပြင်ဆင်တည်းဖြတ်နိုင်ရန် ထောက်ပံ့ပေးခြင်း
* DB Manager plugin ၏ အကူအညီဖြင့် ဖိုင်များမှတစ်ဆင့် spatial database tables များအားဖန်တီးနိုင်စွမ်းရှိခြင်း
* Spatial database tables များကို ကိုင်တွယ်ဆောင်ရွက်ရသည်မှာ ပိုမိုအဆင်ပြေလွယ်ကူလာခြင်း
* Vector attribute table များ စီမံဆောင်ရွက်နိုင်ရန်အတွက် tool များ ပါရှိခြင်း 
* Screenshots များကို georeferenced images ဖိုင်များအဖြစ် သိမ်းဆည်းနိုင်ခြင်း
* စွမ်းဆောင်ရည်တိုးမြှင့်ထားသည့် DXF-Export tool ဖြင့် style များနှင့် plugin များကို Computer Aided Design (CAD) နှင့်တူသောလုပ်ဆောင်ချက်များ (functions) ရရှိစေရန် export လုပ်နိုင်ခြင်း

Analyze data (ဒေတာများကိုခွဲခြမ်းစိတ်ဖြာခြင်း)
-----------------------------------------------

QGIS ကိုအသုံးပြုခြင်းဖြင့် spatial database များနှင့် OGR library မှထောက်ပံ့ပေးသည့် spatial data များကို analysis ပြုလုပ်နိုင်မှာဖြစ်ပါသည်။
လက်ရှိတွင် QGIS ဖြင့် vector analysis ၊ raster analysis ၊ sampling ၊ geoprocessing ၊ geometry နှင့် database management စသည်တို့ကိုဆောင်ရွက်နိုင်ပါသည်။
QGIS တွင်ပေါင်းစပ်ထားသည့် analysis modules ၄၀၀ ကျော် ပါဝင်သည့် GRASS tools တို့ကြောင့်  GRASS ၏လုပ်ဆောင်နိုင်စွမ်း အပြည့်အဝရရှိမည်ဖြစ်ပါသည်။ (:ref:`sec_grass` section တွင်ကြည့်ပါ) 
သို့မဟုတ် QGIS တွင်ပါရှိသည့် စွမ်းဆောင်ရည်မြင့်သော geospatial analysis framework ဖြစ်သည့် Processing plugin ကိုသုံးကာ နဂိုပါရှိပြီးသား algorithms (native algorithms) 
နှင့် GDAL ၊ SAGA ၊ GRASS ၊ OTB ၊ R တို့ကဲ့သို့ ပြင်ပ algorithm များ (third-party algorithms) ကို ရယူအသုံးပြုနိုင်မှာဖြစ်ပါသည်။ (:ref:`sec_processing_intro` section  တွင်ကြည့်ပါ)

ခွဲခြမ်းစိတ်ဖြာခြင်းလုပ်ငန်းစဉ်များ (Analyze functions) အားလုံးသည် နောက်ကွယ် (background) တွင် run (လုပ်ဆောင်) နေမည်ဖြစ်ပါသည်။ ထို့ကြောင့် Analyze ပြုလုပ်မှု မပြီးသေးခင်မှာလည်း မိမိ၏လုပ်လက်စ project ကို ဆက်လက်ဆောင်ရွက်နေနိုင်မည်ဖြစ်ပါသည်။

Graphical modeller သည် လုပ်ဆောင်ချက်များ (functions) ကိုပေါင်းစည်းခြင်းနှင့်ချိတ်ဆက်ခြင်းများဆောင်ရွက်ပြီး 
သူ့အလိုလိုဆောင်ရွက်သည့် graphical environment တစ်ခုအတွင်း ပြီးပြည့်စုံသည့် workflow တစ်ခုလုပ်ဆောင်ပေးပါသည်။


Publish maps on the Internet (အင်တာနက်ပေါ်တွင်မြေပုံများထုတ်ဝေဖြန့်ဖြူးခြင်း)
------------------------------------------------------------------------------

QGIS ကို  WMS ၊ WMTS ၊ WMS-C ၊ WFS ၊ OAPIF နှင့် WFS-T client များအဖြစ်အသုံးပြုနိုင်ပါသည်။ (:ref:`working_with_ogc` section တွင်ကြည့်ပါ) QGIS server (see :ref:`QGIS-Server-manual` တွင်ကြည့်ပါ) ကိုသုံးခြင်းဖြင့် data များကိုအင်တာနက်ပေါ်တွင် WMS ၊ WCS ၊ WFS နှင့် OAPIF protocol များမှ တဆင့် publish လုပ်နိုင်ပါသည်။

 
Extend QGIS functionality through plugins (Plugin များသုံး၍  QGIS ၏ လုပ်ဆောင်နိုင်စွမ်းကိုတိုးမြှင့်ခြင်း)
-----------------------------------------------------------------------------------------------------------

Plugin များဖန်တီးရာတွင် အသုံးပြုနိုင်သည့် plugin architecture နှင့်  library များကို QGIS တွင် လိုအပ်သလို လိုက်လျောညီထွေအသုံးချနိုင်ပါသည်။
C++ သို့မဟုတ် Python ကိုသုံး၍ applications အသစ်များကိုပင်လျှင် ဖန်တီးနိုင်ပါသေးသည်။

Core Plugins (ပင်မ plugin များ)
................................

အဓိက plugin များအနေနှင့် အောက်ပါတို့ပါဝင်ပါသည်-

#. DB Manager (ဖလှယ်ရန်၊ တည်းဖြတ်ရန် နှင့်  layer များနှင့်  tables မှ/သို့ databases များကိုကြည့်ရှုရန်၊ execute SQL queries များကိုလုပ်ဆောင်ရန်)
#. Geometry Checker (ဂျီဩမေတြီ အမှားများကိုစစ်ပေးရန်)
#. Georeferencer GDAL (GDAL အသုံးပြု၍ raster များထဲသို့ projection အချက်အလက်များထည့်သွင်းနိုင်ရန်)
#. GPS Tools (GPS data များနှင့်ပတ်သက်ပြီး လုပ်ဆောင်ရန်)
#. GRASS (GRASS GIS နှင့်ပေါင်းစပ်ပေးရန်)
#. MetaSearch Catalogue Client (Web (CSW) စံနှုန်းအတွက် OGC Catalog Service အားအထောက်အပံ့ပေးသော metadata catalog service များနှင့်အပြန်အလှန် ချိတ်ဆက်ဆောင်ရွက်နိုင်ရန်) 
#. Offline Editing (Database များကိုအသုံးပြု၍ ပြင်ဆင်တည်းဖြတ်ခြင်းနှင့် synchronize လုပ်ခြင်းတို့ကို Offline ဖြင့်ဆောင်ရွက်နိုင်ရန်)
#. Processing (QGIS အတွက် processing framework မှ spatial data များ ထုတ်ပေးနိုင်ရန်)
#. Topology Checker (Vector layer များတွင် topological အမှားများကိုရှာဖွေရန်)


External Python plugins (ပြင်ပ Python Plugin များ)
...................................................

QGIS တွင် Community မှ ပံ့ပိုးနေသည့် ပြင်ပ Python Plugin များအရေအတွက်မှာ တဖြည်းဖြည်းနှင့်တိုးလာပြီဖြစ်ပါသည်။
ထို plugins များကို Official Plugins Repository တွင်ရရှိနိုင်ပြီး Python Plugin Installer အသုံးပြု၍ အလွယ်တကူထည့်သွင်းနိုင်ပါသည်။
:ref:`managing_plugins` section တွင်ကြည့်ပါ။


Python Console
---------------

QGIS တွင် script ရေးရန်အတွက် :menuselection:`Plugins--> Python Console` မှတစ်ဆင့် Python console ကိုဖွင့်၍အသုံးပြုနိုင်ပါသည်။

Python console သည် non-modal utility window အဖြစ်ပွင့်လာမည်ဖြစ်ပါသည်။ 
၎င်းသည် :class:`QgisInterface <qgis.gui.QgisInterface>` ၏ ဥပမာတစ်ခုဖြစ်သည့် :data:`qgis.utils.iface` variable မှတဆင့် QGIS environment နှင့်ချိတ်ဆက်နိုင်မည်ဖြစ်ပါသည်။
ဤ interface သည်  QGIS application ၏အစိတ်အပိုင်းများဖြစ်သော မြေပုံမြင်ကွင်း ၊ menu များ ၊ toolbar များ အစရှိသည်တို့နှင့်ချိတ်ဆက်ပေးပါသည်။ 
Script ဖန်တီးရေးသားပြီးသည့်အခါ  ထို Script ကို QGIS window ထဲသို့  drag and drop ဖြင့်ဆွဲထည့်လိုက်ပါက လုပ်ဆောင်ချက်များ အလိုအလျောက် ဆောင်ရွက်ပြီးဖြစ်သွားပါလိမ့်မည်။

Python console သုံး၍ အလုပ်လုပ်ခြင်းနှင့်ပတ်သက်၍ဖြစ်စေ၊ QGIS plugins များနှင့် applications များကို ပရိုဂရမ်ရေးသားခြင်းနှင့်ပတ်သက်၍ဖြစ်စေ 
အချက်အလက်များကိုပိုမိုသိရှိလိုပါက :ref:`console` နှင့် :ref:`PyQGIS-Developer-Cookbook` တွင်မှီငြမ်းလေ့လာနိုင်ပါသည်။


Known Issues (ကြုံတွေ့နေကျဖြစ်သည့် ပြဿနာများ)
----------------------------------------------

Number of open files limitation (ဖွင့်ခွင့်ပြုသည့် ဖိုင်အရေအတွက်ကန့်သတ်ချက်များ)
.................................................................................

QGIS project အကြီးစားတစ်ခုကို ဖွင့်ကြည့်ကြမည်ဆိုပါစို့၊ ထို project တွင် ပါဝင်သော layers (အလွှာ) အားလုံးသည် error (အမှား) ကင်း၍ အဆင်ပြေမှန်ကန်ကြောင်းသေချာသော်လည်း
အချို့ layer များမှာ error ဖြစ်နေလျှင် ယခုပြဿနာကိုရင်ဆိုင်နေရခြင်းဖြစ်ကောင်းဖြစ်နိုင်ပါသည်။
Linux နှင့်အလားတူ Operating System များတွင် လုပ်ငန်းစဉ်တစ်ခုချင်းအနေနှင့် ဆက်တိုက်ဖွင့်နိုင်သော ဖိုင်အရေအတွက်ကို ကန့်သတ်ထားပါသည်။
အလားတူပင် Resource များကိုလဲ လုပ်ငန်းစဉ်အလိုက် ကန့်သတ်ထားပါသည်။ လုပ်ငန်းစဉ်အသစ်တစ်ခုကိုဖွင့်လှစ်ဆောင်ရွက်သည့်အခါ ၎င်းသည် မူလလုပ်ငန်းစဉ်မှ Resource အရေအတွက်ကန့်သတ်ချက်များ အတိုင်းထပ်တူရယူပါသည်။
Linux တွင်ပါဝင်သော ``ulimit`` command သည် shell built-in command အမျိုးအစားဖြစ်၍ လက်ရှိ shell process ၏ ကန့်သတ်ချက်များကိုပြောင်းလဲပေးနိုင်ပါသည်။
ပြောင်းလဲလိုက်သော ကန့်သတ်ချက်အသစ်ကို လုပ်ငန်းစဉ်အသစ်များ (child processes) မှ ရရှိသွားမည်ဖြစ်ပါသည်။

လက်ရှိ ulimit အချက်အလက်များအားလုံးကို အောက်ပါအတိုင်း ရိုက်ထည့်ခြင်းအားဖြင့်တွေ့ရှိနိုင်ပါသည်-

.. code-block:: bash 

    $ ulimit -aS

လက်ရှိခွင့်ပြုထားသော လုပ်ငန်းစဉ်တစ်ခုချင်းအလိုက် ဖွင့်ထားနိုင်သည့်ဖိုင်အရေအတွက်ကို console တစ်ခုပေါ်တွင် အောက်ပါ command ကိုရိုက်ထည့်ခြင်းအားဖြင့်သိရှိနိုင်ပါသည်-

.. code-block:: bash

    $ ulimit -Sn

**လက်ရှိလုပ်ဆောင်ဆဲပရောဂျက်** တစ်ခုအတွက်  ကန့်သတ်ချက်များကိုပြောင်းလဲလိုလျှင် ယခုကဲ့သို့ command ကိုသုံးနိုင်ပါသည်-

.. code-block:: bash

    $ ulimit -Sn #number_of_allowed_open_files
    $ ulimit -Sn
    $ qgis
    
အခြားတစ်ခုအနေဖြင့် ``prlimit`` ဆိုသည့် utility အသစ်ကိုသုံးနိုင်ပါသည်။
ပိုမိုသိရှိလိုပါက https://manpages.ubuntu.com/manpages/latest/man1/prlimit.1.html တွင်သွားရောက်ကြည့်ရှုနိုင်ပါသည်။


**အမြဲတမ်းအတွက်ပြောင်းလဲပြင်ဆင်ထားလိုလျှင်**

Linux system အများစုတွင် login ဝင်သည့်အခါ system မှ အသုံးပြုနိုင်မည့် resource အရေအတွက်ကိုကန့်သတ်ထားပါသည်။
ထိုကန့်သတ်ချက်များကို ``pam_limits`` ဟူသည့် module ဖြင့်စီမံခြင်းဖြစ်ပါသည်။
ကန့်သတ်ချက်များအတွက် setting များကိုအဓိက ဖိုင်နှစ်ခုဖြစ်သော :file:`/etc/security/limits.conf` နှင့် :file:`/etc/security/limits.d/*.conf` ထဲတွင်သတ်မှတ်ထားပါသည်။ 
ကန့်သတ်ချက်များကိုပြင်ဆင်လိုသည့်အခါ  root privilege ကဲ့သို့သော အထူးခွင့်ပြုချက် လိုအပ်မှာဖြစ်ပါသည်။ (sudoမှတစ်ဆင့်လည်းပြုလုပ်နိုင်ပါသည်)
သတိပြုရမည့်တစ်ခုမှာ မိမိပြောင်းလဲပြင်ဆင်လိုက်သည့် အရေအတွက် ကန့်သတ်ချက်မှန်သမျှသည် ချက်ချင်း ပြောင်းလဲသွားမည်မဟုတ်ဘဲ logout လုပ်ပြီး နောက် login တစ်ဖန်ပြန်ဝင်မှသာပြောင်းလဲသွားပါမည်။

အချက်အလက်များအားပိုမိုသိရှိလိုပါက-

https://www.cyberciti.biz/faq/linux-increase-the-maximum-number-of-open-files/
https://linuxaria.com/article/open-files-in-linux တို့တွင်ကြည့်ရှုလေ့လာနိုင်ပါသည်။
