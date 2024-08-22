
.. _creating_layers:

****************************************
Creating Layers (Layer များဖန်တီးခြင်း)
****************************************

.. only:: html

   .. contents::
      :local:


Layers များကို အောက်ပါနည်းလမ်းများ အပါအဝင် နည်းလမ်းများစွာဖြင့် ဖန်တီးနိုင်ပါသည်- 

* Scratch မှ layer အလွတ်များ 
* လက်ရှိရှိနေသည့် layer များမှ layer များ 
* Clipboard (ဖိုင်တစ်ခုမှ အရာများအား နောက်ဖိုင်တစ်ခုသို့ ကူးယူရန်အတွက် ခေတ္တသိမ်းဆည်းထားသည့်နေရာ) ရှိ layer များ 
* တစ်ခုသို့ တစ်ခုထက်ပိုသော layer များအပေါ်အခြေခံထားသည့် SQL-like query ၏ ရလဒ်တစ်ခုအဖြစ်ရရှိလာသည့် layer များ (:ref:`virtual layers <vector_virtual_layers>`)

QGIS သည် အမျိုးမျိုးသော formats များအား တစ်ခုမှအခြားတစ်ခုသို့ import/export ပြုလုပ်နိုင်ရန် tools (ကိရိယာတန်ဆာပလာ) အမျိုးမျိုးအား ပံ့ပိုးပေးထားပါသည်။ 

.. index:: Create new layers
.. index:: Shapefile, SpatiaLite, GPX

.. _sec_create_vector:

Creating new vector layers (Vector layer အသစ်များ ဖန်တီးခြင်း)
===============================================================

QGIS သည် layer များကို အမျိုးမျိုးသော formats များဖြင့်ဖန်တီးနိုင်ရန်ခွင့်ပြုထားပါသည်။ ၎င်းသည် GeoPackage ၊ Shapefile ၊ SpatiaLite ၊ GPX format နှင့် disk များထဲတွင် သိမ်းဆည်းထားခြင်းမျိုးမဟုတ်ဘဲ QGIS ပိတ်လိုက်သည်နှင့် ပျောက်သွားမည့် Temporary Scratch layers (memory layers ဟုလည်းခေါ်ဆိုပါသည်) များဖန်တီးနိုင်ရန်အတွက် tools များကို ထောက်ပံ့ပေးထားပါသည်။ 
GRASS plugin အတွင်းတွင် :ref:`GRASS layer အသစ် <creating_new_grass_vectors>` တစ်ခု ဖန်တီးနိုင်ရန် ပံ့ပိုးထားပါသည်။ 


.. index:: New GeoPackage layer
.. _vector_create_geopackage:

Ceating a new GeoPackage layer (GeoPackage layer အသစ်တစ်ခုအား ဖန်တီးခြင်း)
---------------------------------------------------------------------------

GeoPackage layer (အမျိုးမျိုးသော raster နှင့် vector layer များကို သိမ်းဆည်းထားသည့် layer) အသစ်တစ်ခုကိုဖန်တီးရန် :menuselection:`Layer --> Create Layer -->` menu သို့မဟုတ် :guilabel:`Data Source Manager` toolbar ရှိ |newGeoPackageLayer| :menuselection:`New GeoPackage Layer...` ခလုတ်ကိုနှိပ်ပါ။ :numref:`figure_create_geopackage` တွင်ပြသထားသည့်အတိုင်း :guilabel:`New GeoPackage Layer` dialog ကိုပြသသွားမည်ဖြစ်ပါသည်။ 

.. _figure_create_geopackage:

.. figure:: img/editNewGeoPackage.png
   :align: center

   GeoPackage layer dialog အသစ်တစ်ခုအား ဖန်တီးခြင်း  

#. ပထမအဆင့်သည် database ဖိုင်တည်နေရာကို ညွှန်ပြသတ်မှတ်ခြင်းဖြစ်ပါသည်။ ၎င်းကို :guilabel:`Database` field ၏ ညာဘက်ဘေးရှိ :guilabel:`...` ခလုတ် ကို နှိပ်၍ ရှိနေသည့် GeoPackage file တစ်ခုကို select ပြုလုပ်ခြင်း သို့မဟုတ် အသစ်ဖန်တီးခြင်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။ QGIS သည် သတ်မှတ်ခဲ့သည့် အမည်အတိုင်း မှန်ကန်သည့် extension ကို အလိုအလျောက်ထည့်သွင်းသွားမည်ဖြစ်ပါသည်။ 
#. Layer / table အသစ်အား အမည်ပေးပါ။  (:guilabel:`Table name`)
#. :guilabel:`Geometry type` ကို သတ်မှတ်ပါ။ Geometryless (ဂျီဩမေတြီ မပါရှိသည့်) layer တစ်ခုမဟုတ်ပါက ၎င်းသည် :guilabel:`Include Z dimension` နှင့်/သို့မဟုတ် :guilabel:`Include M values` ဖြစ်သင့်သည်ကို သတ်မှတ်နိုင်ပါသည်။ 
#. |setProjection| ခလုတ်ကို အသုံးပြု၍ coordinate reference system ကို သတ်မှတ်ပါ။ 

ဖန်တီးထားသည့် layer ထဲတွင် သက်ဆိုင်ရာ field များအား ထည့်သွင်းရန်-

#. Field ၏ :guilabel:`Name` (အမည်) ကိုထည့်သွင်းပါ။ 
#. Data :guilabel:`Type` ကို ရွေးချယ်ပါ။ ပံ့ပိုးထားသည့်အမျိုးအစားများမှာ :guilabel:`Text data` ၊ :guilabel:`Whole number` (integer နှင့် integer64 နှစ်မျိုးစလုံး)၊ :guilabel:`Decimal number` ၊ :guilabel:`Date` နှင့် :guilabel:`Date and time`၊ :guilabel:`Binary (BLOB)` နှင့် :guilabel:`Boolean` တို့ဖြစ်ပါသည်။ 
#. ရွေးချယ်ထားသည့် data format အလိုက် တန်ဖိုးများ၏ :guilabel:`Maximum length` (အမြင့်ဆုံးအရှည်) ကို ထည့်သွင်းပါ။ 
#. |newAttribute| :guilabel:`Add to Fields List` ခလုတ် ကို click နှိပ်ပါ။ 
#. ထည့်သွင်းလိုသည့် field တစ်ခုချင်းစီအတွက် အထက်တွင်ဖော်ပြခဲ့သည့် အဆင့်များအတိုင်း ပြန်လည်လုပ်ဆောင်ပါ။ 
#. ဆက်စပ် attributes များကို စိတ်တိုင်းကျပြီဆိုပါက :guilabel:`OK` ကို နှိပ်ပါ။ QGIS သည် legend (ရည်ညွှန်းချက်) ထဲသို့ layer အသစ်အား ထည့်သွင်းသွားမည်ဖြစ်ပြီး ၎င်းကို :ref:`sec_edit_existing_layer` တွင် ဖော်ပြထားသည့်အတိုင်း edit (ပြောင်းလဲပြင်ဆင်ခြင်း) ပြုလုပ်နိုင်ပါသည်။ 

ပုံမှန်အားဖြင့် GeoPackage layer တစ်ခုကို ဖန်တီးသည့်အခါတွင် QGIS သည် Layer ၏ primary key (အဓိကသော့ချက်) အဖြစ်ဆောင်ရွက်သွားမည့် ``fid`` ဟုခေါ်သည့် :guilabel:`Feature id column` တစ်ခုကို ဖန်တီးထုတ်လုပ်ပေးသွားမည်ဖြစ်ပါသည်။ အမည်အား ပြောင်းလဲပြင်ဆင်နိုင်ပါသည်။ 
ဂျီဩမေတြီ field ကို ရရှိနိုင်ပါက ``geometry`` အဖြစ် အမည်ပေးထားပြီး ၎င်းအပေါ်တွင် :guilabel:`Create a spatial index (Spatial index တစ်ခုဖန်တီးရန်)` ကို ရွေးချယ်နိုင်ပါသည်။ ဤနည်းလမ်းများ (options) ကို :guilabel:`Advanced Options` အောက်တွင် :guilabel:`Layer identifier` (ဖတ်ရှုသဘောပေါက်ရန်လွယ်ကူသည့် layer ၏ အမည်) နှင့် :guilabel:`Layer description` (layer သတ်မှတ်ဖော်ပြချက်) တို့နှင့်အတူတွေ့ရှိနိုင်ပါသည်။ 

နောက်ထပ် GeoPackage layer များစီမံခန့်ခွဲခြင်းကို :ref:`DB Manager <dbmanager>` ဖြင့်လုပ်ဆောင်နိုင်ပါသည်။ 

.. _vector_create_shapefile:

Creating a new Shapefile layer (Shapefile layer အသစ်တစ်ခုအား ဖန်တီးခြင်း)
--------------------------------------------------------------------------

ESRI Shapefile format layer အသစ်တစ်ခုအားဖန်တီးရန် :menuselection:`Layer --> Create Layer -->` menu ထဲရှိ |newVectorLayer| :menuselection:`New Shapefile Layer...`  သို့မဟုတ် :guilabel:`Data Source Manager` toolbar ကို နှိပ်ပါ။ :guilabel:`New Shapefile Layer` dialog သည် :numref:`figure_create_shapefile` တွင်ပြထားသည့်အတိုင်း ပြသမည်ဖြစ်ပါသည်။ 

#. :guilabel:`File name` ဘေးရှိ :guilabel:`...` ခလုတ်ကို အသုံးပြုပြီး ဖိုင်နာမည် (file name) နှင့် လမ်းကြောင်း (path) တစ်ခုကို ပေးပါ။ QGIS သည် ပေးထားသည့်အမည်အတွက် မှန်ကန်သည့် extension ကို အလိုအလျောက်ထည့်သွင်းပေးမည်ဖြစ်ပါသည်။
#. ထို့နောက် data ၏ :guilabel:`File encoding` ကို ဖော်ပြပါ။
#. Layer ၏ :guilabel:`Geometry type` ကို ရွေးချယ်ပါ - No Geometry ( :file:`.DBF` format file ဖြင့်ရရှိလာမည်ဖြစ်သည်)၊ point (အမှတ်)၊ multipoint (အမှတ်များ)၊ line (မျဉ်း) နှင့် polygon (ဗဟုဂံ)။   
#. ဂျီဩမေတြီ သည် အခြားသောအတိုင်းအတာများ (dimensions) - :guilabel:`None` ၊ :guilabel:`Z (+ M values)` သို့မဟုတ် :guilabel:`M values` ရှိသင့်သည်/မရှိသင့်သည်ကို ဆုံးဖြတ်သတ်မှတ်ပါ။ 
#. |setProjection| ခလုတ်ကို အသုံးပြု၍ coordinate reference system (ကိုဩဒိနိတ်စနစ်) ကို သတ်မှတ်ဖော်ပြပါ။

.. _figure_create_shapefile:

.. figure:: img/editNewVector.png
   :align: center

   Shapefile layer အသစ်တစ်ခုကိုဖန်တီးခြင်းပြပုံ

ဖန်တီးထားသည့် layer ထဲသို့ field များထည့်သွင်းရန်-

#. Field ၏ :guilabel:`Name` ကို ထည့်သွင်းပါ။ 
#. Data :guilabel:`Type` ကို ရွေးချယ်ပါ။ :guilabel:`Decimal number` (ဒဿမကိန်း)၊ :guilabel:`Whole number` (အပြည့်ကိန်း)၊ :guilabel:`Text data` (စာသား) and :guilabel:`Date` (ရက်စွဲ) စသည့် attributes များကိုသာ ပံ့ပိုးထားပါသည်။ 
#. ရွေးချယ်ထားသည့် data format အလိုက် :guilabel:`Length (အရှည်)` နှင့် :guilabel:`Precision (တိကျမှု)` ကို ထည့်သွင်းပါ။ 
#. |newAttribute| :guilabel:`Add to Fields List` ခလုတ်ကို click နှိပ်ပါ။ 
#. ထပ်မံထည့်သွင်းရန်လိုအပ်ပါက အထက်တွင်ဖော်ပြခဲ့သည့်အဆင့်များကို ပြန်လည်လုပ်ဆောင်ပါ။ 
#. Attributes များကိုစိတ်တိုင်းကျပြီဆိုပါက :guilabel:`OK` ကိုနှိပ်ပါ။ QGIS သည် ရည်ညွှန်းချက် (legend) ထဲတွင် layer အသစ်ကို ထည့်သွင်းပေးသွားမည်ဖြစ်ပြီး :ref:`sec_edit_existing_layer` အပိုင်းတွင် ဖော်ပြထားသည့်အတိုင်း edit (ပြောင်းလဲပြင်ဆင်ခြင်း) လုပ်နိုင်ပါသည်။ 

ပုံမှန်အားဖြင့် ပထမဆုံးကိန်းပြည့် ``id`` column တစ်ခုကို ထည့်သွင်းထားမည်ဖြစ်ပြီး ၎င်းကို ဖယ်ရှား၍ရနိင်ပါသည်။


.. index:: New SpatiaLite layer
.. _vector_create_spatialite:

Creating a new SpatiaLite layer (SpatiaLite layer အသစ်တစ်ခုအားဖန်တီးခြင်း)
---------------------------------------------------------------------------

SpatiaLite layer (Single file တစ်ခုထဲတွင် spatial database တစ်ခုလုံးကို ကိုင်တွယ်ဆောင်ရွက်ရလွယ်ကူစေရန် ဖန်တီးထားသည့် layer) အသစ်တစ်ခုကို ဖန်တီးရန် :menuselection:`Layer--> Create Layer -->` menu ရှိ :menuselection:`New SpatiaLite Layer...` ခလုတ်သို့မဟုတ် :guilabel:`Data Source Manager` toolbar ကို နှိပ်ပါ။ :numref:`Figure_create_spatialite` တွင်ပြထားသည့်အတိုင်း :guilabel:`New SpatiaLite Layer` dialog ကို ပြသမည်ဖြစ်ပါသည်။ 

.. _figure_create_spatialite:

.. figure:: img/editNewSpatialite.png
   :align: center

   SpatiaLite layer အသစ်တစ်ခုအားဖန်တီးခြင်း Dialog
   
#. ပထမဆုံးအဆင့်သည် database file location (ဒေတာဘေ့စ်ဖိုင်တည်နေရာ) ကို သတ်မှတ်ဖော်ပြခြင်းဖြစ်ပါသည်။ ၎င်းကို :guilabel:`Database` field ၏ ညာဘက်ဘေးရှိ :guilabel:`...` ခလုတ်ကို နှိပ်ပြီး လက်ရှိရှိနေသည့် SpatiaLite file ကို ရွေးချယ်ခြင်း သို့မဟုတ် အသစ်တစ်ခုကို ဖန်တီးခြင်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။ QGIS သည် သတ်မှတ်ထားသည့်အမည်အား မှန်ကန်သည့် extension ကို အလိုအလျောက်ထည့်သွင်းပေးသွားမည်ဖြစ်ပါသည်။
#. Layer အသစ်အတွက် (:guilabel:`Layer name`) အမည်တစ်ခုပေးပါ။
#. :guilabel:`Geometry type` ကို သတ်မှတ်ပါ။ Geometryless (ဂျီဩမေတြီမပါရှိသော) layer တစ်ခုမဟုတ်ပါက ၎င်းသည် :guilabel:`Include Z dimension` နှင့်/သို့မဟုတ် :guilabel:`Include M values` ဖြစ်သင့်သည် ကို သတ်မှတ်နိုင်ပါသည်။
#. |setProjection| ခလုတ်ကိုအသုံးပြု၍ coordinate reference system ကို သတ်မှတ်ပါ။

ဖန်တီးထားသည့်  layer အား field များထည့်သွင်းရန်-

#. Field ၏ :guilabel:`Name` (အမည်) ကိုထည့်သွင်းပါ။ 
#. Data :guilabel:`Type` ကို ရွေးချယ်ပါ။ ပံ့ပိုးပေးထားသည့်အမျိုးအစားများမှာ :guilabel:`Text data` (စာသား) ၊ :guilabel:`Whole number` (ကိန်းပြည့်) ၊ :guilabel:`Decimal number` (ဒဿမကိန်း) ၊ :guilabel:`Date` (ရက်စွဲ) နှင့် :guilabel:`Date time` (ရက်စွဲအချိန်) တို့ဖြစ်ပါသည်။ 
#. |newAttribute| :guilabel:`Add to Fields List` ခလုတ်ကို click နှိပ်ပါ။ 
#. ထပ်ထည့်ရန်လိုအပ်ပါက အထက်တွင်ဖော်ပြခဲ့သည့်အဆင့်များအတိုင်း ပြန်လည်လုပ်ဆောင်ပါ။ 
#. Attribute များကို စိတ်တိုင်းကျပြီဆိုပါက :guilabel:`OK` ကို နှိပ်ပါ။ QGIS သည် legend (ရည်ညွှန်းချက်) ထဲတွင် layer အသစ်ကို ထည့်သွင်းသွားမည်ဖြစ်ပြီး ၎င်းကို :ref:`sec_edit_existing_layer` section တွင် ဖော်ပြထားသည့်အတိုင်း edit (ပြန်လည်ပြင်ဆင်ခြင်း) ပြုလုပ်နိုင်ပါသည်။ 

ဆန္ဒရှိပါက :guilabel:`Advanced Options` section အောက်ရှိ |checkbox| :guilabel:`Create an autoincrementing primary key` ကို select ပြုလုပ်နိုင်ပါသည်။ :guilabel:`Geometry column` (ပုံမှန်အားဖြင့် ``geometry``) ကိုလည်း အမည်ပြန်လည်ပြင်ဆင်နိုင်ပါသည်။ 

နောက်ထပ် SpatiaLite layer များစီမံခန့်ခွဲခြင်းကို :ref:`DB Manager <dbmanager>` ဖြင့် ဆောင်ရွက်နိုင်ပါသည်။ 


.. index:: New Mesh layer
.. _vector_create_mesh:

Creating a new Mesh layer (Mesh layer အသစ်တစ်ခုအားဖန်တီးခြင်း)
---------------------------------------------------------------

Mesh layer အသစ်တစ်ခုဖန်တီးရန် :menuselection:`Layer --> Create Layer -->` menu ထဲရှိ |newMeshLayer| :menuselection:`New Mesh Layer...` ခလုတ်သို့မဟုတ် :guilabel:`Data Source Manager` toolbar ကို နှိပ်ပါ။ :numref:`figure_create_mesh` တွင်ပြထားသည့်အတိုင်း :guilabel:`New Mesh Layer` dialog သည် ပြသသွားမည်ဖြစ်ပါသည်။ 

.. _figure_create_mesh:

.. figure:: img/editNewMesh.png
   :align: center

   Mesh layer အသစ်တစ်ခုအားဖန်တီးခြင်း Dialog

#. ပထမဆုံးအဆင့်သည် mesh file location (mesh ဖိုင်တည်နေရာ) ကို သတ်မှတ်ဖော်ပြခြင်းဖြစ်ပါသည်။ ၎င်းကို :guilabel:`File name` field ၏ ညာဘက်ဘေးရှိ :guilabel:`...` ခလုတ်ကို နှိပ်ပြီး လက်ရှိရှိနေသည့် mesh file ကို ရွေးချယ်ခြင်း သို့မဟုတ် အသစ်တစ်ခုကို ဖန်တီးခြင်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။
#. (:guilabel:`Layer name`) အမည်တစ်ခုသတ်မှတ်ပါ။ ဆိုလိုသည်မှာ :guilabel:`Layers` panel ထဲတွင် layer ကို ပြသသွားမည့် အမည်ဖြစ်ပါသည်။ 
#. :guilabel:`File format` ကို select ပြုလုပ်ပါ။ လက်ရှိတွင်ပံ့ပိုးပေးထားသည့်  mesh file formats များမှာ ``2DM Mesh File (*.2dm)`` ၊ ``Selafin File (*.slf)`` နှင့် ``UGRID (*.nc)`` တို့ဖြစ်ပါသည်။
#. Dataset တွင်ထည့်သွင်းရန် :ref:`Coordinate Reference System <crs_selector>` ကို သတ်မှတ်ပါ။
#. အထက်ဖော်ပြပါအဆင့်များသည် နောက်ပိုင်းတွင် vertices များကို digitize ပြုလုပ်ခြင်းနှင့် dataset groups များထည့်သွင်းခြင်းကို ဆောင်ရွက်နိုင်သည့် layer အလွတ်တစ်ခုကို ထုတ်ပေးမည်ဖြစ်ပါသည်။ သို့ရာတွင် ၎င်းသည် လက်ရှိရှိနေပြီးသား mesh layer တစ်ခုနှင့်အတူ layer ကို စတင်ဆောင်ရွက်နိုင်ပါသည်။ ဥပမာ- layer အသစ်ကို အခြား layer မှ vertices (မျဉ်းအဆစ်ထောင့်များ) သို့မဟုတ် faces (မျက်နှာများ) များဖြင့်ဖြည့်ခြင်း။ ထိုသို့ဆောင်ရွက်ရန်-

   #. |checkbox| :guilabel:`Initialize Mesh using` ကို အမှန်ခြစ်ပါ။
   #. ထို့နောက် :guilabel:`Mesh from the current project (လက်ရှိ project မှ mesh)` သို့မဟုတ် :guilabel:`Mesh from a file (File တစ်ခုမှ mesh)` ကို ရွေးချယ်ပါ။ Select ပြုလုပ်ထားသည့် mesh file ၏ အချက်အလက်များကို စစ်ဆေးမှုများပြုလုပ်ရန် (checkup) ပြသသွားမည်ဖြစ်ပါသည်။

   Mesh layer ၏ frame (ဘောင်) ကိုသာ layer အသစ်ထဲသို့ ကူးပြောင်းခြင်းလုပ်နိုင်ပြီး ၎င်းတို့၏ datasets များကို ကူးယူ၍မရသည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ 


.. index:: New GPX layer
.. _vector_create_gpx:

Creating a new GPX layer (GPX layer အသစ်တစ်ခုအားဖန်တီးခြင်း)
-------------------------------------------------------------

GPX file အသစ်တစ်ခုကိုဖန်တီးရန်-

#. :menuselection:`Layer` menu မှ :menuselection:`Create Layer -->` |createGPX| :menuselection:`New GPX Layer...` ကို ရွေးချယ်ပါ။ 
#. Dialog တွင် ဖိုင်အသစ်ကို မည်သည့်နေရာတွင် သိမ်းဆည်းမည်ကို ရွေးချယ်ပါ။ အမည်ပေးပါ။ ထို့နောက် :guilabel:`Save` ကိုနှိပ်ပါ။
#. Layers အသစ် သုံးခုကို :guilabel:`Layers Panel` ထဲသို့ ထည့်သွင်းသွားမည်ဖြစ်ပါသည်-

   * Name (အမည်) ၊ elevation (အမြင့်) ၊ comment (မှတ်ချက်) ၊ description (သတ်မှတ်ဖော်ပြချက်) ၊ source (ရင်းမြစ်) ၊ url နှင့် url name များကို သိမ်းဆည်းထားသည့် field များနှင့်အတူ တည်နေရာများ (``waypoints``) ကို digitize (digital form အဖြစ်သို့ ပြောင်းလဲခြင်း) ပြုလုပ်နိုင်သည့် point layer တစ်ခု
   * Name (အမည်) ၊ symbol (သင်္ကေတ) ၊ number (ကိန်းဂဏန်း) ၊ comment (မှတ်ချက်) ၊ description (သတ်မှတ်ဖော်ပြချက်) ၊ source (ရင်းမြစ်) ၊ url နှင့် url name များကို သိမ်းဆည်းထားသည့် field များနှင့်အတူ ကြိုတင်သတ်မှတ်ထားသည့်လမ်းကြောင်းတစ်ခုကို ပြုလုပ်ပေးနိုင်သည့် အတွဲလိုက်တည်နေရာများ (sequences of locations) ကို digitize ပြုလုပ်နိုင်သည့် line layer တစ်ခု
   * Name (အမည်) ၊ symbol (သင်္ကေတ) ၊ number (ကိန်းဂဏန်း) ၊ comment (မှတ်ချက်) ၊ description (သတ်မှတ်ဖော်ပြချက်) ၊ source (ရင်းမြစ်) ၊ url နှင့် url name များကို သိမ်းဆည်းထားသည့် field များနှင့်အတူ လက်ခံသူ၏ အချိန်နှင့်အမျှ လှုပ်ရှားသွားလာမှု (``tracks``) ကို ခြေရာခံရန် line layer တစ်ခု

#. :ref:`sec_edit_existing_layer` section တွင် ဖော်ပြထားသည့်အတိုင်း ၎င်းတို့အထဲမှ မည်သည်ကိုမဆို ယခုအချိန်တွင် ပြင်ဆင်ခြင်းများဆောင်ရွက်နိုင်ပြီဖြစ်ပါသည်။ 

.. index:: New Temporary Scratch layer
.. _vector_new_scratch_layer:

Creating a new Temporary Scratch Layer (Temporary Scratch Layer အသစ်တစ်ခုအားဖန်တီးခြင်း)
-----------------------------------------------------------------------------------------

Temporary Scratch Layers များသည် in-memory layers ဖြစ်ပါသည်။ ဆိုလိုသည်မှာ ၎င်းတို့ကို disk တွင် သိမ်းဆည်းထားခြင်းမဟုတ်ဘဲ QGIS ပိတ်လိုက်သည်နှင့် ဖယ်ရှားခံရမည်ဖြစ်ပါသည်။ ၎င်းတို့သည် ယာယီလိုအပ်သည့် feature များကို သိမ်းဆည်းရာတွင်ဖြစ်စေ geoprocessing
operations (လုပ်ငန်းဆောင်တာများ) ဆောင်ရွက်နေစဉ်တွင် intermediate layers များအဖြစ်သိမ်းဆည်းရာတွင်ဖြစ်စေ များစွာအသုံးတည့်ပါသည်။ 

Temporary Scratch layer အသစ်တစ်ခုအားဖန်တီးရန် :menuselection:`Layer --> Create Layer -->` menu ထဲရှိ |createMemory|
:menuselection:`New Temporary Scratch Layer...` entry  သို့မဟုတ် :guilabel:`Data Source Manager` toolbar ကို ရွေးချယ်ပါ။ 
:guilabel:`New Temporary Scratch Layer` dialog သည် :numref:`figure_create_temporary` တွင်ပြထားသည့်အတိုင်း ပြသမည်ဖြစ်ပါသည်။ ထို့နောက်-

#. :guilabel:`Layer name` ကို ထည့်သွင်းပါ။
#. :guilabel:`Geometry type` ကို select ပြုလုပ်ပါ။ ဤနေရာတွင် အောက်ပါတို့ကိုဖန်တီးနိုင်ပါသည်-

   * ``No geometry`` အမျိုးအစား layer ၊ simple table (ရိုးရှင်းသည့်ဇယား) ဖြင့် ဆောင်ရွက်ပါသည်။
   * ``Point`` သို့မဟုတ် ``MultiPoint`` layer ၊ 
   * ``LineString/CompoundCurve`` သို့မဟုတ် ``MultiLineString/MultiCurve`` layer
   * ``Polygon/CurvePolygon`` သို့မဟုတ် ``MultiPolygon/MultiSurface`` layer
#. Geometric အမျိုးအစားများအတွက် dataset ၏ အတိုင်းအတာများ (dimensions) ကို သတ်မှတ်ပါ။ ၎င်းတို့သည် :guilabel:`Include Z dimension` နှင့်/သို့မဟုတ် :guilabel:`Include M values` ဖြစ်သင့်သည်ကို စစ်ဆေးပါ။ 
#. |setProjection| ခလုတ်ကို အသုံးပြု၍ coordinate reference system ကို သတ်မှတ်ပါ။
#. Layer ထဲသို့ fields များထည့်သွင်းပါ။ သတိပြုရန်မှာ အခြားသော formats များနှင့်မတူသည်မှာ temporary
   layer များကို မည်သည့် field များမပါဘဲ ဖန်တီးနိုင်ပါသည်။ ထို့ကြောင့် ဤအဆင့်သည် စိတ်ကြိုက်ရွေးချယ်ခွင့် (optional) ဖြစ်ပါသည်။ 
#. Field ၏ :guilabel:`Name` ကို ထည့်သွင်းပါ။
#. Data :guilabel:`Type` ကို select ပြုလုပ်ပါ။ :guilabel:`Text` ၊ :guilabel:`Whole number` ၊ :guilabel:`Decimal number` ၊ :guilabel:`Boolean` ၊ :guilabel:`Date` ၊ :guilabel:`Time` ၊ :guilabel:`Date & Time` နှင့် :guilabel:`Binary (BLOB)` များကို ပံ့ပိုးပေးထားပါသည်။
#. ရွေးချယ်ထားသည့် data format အလိုက်  :guilabel:`Length` နှင့် :guilabel:`Precision` ကို ထည့်သွင်းပါ။
#. |newAttribute| :guilabel:`Add to Fields List` ခလုတ်ကို click နှိပ်ပါ။
#. ထပ်မံထည့်သွင်းလိုပါက အထက်တွင်ဆောင်ရွက်ခဲ့သည့်အဆင့်များအတိုင်း ပြန်လည်လုပ်ဆောင်ပါ။ 
#. Setting များကို စိတ်တိုင်းကျပြီဆိုပါက :guilabel:`OK` ကို နှိပ်ပါ။ QGIS သည် :guilabel:`Layers` panel ထဲတွင် layer အသစ်တစ်ခုကို ထည့်သွင်းသွားမည်ဖြစ်ပြီး ၎င်းကို :ref:`sec_edit_existing_layer` section တွင် ဖော်ပြထားသည့်အတိုင်း edit (ပြန်လည်ပြင်ဆင်ခြင်း) ပြုလုပ်နိုင်ပါသည်။ 


.. _figure_create_temporary:

.. figure:: img/editNewTemporaryLayer.png
   :align: center

   Temporary Scratch layer အသစ်တစ်ခုအားဖန်တီးခြင်း Dialog

Prepopulated (ကြိုတင်တွက်ချက်ဖြည့်တင်းထားသည့်) temporary scratch layers များကို clipboard (:ref:`paste_into_layer` တွင်ကြည့်ရှုပါ) ကို အသုံးပြုခြင်းဖြင့်ဖြစ်စေ သို့မဟုတ် :ref:`Processing algorithm <processing_algs>` ၏ ရလဒ်တစ်ခုအဖြစ် အသုံးပြုခြင်းဖြင့်ဖြစ်စေ ဖန်တီးနိုင်ပါသည်။ 

.. tip:: **Memory layer တစ်ခုကို Disk တွင် အမြဲသိမ်းဆည်းထားပါ**

  Temporary scratch layers များနှင့်အတူ project တစ်ခုကို ပိတ်သည့်အခါတွင် ဒေတာဆုံးရှုံးမှုများကို ရှောင်ရှားရန် ၎င်းတို့ကို QGIS မှ ပံ့ပိုးထားသည့် မည်သည့် vector format အဖြစ်သို့မဆိုပြောင်း၍ သိမ်းဆည်းထားနိုင်ပါသည်- 

  * Layer ၏ ဘေးတွင်ရှိသည့် |indicatorMemory| indicator icon ကို နှိပ်ခြင်းဖြင့်၊
  * Layer contextual menu ထဲရှိ :guilabel:`Make permanent` entry ကို select လုပ်ခြင်းဖြင့်၊
  * Contextual menu ထဲရှိ :menuselection:`Export -->` entry သို့မဟုတ် :menuselection:`Layer --> Save As...` menu ကို အသုံးပြုခြင်းဖြင့်ဖြစ်စေ။

  ဖော်ပြပါ commands (စေခိုင်းဆောင်ရွက်မှုများ) သည်  :ref:`general_saveas` section တွင်ဖော်ပြထားသည့် :guilabel:`Save Vector Layer as` dialog ကို ပွင့်စေပြီး သိမ်းဆည်းထားသည့်ဖိုင် (saved file) သည် :guilabel:`Layers` panel ထဲရှိ ယာယီဖိုင်နှင့် နေရာလဲသွားမည်ဖြစ်ပါသည်။ 

.. index:: Save layer
.. _general_saveas:

Creating new layers from an existing layer (ရှိပြီးသား layer တစ်ခုမှ layer အသစ်များကို ဖန်တီးခြင်း)
====================================================================================================

Raster နှင့် vector layer များကို အမျိုးမျိုးသော format များဖြင့်သိမ်းဆည်းနိုင်ပြီး မတူညီသော coordinate reference system (CRS) သို့ :menuselection:`Layer --> Save As...` menu  သို့မဟုတ် :guilabel:`Layers panel` ရှိ layer ပေါ်တွင် right-clicking နှိပ်ပြီး အောက်ပါတို့ကိုရွေးချယ်ကာ reproject ပြုလုပ်နိုင်ပါသည်- 

* Raster layers များအတွက် :menuselection:`Export --> Save As...` 
* Vector layers များအတွက် :menuselection:`Export --> Save Features As...` သို့မဟုတ် :menuselection:`Export --> Save Selected Features As...`  
* Layer tree (node များဖြင့်တည်ဆောက်ထားသော classical tree structure တစ်ခု) ထဲရှိ layer ကို :guilabel:`Browser Panel` ထဲရှိ PostGIS entry (spatial data များကို သိမ်းဆည်းရန်၊ spatial shapes များကို ဖန်တီးရန်နှင့်သိမ်းဆည်းရန်၊ လမ်းကြောင်းများကို ဆုံးဖြတ်ရန်၊ ဧရိယာနှင့်အကွာအဝေးများကို တွက်ချက်ရန်အသုံးပြုပါသည်) ထဲသို့ ဆွဲထည့်ပါ။ :guilabel:`Browser Panel` ထဲတွင် PostGIS connection တစ်ခုရှိရမည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ 

Common parameters (အသုံးများသော သတ်မှတ်ချက်များ) 
--------------------------------------------------

:guilabel:`Save Layer as...` dialog သည် layer ကို သိမ်းဆည်းသောအခါတွင် behavior (database တစ်ခုထဲရှိ အရာဝတ္ထုတစ်ခု၏ လုပ်ဆောင်ချက်များနှင့် ဝိသေသလက္ခဏာများ) များကို ပြောင်းလဲရန်အတွက် များစွာသော parameters (သတ်မှတ်ချက်များ) ကိုပြသပါသည်။
Raster နှင့် vector အတွက် common parameter များမှာ-

* :guilabel:`File name` - Disk တွင်ရှိသည့် ဖိုင်၏တည်နေရာ။ ၎င်းသည် output layer သို့မဟုတ် layer များကိုသိမ်းဆည်းထားသည့် container တစ်ခု (ဥပမာ- GeoPackage ၊ SpatiaLite သို့မဟုတ် Open Document Spreadsheets ကဲ့သို့သော database နှင့်တူသော format များ) ကို ညွှန်းဆိုပါသည်။ 
* Data များကို coordinate system တစ်ခုမှ အခြားတစ်ခုသို့ပြောင်းလဲခြင်း (reproject) ပြုလုပ်ရန် :guilabel:`CRS` ကို ပြောင်းလဲနိုင်ပါသည်။ 
* :guilabel:`Extent` - :ref:`extent_selector <extent_selector>` widget ကို အသုံးပြု၍ export လုပ်ခြင်းခံရမည့် input ၏ extent ကို ကန့်သတ်ပါသည်။ 
* :guilabel:`Add saved file to map` - Canvas (မြေပုံရေးဆွဲသည့်နေရာ) ထဲသို့ layer အသစ်ကို ထည့်သွင်းရန်။ 

သို့ရာတွင် အချို့သော parameters များသည်  raster နှင့် vector format များအတွက် သီးသန့်ဖြစ်ပါသည်။

Raster specific parameters (Raster အတွက် သီးသန့် parameter များ)
-----------------------------------------------------------------

Export ထုတ်မည့် format အပေါ်မူတည်၍ အောက်ဖော်ပြပါ အချို့သော options (နည်းလမ်းများ) ကိုရရှိနိုင်မည်မဟုတ်ပါ- 

* :guilabel:`Output mode` (၎င်းသည် **raw data** သို့မဟုတ် **rendered image** ဖြစ်နိုင်ပါသည်)
* :guilabel:`Format` - GeoTiff ၊ GeoPackage ၊ MBTiles ၊ Geospatial PDF ၊ SAGA GIS Binary Grid ၊ Intergraph Raster ၊ ESRI .hdr Labelled... ကဲ့သို့သော GDAL မှ ရေးသားနိုင်သည့် မည်သည့် raster format များသို့မဆို export ပြုလုပ်ပါသည်။
* :guilabel:`Resolution` (ကြည်လင်ပြတ်သားမှု)
* ဖိုင်များကို ထုတ်လုပ်သည့်အခါတွင် output format နှင့်ဆက်စပ်နေသည့် :ref:`predefined create profiles <gdal_createoptions>` မှ သော်လည်းကောင်း parameter တစ်ခုချင်းစီကို သတ်မှတ်ခြင်းဖြင့်သော်လည်းကောင်း advanced options (file compression (ဖိုင်ချုံ့ခြင်း) ၊ block sizes (blockchain တစ်ခုထဲတွင် single block တစ်ခုမှ သိမ်းဆည်းထားနိုင်သည့် အကြီးဆုံးဒေတာပမာဏ) ၊ colorimetry (color compound များစုစည်းမှုကိုဆုံးဖြတ်သည့်ပညာရပ်...)) များကို အသုံးပြုပါ။ 
* :guilabel:`Pyramids` ဖန်တီးခြင်း 
* အကယ်၍ |checkbox| :guilabel:`Create VRT` ကို အမှန်ခြစ်ခဲ့ပါက :guilabel:`VRT Tiles` 
* :guilabel:`No data values`

.. _figure_save_raster:

.. figure:: img/saveasraster.png
   :align: center

   Raster layer အသစ်တစ်ခုအဖြစ်သို့သိမ်းဆည်းခြင်း 

Vector specific parameters (Vector အတွက် သီးသန့် သတ်မှတ်ချက်များ)
------------------------------------------------------------------

Export ထုတ်မည့် format အပေါ်မူတည်၍ အောက်ဖော်ပြပါ အချို့သော options (နည်းလမ်းများ) များကို ရရှိနိုင်ပါသည်။-

* :guilabel:`Format` - GeoPackage ၊ GML ၊ ESRI Shapefile ၊ AutoCAD DXF ၊ ESRI FileGDB ၊ Mapinfo TAB or
  MIF ၊ SpatiaLite ၊ CSV ၊ KML ၊ ODS ၊ ... ကဲ့သို့သော GDAL မှ ရေးသားနိုင်သည့် မည်သည့် vector format များသို့မဆို export ပြုလုပ်ပါသည်။ 
* :guilabel:`Layer name` - :guilabel:`File name` (ဖိုင်အမည်) သည် container-like format (container နှင့်တူသော format) ကို ညွှန်းဆိုသည့်အခါတွင် ရယူဆောင်ရွက်နိုင်ပါသည်။ ဤ entry သည် output layer ကို ကိုယ်စားပြုဖော်ပြပါသည်။ 
* :guilabel:`Encoding` (စာဝှက်ဖြင့်ရေးသားခြင်း)
* :guilabel:`Save only selected features` (ရွေးချယ်ထားသော feature များကိုသာ သိမ်းဆည်းခြင်း)
* :guilabel:`Select fields to export and their export options` - Field များကို စိတ်ကြိုက်အမည်များနှင့် :ref:`form widget <configure_field>` setting များနှင့်အတူ export ပြုလုပ်ရန် နည်းလမ်းများကို ပံ့ပိုးပေးသည်- 

  * Output layer (ထွက်ရှိလာသည့် layer) ထဲတွင် သိမ်းဆည်းရန်အတွက် field များကို ရွေးချယ်ရန် :guilabel:`Name` ကော်လံတိုင် (column)အောက်ရှိ row များကို အမှန်ခြစ်ပါ။ သို့မဟုတ် :guilabel:`Select All` သို့မဟုတ် :guilabel:`Deselect All` ခလုတ်များကိုနှိပ်ပါ။ 
  * :guilabel:`Export name` column ကို သက်ဆိုင်ရာ field aliases (field တစ်ခုကိုသတ်မှတ်ထားသည့် အခြားအမည်တစ်ခု) များဖြင့်ဖြည့်ရန် သို့မဟုတ် original field name (field ၏ မူရင်းအမည်) ကို reset (မူလအတိုင်းပြန်လည်ထားရှိရန်) :guilabel:`Use aliases for exported name` checkbox ကို အမှန်ခြစ်ပါ။ Cell တစ်ခုကို Double-clicking ပြုလုပ်ခြင်းသည်လည်း အမည်ကို ပြန်လည်ပြင်ဆင်နိုင်မည်ဖြစ်ပါသည်။ 
  * Attribute form custom widgets (attribute ပုံစံ စိတ်ကြိုက် widegt) များ အားအသုံးပြုနေမှုရှိ/မရှိအပေါ်မူတည်၍ :guilabel:`Replace all selected raw field values by displayed values` (Select ပြုလုပ်ထားသည့် raw field values များကို displayed values များဖြင့်အစားထိုးခြင်း) ကို ဆောင်ရွက်နိုင်ပါသည်။ ဥပမာ- အကယ်၍ ``value map`` widget တစ်ခုသည် field တစ်ခုအပေါ်သို့ သက်ရောက်ထားပါက output layer သည် original values (မူလတန်ဖိုးများ) အစား description values (ဖော်ပြထားသည့်တန်ဖိုးများ) ပါဝင်လိမ့်မည်ဖြစ်ပါသည်။ ထိုသို့နေရာလဲခြင်း (replacement) ကို :guilabel:`Replace with displayed values` column ထဲတွင် field by field basis (field တစ်ခုချင်းစီ) နည်းလမ်းဖြင့် ဆောင်ရွက်နိုင်ပါသည်။

* :guilabel:`Persist layer metadata` သည် source layer ထဲတွင် :ref:`metadata
  <vectormetadatamenu>` များရှိနေသည့် မည်သည့် layer ကိုမဆို အောက်ဖော်ပြပါအနေဖြင့် ကော်ပီကူးယူခြင်းနှင့် သိမ်းဆည်းခြင်းကို သေချာစေပါသည်- 

  * အကယ်၍ output သည် GeoPackage format ဖြစ်ပါက အသစ်ဖန်တီးထားသည့် layer ထဲတွင်၊ 
  * အခြားသော format များအတွက် output layer နှင့် အတူ :file:`.qmd` file တစ်ခုအဖြစ်။ Dataset (ဥပမာ- SpatiaLite ၊ DXF ၊...) တစ်ခုထက်ပို၍ ပံ့ပိုးပေးသော file-based formats များသည် unintended behavior (ရည်ရွယ်ထားခြင်းမရှိသည့်လုပ်ဆောင်ချက်) ရှိကောင်းရှိနိုင်သည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ 
* :guilabel:`Symbology export` ကို DXF export နှင့် OGR feature styles များကို (အောက်ရှိ note တွင်ကြည့်ပါ)  DXF ၊ KML ၊ tab file formats များအဖြစ်သို့ ကိုင်တွယ်ဆောင်ရွက်နိုင်သည့် အခြားသော file formats များအတွက် အဓိကအသုံးပြုနိုင်ပါသည်-

  * **No symbology** - Data များကိုဖတ်ရှုသည့် application ၏ default style (ပုံမှန်စတိုင်)
  * **Feature symbology** - OGR Feature Style များဖြင့် style ကို သိမ်းဆည်းပါသည် (အောက်ရှိ note တွင်ကြည့်ပါ) 
  * **Symbol Layer symbology** - OGR Feature Style များဖြင့် style ကို သိမ်းဆည်းပါသည် (အောက်ရှိ မှတ်စု ကိုကြည့်ပါ)။ သို့ရာတွင် အကယ်၍ symbology symbol layer များ အများအပြားရှိနေပါက တူညီသည့် ဂျီဩမေတြီများကို အကြိမ်များစွာ (multiple times) export ပြုလုပ်ပါသည်။ 
  * **Scale** value (Scale တန်ဖိုး) တစ်ခုကို နောက်ဆုံးနည်းလမ်းများ (latest options) အပေါ်တွင် အသုံးချနိုင်ပါသည်။ 

.. _ogr_features_note:

.. note:: *OGR Feature Styles* များသည် style ကို data ထဲတွင် hidden attribute (တွေ့မြင်နိုင်ခြင်းမရှိသည့် attribute) အဖြစ်သို့ တိုက်ရိုက်သိမ်းဆည်းနိုင်သည့် နည်းလမ်းတစ်ခုဖြစ်ပါသည်။ Format အချို့သာ ဤကဲ့သို့သော အချက်အလက်များ (information) ကို ကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်။ KML ၊ DXF နှင့် TAB file format များသည် ထိုကဲ့သို့သော format များဖြစ်ပါသည်။ ပို၍အသေးစိတ်သည့်အချက်အလက်များအတွက် `OGR Feature Styles specification <https://gdal.org/user/ogr_feature_style.html>`_ document တွင် ဖတ်ရှုနိုင်ပါသည်။ 

* :guilabel:`Geometry` - Output layer ၏ ဂျီဩမေတြီ capabilities (စွမ်းဆောင်နိုင်ရည်များ) များကို သတ်မှတ်နိုင်ပါသည်-

  * :guilabel:`geometry type` - **Automatic** အဖြစ်သတ်မှတ်ထားသည့်အခါတွင် feature များ၏ မူလ ဂျီဩမေတြီကို သိမ်းထားနိုင်ပါသည်။ ထိုသို့မဟုတ်ပါက ၎င်းကို ဖယ်ရှားခြင်း သို့မဟုတ် မည်သည့်အမျိုးအစားနှင့်မဆို ပြင်ဆင်ရေးသားခြင်းများ ဆောင်ရွက်နိုင်ပါသည်။ Attribute table တစ်ခုထဲသို့ ဂျီဩမေတြီ column အလွတ်တစ်ခုကို ထည့်သွင်းနိုင်ပြီး spatial layer တစ်ခု၏ ဂျီဩမေတြီ column ကို ဖယ်ရှားနိုင်ပါသည်။ 
  * :guilabel:`Force multi-type` - Layer ထဲတွင် multi-geometry feature (အမျိုးမျိုးသော ဂျီဩမေတြီ features) များဖန်တီးခြင်းကို ဖြစ်စေပါသည်။ 
  * :guilabel:`Include z-dimension` - ဂျီဩမေတြီ များတွင် z-dimension ကို ထည့်သွင်းပါသည်။ 

.. tip::

  Layer ဂျီဩမေတြီ အမျိုးအစားကို ပြင်ဆင်ရေးသားခြင်းသည် geometryless (ဂျီဩမေတြီမပါရှိသော) ဇယား (ဥပမာ- :file:`.csv` file) တစ်ခုအား မည်သည့် ဂျီဩမေတြီ အမျိုးအစား (point ၊ line ၊ polygon) ဖြစ်ဖြစ် ပါရှိသည့် shapefile တစ်ခုအဖြစ် သို့ သိမ်းဆည်းခြင်းကဲ့သို့သော အရာများကို လုပ်ဆောင်နိုင်စေပါသည်။ သို့မှသာ ဂျီဩမေတြီ များကို |addPart| :sup:`Add Part` tool အသုံးပြုပြီး rows များထဲသို့ ကိုယ်တိုင် (manually) ထည့်သွင်းနိုင်မည်ဖြစ်ပါသည်။ 

* :guilabel:`Datasource Options` ၊ :guilabel:`Layer Options` သို့မဟုတ် :guilabel:`Custom Options` သည် output format အလိုက် advanced parameters (အထူးသတ်မှတ်ချက်များ) ကို ဖန်တီးသတ်မှတ်ခြင်းကိုခွင့်ပြုပါသည်။ အချို့ကို :ref:`supported_format` တွင်ဖော်ပြထားသော်လည်း အပြည့်အစုံကို `GDAL <https://gdal.org>`_ driver documentation တွင် ကြည့်ရှုပါ။ File တစ်ခုချင်းစီသည် ၎င်း၏ကိုယ်ပိုင် custom parameters (စိတ်ကြိုက်သတ်မှတ်ချက်များ) များရှိပါသည်။  ဥပမာ- ``GeoJSON`` format အတွက် `GDAL GeoJSON <https://gdal.org/drivers/vector/geojson.html#layer-creation-options>`_ documentation တွင် ကြည့်ရှုပါ။ 

.. _figure_save_vector:

.. figure:: img/saveasvector.png
   :align: center

   Vector layer အသစ်တစ်ခုအဖြစ် သိမ်းဆည်းခြင်း 

.. index:: Overwrite file, Append features

Vector layer တစ်ခုကို လက်ရှိရှိပြီးသားဖိုင်ထဲတွင် သိမ်းဆည်းသောအခါ output format ၏ စွမ်းဆောင်နိုင်ရည်များ (capabilities) အလိုက် သုံးစွဲသူအနေဖြင့် အောက်ပါတို့ကို ဆောင်ရွက်မည်/မဆောင်ရွက်မည်ကို ဆုံးဖြတ်နိုင်ပါသည်- 

* ဖိုင်တစ်ခုလုံးကို ပြန်လည်ပြင်ဆင်ရေးသားခြင်း၊
* Target layer (ရည်ရွယ်ထားသည့် layer) ကိုသာပြန်လည်ပြင်ဆင်ရေးသားခြင်း (layer အမည်သည် ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်)၊ 
* လက်ရှိရှိနေသည့် target layer ထဲသို့ feature များကို နောက်ဆက်တွဲပေါင်းထည့်ခြင်း (Append)၊ 
* Feature များကို နောက်ဆက်တွဲပေါင်းထည့်ခြင်း၊ အကယ်၍ တစ်ခုခုရှိနေပါက field အသစ်များကို ပေါင်းထည့်ခြင်း။ 

ESRI Shapefile ၊ MapInfo .tab ၊ ကဲ့သို့သော formats များအတွက် Features append (Feature များကို နောက်ဆက်တွဲပေါင်းထည့်ခြင်း) ကိုရယူဆောင်ရွက်နိုင်ပါသည်။ 


.. index:: DXF Export
.. _create_dxf_files:

Creating new DXF files (DXF files အသစ်များအား ဖန်တီးခြင်း)
===========================================================

:file:`*.DXF` အပါအဝင် single layer တစ်ခုကို အခြားသော format အဖြစ်သို့ export ထုတ်သည့် options (နည်းလမ်းများ) ကို ပံ့ပိုးသည့် :guilabel:`Save As...` dialog အပြင် QGIS သည် multiple layers များကို single DXF layer တစ်ခုအဖြစ်သို့ export ထုတ်ရန် အခြားသော tool ကို ပံ့ပိုးပေးထားပါသည်။ ၎င်းကို :menuselection:`Project --> Import/Export --> Export Project to DXF...` menu ထဲတွင် ကိုင်တွယ်ဆောင်ရွက်ခွင့် (accessible) ရှိပါသည်။ 

:guilabel:`DXF Export` dialog ထဲတွင်- 

#. ဖိုင်တည်နေရာကိုပံ့ပိုးထားပါသည်။ 
#. အကယ်၍ အသုံးပြုနိုင်မည်ဆိုပါက symbology mode နှင့် scale (စကေး) ကို ရွေးချယ်ပါ။ (:ref:`OGR Feature Styles <ogr_features_note>` note တွင်ကြည့်ရှပါ)
#. Data :guilabel:`Encoding` ကို select ပြုလုပ်ပါ။
#. အသုံးပြုမည့် :guilabel:`CRS` ကို select ပြုလုပ်ပါ။ Select ပြုလုပ်ထားသည့် layer များကို ပေးထားသည့် CRS နှင့်အညီ reproject လုပ်ဆောင်မည်ဖြစ်သည်။
#. Table widget ထဲတွင် ၎င်းတို့အားအမှန်ခြစ်ပေးခြင်းဖြင့်လည်းကောင်း လက်ရှိရှိနေသည့် :ref:`map theme
   <map_themes>` မှ အလိုအလျောက်ရွေးချယ်ခြင်းဖြင့်လည်းကောင်း  DXF files များထဲတွင် ထည့်သွင်းရန် layer များကို select ပြုလုပ်ပါ။
   :guilabel:`Select All` နှင့် :guilabel:`Deselect All` ခလုတ်များသည် export ပြုလုပ်နိုင်ရန် data ကို လျင်မြန်စွာ သတ်မှတ်နိုင်အောင် ကူညီပံ့ပိုးပေးပါသည်။ 

   Layer တစ်ခုချင်းစီအတွက် features အားလုံးကို single DXF layer တစ်ခုအဖြစ်သို့ export ပြုလုပ်မည် သို့မဟုတ် 
   Feature များကို DXF output ထဲရှိ layer များအဖြစ်သို့ခွဲထုတ်ရာတွင် အသုံးပြုသည့် ကိန်းဂဏန်းတန်ဖိုးများပါရှိသည့် field တစ်ခုအပေါ်တွင်မှီခိုမည် စသည်တို့ကို ရွေးချယ်နိုင်ပါသည်။ 

အောက်ပါတို့ကိုလည်း ရွေးချယ်လိုပါက ရွေးချယ်နိုင်ပါသည်-

* Layer ၏ မူရင်းအမည်အစား သတ်မှတ်ထားသည့်အမည်ကို layer title အဖြစ်အသုံးပြုရန် |checkbox| :guilabel:`Use the layer title as name if set` ကို အမှန်ခြစ်ပါ။ 
* လက်ရှိ map extent နှင့်ထပ်နေသည့် feature များကိုသာ export ထုတ်ရန် |checkbox| :guilabel:`Export features intersecting the current map extent` ကို အမှန်ခြစ်ပါ။ 
* |unchecked| :guilabel:`Force 2d output (eg. to support polyline width)` ကို အမှန်ခြစ်ဖျောက်ပါ။ 
* MTEXT elements သို့မဟုတ် TEXT elements အနေဖြင့် label ကို export ထုတ်ရန် |checkbox| :guilabel:`Export label as MTEXT elements` ကိုအမှန်ခြစ်ပါ။ 

.. _figure_create_dxf:

.. figure:: img/export_dxf.png
   :align: center

   Project တစ်ခုကို DXF အဖြစ်သို့ Export ပြုလုပ်ခြင်း Dialog 


.. _paste_into_layer:

Creating new layers from the clipboard (Clipboard မှ layer အသစ်များ ဖန်တီးခြင်း)
=================================================================================

Clipboard ပေါ်ရှိ feature များကို layer အသစ်တစ်ခုထဲသို့ paste ပြုလုပ်နိုင်ပါသည်။ ထိုသို့လုပ်ဆောင်ရန် features အချို့ကို select ပြုလုပ်ပါ။ ၎င်းတို့ကို clipboard သို့ ကော်ပီကူးယူပါ၊ ထို့နောက် :menuselection:`Edit --> Paste Features as -->` ကို အသုံးပြု၍ အောက်ပါတို့ကို ရွေးချယ်ပြီး layer အသစ်တစ်ခုထဲတွင် paste ပြုလုပ်ပါ-


* :guilabel:`New Vector Layer...` - :guilabel:`Save vector layer as...` dialog ပေါ်လာမည်ဖြစ်ပါသည်။ (parameter များအတွက် :ref:`general_saveas` တွင် ကြည့်ရှုပါ)
* သို့မဟုတ် :guilabel:`Temporary Scratch Layer...` - Layer အတွက် အမည်တစ်ခု ပေးရမည်ဖြစ်ပါသည်။ 

ရွေးချယ်ထားသည့် feature များနှင့် ၎င်းတို့၏ attribute များဖြင့်ဖြည့်ထားသည့် layer အသစ်တစ်ခုကို ဖန်တီးသွားမည်ဖြစ်ပါသည်။ (ထို့နောက် map canvas ထဲသို့ ထည့်သွားမည်ဖြစ်ပါသည်)

.. note:: Clipboard မှ layer များကိုဖန်တီးခြင်းကို QGIS အတွင်း select နှင့် copy လုပ်ထားသည့် feature များအပြင် အခြားသော application များမှ feature များဖြင့်လည်းဆောင်ရွက်နိုင်ပါသည်။ ထိုသို့ဆောင်ရွက်ခြင်းကို ၎င်းတို့၏ ဂျီဩမေတြီ များကို သိသာထင်ရှားသည့်စာသား (well-known text (WKT)) အသုံးပြု၍ သတ်မှတ်ထားသရွေ့ လုပ်ဆောင်နိုင်ပါသည်။ 


.. index:: Virtual layers
.. _vector_virtual_layers:

Creating virtual layers (Virtual layers များဖန်တီးခြင်း)
=========================================================

Virtual layer တစ်ခုဆိုသည်မှာ အထူး (special) vector layer အမျိုးအစားတစ်ခုဖြစ်ပါသည်။ ၎င်းသည် layer တစ်ခုကို QGIS မှ ဖွင့်နိုင်သည့် အခြား vector layer များမဆို ပါ၀င်သော SQL query တစ်ခု၏ ရလဒ်အဖြစ် သတ်မှတ်ရန် ခွင့်ပြုပါသည်။
Virtual layer များသည် ၎င်းတို့ကိုယ်တိုင် ဒေတာများကို သယ်ဆောင်ခြင်း (carry) မပြုလုပ်ဘဲ မြင်ကွင်းများ (views) အဖြစ် တွေ့မြင်နိုင်ပါသည်။

Virtual layer တစ်ခုကို ဖန်တီးရန် virtual layer creation dialog ကို အောက်ပါတို့ကိုဆောင်ရွက်ခြင်းဖြင့် ဖွင့်ပါ-

* :menuselection:`Layer --> Add Layer -->` menu ထဲရှိ |addVirtualLayer| :guilabel:`Add/Edit Virtual Layer` entry ကို ရွေးချယ်ခြင်း၊
* :guilabel:`Data Source Manager` dialog ထဲရှိ |addVirtualLayer| :guilabel:`Add Virtual Layer` tab ကို ဖွင့်ခြင်း၊
* သို့မဟုတ် :guilabel:`DB Manager` dialog tree ကို အသုံးပြုခြင်း

Dialog သည် :guilabel:`Layer name` တစ်ခုနှင့် SQL :guilabel:`Query` တစ်ခုကို သတ်မှတ်ခြင်းကို ခွင့်ပြုပါသည်။ Query သည် ထည့်သွင်းထားသည့် vector layers အမည် (သို့မဟုတ် id) ကို table များအဖြစ်အသုံးပြုနိုင်သည့်အပြင် ၎င်းတို့၏ field အမည်များကို  column များအဖြစ်လည်းအသုံးပြုနိုင်ပါသည်။ 

ဥပမာ- သင့်တွင် ``airports`` ဟုခေါ်သည့် layer တစ်ခုရှိပါက ``public_airports`` ဟုခေါ်သော virtual layer အသစ်တစ်ခုကို အောက်ဖော်ပြပါ SQL query တစ်ခုဖြင့် ဖန်တီးနိုင်ပါသည်-

.. code-block:: sql

   SELECT *
   FROM airports
   WHERE USE = "Civilian/Public"

``airports`` layer ၏ provider သည် SQL query များကို တိုက်ရိုက်မပံ့ပိုးစေကာမူ SQL query ကို လုပ်ကိုင်ဆောင်ရွက်နိုင်ပါသည်။ 

.. figure:: img/create_virtual_layers.png
   :align: center

   Virtual layer များဖန်တီးခြင်း Dialog 

Joins (ချိတ်ဆက်မှုများ) နှင့် ရှုပ်ထွေးသည့် (complex) query များကိုလည်း ဖန်တီးနိုင်ပါသည်။
ဥပမာ- လေဆိပ်များ (airports) နှင့် နိုင်ငံ၏အချက်အလက်များ (country information) ကို ချိတ်ဆက်ရန်- 

.. code-block:: sql

   SELECT airports.*, country.population
   FROM airports
   JOIN country
   ON airports.country = country.name   

.. note::

   Virtual layer များကို :ref:`dbmanager` ၏ SQL window ကို အသုံးပြု၍ ဖန်တီးရန်လည်း ဖြစ်နိုင်ပါသည်။ 

Embedding layers for use in queries (Query များထဲတွင် အသုံးပြုရန် layers များကို ထည့်သွင်းခြင်း)
-------------------------------------------------------------------------------------------------

Map canvas တွင် ရရှိနိုင်သည့် vector layers များအပြင် :guilabel:`Embedded layers` list ထဲသို့ layer များကို ထည့်သွင်းနိုင်ပါသည်။ ၎င်းကို map canvas သို့မဟုတ် layers panel ထဲတွင် ပြသရန်မလိုအပ်ဘဲ query များတွင် အသုံးပြုနိုင်ပါသည်။

Layer တစ်ခုကို ထည့်သွင်းရန် :guilabel:`Add` ကို click နှိပ်ပြီး :guilabel:`Local name` ၊ :guilabel:`Provider` ၊ :guilabel:`Encoding` နှင့် :guilabel:`Source` လမ်းကြောင်း စသည်တို့ကို ထည့်သွင်းပါ။ 

:guilabel:`Import` ခလုတ် သည် map canvas ထဲရှိ layers များကို Embedded layers list (ထည့်သွင်းထားသည့် layer စာရင်း) ထဲသို့ ထည့်သွင်းခြင်းကိုခွင့်ပြုပါသည်။ အဆိုပါ layer များကို နောက်ပိုင်းတွင် ရှိပြီးသား existent queries များကိုဖြိုခွဲခြင်းမပြုဘဲ layers panel များမှဖယ်ရှားနိုင်ပါသည်။ 

Supported query language (ပံ့ပိုးပေးထားသည့် Query ဘာသာစကား)
------------------------------------------------------------

Underlying engine (အရင်းခံ engine) သည် လုပ်ငန်းဆောင်တာများလည်ပတ်ရန် SQLite နှင့် SpatiaLite ကို အသုံးပြုပါသည်။

ဆိုလိုသည်မှာ SQLite ၏ local installation ပြုလုပ်ခြင်းက နားလည်နိုင်သော SQL အားလုံးကို အသုံးပြုနိုင်ပါသည်။  

SQLite မှ လုပ်ငန်းဆောင်ရွက်မှုများ (functions) နှင့် SpatiaLite မှ spatial function များကို virtual layer query တစ်ခုထဲတွင် အသုံးပြုနိုင်ပါသည်။ ဥပမာ- point layer တစ်ခုကို attribute-only layer တစ်ခု၏ ပြင်ပမှ ဖန်တီးခြင်းကို အောက်ဖော်ပြပါနှင့်အလားတူသည့် query တစ်ခုဖြင့် လုပ်ဆောင်နိုင်ပါသည်- 

.. code-block:: sql

   SELECT id, MakePoint(x, y, 4326) as geometry
   FROM coordinates

:ref:`Functions of QGIS expressions<functions_list>`  ကို virtual layer query တစ်ခုထဲတွင်လည်း အသုံးပြုနိုင်ပါသည်။ 

Layer တစ်ခု၏ ဂျီဩမေတြီ column ကို ညွှန်းဆိုရန် ``geometry`` ဆိုသည့် အမည်ကို အသုံးပြုပါ။

Pure SQL query တစ်ခုနှင့်မတူသည်မှာ virtual layer query တစ်ခု၏ field အားလုံးကို အမည်သတ်မှတ်ပေးထားရမည်ဖြစ်ပါသည်။
အကယ်၍ ၎င်းတို့သည် တွက်ချက်မှု (computation) တစ်ခု၏ ရလဒ် သို့မဟုတ် function call တစ်ခုဖြစ်ပါက column များကို အမည်ပေးရန် ``as`` keyword  ကို အသုံးပြုရန်မမေ့သင့်ပါ။

Performance issues (စွမ်းဆောင်ရည်ပိုင်းဆိုင်ရာပြဿနာရပ်များ)
------------------------------------------------------------

ပုံမှန်သတ်မှတ်ချက်များ (default parameters) နှင့်အတူ virtual layer engine သည် အကယ်၍ ဂျီဩမေတြီ column တစ်ခုကို ဖော်ပြထားပါက ဂျီဩမေတြီ column ၏ အမျိုးအစားအပါအဝင် query ၏ မတူညီသည့် column များ၏အမျိုးအစားကို ရှာဖွေတွေ့ရှိရန် (detect) အစွမ်းကုန်ဆောင်ရွက်သွားမည်ဖြစ်ပါသည်။

၎င်းကို သင့်လျော်သည့်အခါတိုင်းတွင် query ကို ဆန်းစစ်ခြင်း (introspecting) သို့မဟုတ် query ၏ ပထမဆုံး row (LIMIT 1) ကို နောက်ဆုံး resort အဖြစ်သို့ fetching (တစ်စုံတစ်ခုကိုရယူရန်ဆောင်ရွက်ခြင်း) ပြုလုပ်ခြင်းဖြင့်ဆောင်ရွက်နိုင်ပါသည်။ Layer ကို ဖန်တီးရုံသက်သက်ဖြင့် first row ရလဒ်၏ ကို fetching ပြုလုပ်ခြင်းသည် စွမ်းဆောင်ရည်ပိုင်းဆိုင်ရာအကြောင်းပြချက်များ (performance reasons) အတွက် လိုအပ်မှုမရှိသည်လည်းဖြစ်နိုင်ပါသည်။ 

Creation dialog သတ်မှတ်ချက်များ-

* :guilabel:`Unique identifier column` - QGIS မှ row identifier များအဖြစ်အသုံးပြုနိုင်သော သိသာထင်ရှားသည့် အပြည့်ကိန်းတန်ဖိုးများ (unique integer values) ကို ကိုယ်စားပြုဖော်ပြသည့် query ၏ field တစ်ခုကို သတ်မှတ်ပါသည်။ ပုံမှန်အားဖြင့် အလိုအလျောက်တိုးပွားသည့် အပြည့်ကိန်းတန်ဖိုးကို အသုံးပြုပါသည်။ Unique (သိသာထင်ရှားသည့်) identifier column တစ်ခုကို သတ်မှတ်ခြင်းသည် id ဖြင့် row များအား selection ပြုလုပ်ခြင်းကို လျင်မြန်စေပါသည်။ 

* :guilabel:`No geometry` - Virtual layer အား မည်သည့် ဂျီဩမေတြီ field ကိုမဆို လျစ်လျူရှုခြင်း (ignore) ကို ဖြစ်စေပါသည်။ ရရှိလာသည့် layer သည် attribute-only (features များကို ဖော်ပြသည့် spatial data နှင့် ချိတ်ဆက်ထားသော အချက်အလက်များသာပါဝင်သည့်) layer တစ်ခုဖြစ်ပါသည်။

* Geometry :guilabel:`Column` - ဂျီဩမေတြီ column ၏ အမည်ကို သတ်မှတ်ပါသည်။

* Geometry :guilabel:`Type` - ဂျီဩမေတြီ ၏ အမျိုးအစားကို သတ်မှတ်ပါသည်။ 

* Geometry :guilabel:`CRS` - Virtual layer ၏ coordinate reference system ကို သတ်မှတ်ပါသည်။ 

Special comments (အထူးမှတ်ချက်များ) 
-------------------------------------

Virtual layer engine သည် query ၏ column တစ်ခုချင်းစီ၏ အမျိုးအစားကို ဆုံးဖြတ်ရန် ကြိုးပမ်းမည်ဖြစ်ပါသည်။ အကယ်၍ မအောင်မြင်ခဲ့ပါက column အမျိူးအစားများကို ဆုံးဖြတ်ရန် query ၏ ပထမဆုံး row သည် fetch ပြုလုပ်ခြင်း ခံရမည်ဖြစ်ပါသည်။ 

Query ထဲတွင် သီးသန့် column တစ်ခု၏ အမျိုးအစားကို special comments (အထူးမှတ်ချက်များ) အချို့ကို အသုံးပြု၍ တိုက်ရိုက်သတ်မှတ်နိုင်ပါသည်။ 

Syntax (စကားလုံးနှင့်စကားရပ်အထားအသို) သည် ဖော်ပြပါအတိုင်းဖြစ်ပါသည်- ``/*:type*/`` ။ ၎င်းကို column တစ်ခု၏အမည်နောက်တွင် ထားရှိရမည်ဖြစ်ပါသည်။ ``type`` သည် အပြည့်ကိန်း (integer) များအတွက် ``int`` ၊ floating point numbers (ဒသမနေရာများပါဝင်သည့် အပေါင်းနှင့်အနုတ်ကိန်းပြည့်များ) ``real`` သို့မဟုတ် ``text`` ဖြစ်နိုင်ပါသည်။ 

ဥပမာ-

.. code-block:: sql

  SELECT id+1 as nid /*:int*/
  FROM table

ဂျီဩမေတြီ column ၏ အမျိုးအစားနှင့် coordinate reference system ကို ဖော်ပြပါ syntax ``/*:gtype:srid*/`` နှင့်အတူ special comments (အထူးမှတ်ချက်များ) များဖြင့်သတ်မှတ်နိုင်ပါသည်။ ``/*:gtype:srid*/`` တွင် ``gtype`` သည် ဂျီဩမေတြီ အမျိုးအစား (``point`` ၊ ``linestring`` ၊ ``polygon`` ၊ ``multipoint`` ၊ ``multilinestring`` သို့မဟုတ် ``multipolygon``) နှင့် ``srid`` သည် coordinate reference system တစ်ခု၏ EPSG code ကို ကိုယ်စားပြုဖော်ပြသည့် အပြည့်ကိန်း (integer) တစ်ခု ဖြစ်ပါသည်။ 

Use of indexes (အညွှန်း (index) များအသုံးပြုခြင်း) 
----------------------------------------------------

Virtual layer တစ်ခုမှတဆင့် layer တစ်ခုကို တောင်းဆိုသည့်အခါတွင် source layer indices (ရင်းမြစ် layer ၏ အညွှန်း) ကို အောက်ဖော်ပြပါနည်းလမ်းများဖြင့် အသုံးပြုသွားမည်ဖြစ်ပါသည်- 

* အကယ်၍ ``=`` predicate (အတိအကျဖော်ပြမှု) တစ်ခုကို layer ၏ primary key column (အဓိကကော်လံ) တွင် အသုံးပြုထားပါက underlying data provider သည် particular id(သီးသန့်အိုင်ဒီ) (FilterFid) ကို တောင်းဆိုမည်ဖြစ်သည်။
* အခြားသော predicate များ (``>`` ၊ ``<=`` ၊ ``!=`` ၊ အစရှိသည်...) အတွက် သို့မဟုတ် primary key တစ်ခု မပါရှိသည့် column တစ်ခုအပေါ်တွင် expression တစ်ခုမှ တည်ဆောက်ထားသည့် request (တောင်းဆိုမှု) တစ်ခုအား underlying vector data provider ကို request (တောင်းဆိုမှု) လုပ်ရန် အသုံးပြုလိမ့်မည်ဖြစ်သည်။ ဆိုလိုသည်မှာ အကယ်၍ database providers တည်ရှိနေပါက အညွှန်းများ (indexes) ကို အဆိုပါ database providers များအပေါ်တွင်အသုံးပြုမည်ဖြစ်ပါသည်။ 

တိကျသည့် syntax (specific syntax) တစ်ခုသည် request များထဲတွင် spatial predicate များကိုကိုင်တွယ်ဆောင်ရွက်ရန်  နှင့် spatial index တစ်ခုအသုံးပြုမှုကို အစပျိုးလုပ်ဆောင်ရန် တည်ရှိပါသည်။ ``_search_frame_`` ဟု အမည်တွင်သည့် မမြင်အောင်ဖျောက်ထားသည့် column တစ်ခုသည် virtual layer တစ်ခုချင်းစီအတွက် တည်ရှိမည်ဖြစ်ပါသည်။ ဤ column သည် တန်းတူညီမျှရှိစေရေး (equality) အတွက် bounding box တစ်ခုနှင့်နှိုင်းယှဉ်နိုင်မည်ဖြစ်ပါသည်။ ဥပမာ-

.. code-block:: sql

   SELECT *
   FROM vtab
   WHERE _search_frame_=BuildMbr(-2.10,49.38,-1.3,49.99,4326)

ဤ spatial index syntax များနှင့်ဆက်စပ်၍ အသုံးပြုသောအခါတွင် ``ST_Intersects`` ကဲ့သို့သော Spatial binary predicate များသည် သိသာထင်ရှားစွာ အရှိန်မြင့်တက်လာမည်ဖြစ်ပါသည်။ 

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addPart| image:: /static/common/mActionAddPart.png
   :width: 1.5em
.. |addVirtualLayer| image:: /static/common/mActionAddVirtualLayer.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |createGPX| image:: /static/common/create_gpx.png
   :width: 1.5em
.. |createMemory| image:: /static/common/mActionCreateMemory.png
   :width: 1.5em
.. |indicatorMemory| image:: /static/common/mIndicatorMemory.png
   :width: 1.5em
.. |newAttribute| image:: /static/common/mActionNewAttribute.png
   :width: 1.5em
.. |newGeoPackageLayer| image:: /static/common/mActionNewGeoPackageLayer.png
   :width: 1.5em
.. |newMeshLayer| image:: /static/common/mActionNewMeshLayer.png
   :width: 1.5em
.. |newSpatiaLiteLayer| image:: /static/common/mActionNewSpatiaLiteLayer.png
   :width: 1.5em
.. |newVectorLayer| image:: /static/common/mActionNewVectorLayer.png
   :width: 1.5em
.. |setProjection| image:: /static/common/mActionSetProjection.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
