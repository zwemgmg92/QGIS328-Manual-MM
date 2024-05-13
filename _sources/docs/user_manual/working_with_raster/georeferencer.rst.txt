.. index:: Georeferencing images
   single: Raster; Georeference
.. _`georef`:

မြေပုံမြေပြင်မှတ်ပုံတင်ရာ (Georeferencer)
==========================================

.. only:: html

   .. contents::
      :local:

|georefRun| Georeferencer ဆိုသည်မှာ layer များအတွက် world file (ဖိုင်အမျိုးစားတစ်မျိုး) များကို ဖန်တီးရန်အတွက် tool တစ်ခုဖြစ်ပါသည်။ ဤ tool ကိုအသုံးပြု၍
GeoTiff ဖိုင်အသစ်တစ်ခုဖန်တီးခြင်း သို့မဟုတ် ရှိနေပြီးသား ဓာတ်ပုံကို world file တစ်ခုပေါင်းထည့်ခြင်းဖြင့် raster သို့မဟုတ် vector ဖိုင်များကို geographic သို့မဟုတ် projected coordinate system များ ထည့်ပေးပါသည်။ Layer တစ်ခုကို georeferencing ပြုလုပ်ရန် အခြေခံနည်းလမ်းမှာ coordinate များ၏
တိကျသည့်တန်ဖိုးများကို အသုံးပြုပြီး layer ပေါ်တွင် point များထည့်ပေးခြင်း ဖြစ်ပါသည်။

**Features**

.. index::
   single: Tools; Georeferencer tools

.. _table_georeferencer_tools:

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - Icon
     - ရည်ရွယ်ချက်
     - Icon
     - ရည်ရွယ်ချက်
   * - |addRasterLayer|
     - Raster ကိုဖွင့်ရန်
     - |addOgrLayer|
     - Vector ကိုဖွင့်ရန်
   * - |start|
     - Georeferencing စတင်ပြုလုပ်ရန်
     -
     -
   * - |gdalScript|
     - GDAL Script ထုတ်ပေးရန်
     - |loadGCPpoints|
     - GCP (မြေပြင်ထိန်းချုပ်မှတ်) Point များ ထည့်သွင်းရန်
   * - |saveGCPPointsAs|
     - GCP (မြေပြင်ထိန်းချုပ်မှတ်) Point များကို ... အနေဖြင့် သိမ်းဆည်းရန်
     - |transformSettings|
     - အသွင်ပြောင်းခြင်း setting များ
   * - |addGCPPoint|
     - Point ပေါင်းထည့်ရန်
     - |deleteGCPPoint|
     - Point ကိုဖျက်ရန်
   * - |moveGCPPoint|
     - GCP Point ကိုနေရာရွှေ့ရန်
     - |pan|
     - မြင်ကွင်းရွှေ့ကြည့်ရန်
   * - |zoomIn|
     - မြင်ကွင်းချဲ့ကြည့်ရန်
     - |zoomOut|
     - မြင်ကွင်းချုံ့ကြည့်ရန်
   * - |zoomToLayer|
     - Layer ကို zoom ချဲ့ကြည့်ရန်
     - |zoomLast|
     - နောက်ဆုံးအရာကို zoom ပြုလုပ်ရန်
   * - |zoomNext|
     - နောက်ထပ်အရာတစ်ခုကို zoom ပြုလုပ်ရန်
     - |linkGeorefToQGis|
     - Georeferencer ကို QGIS နှင့်ချိတ်ဆက်ရန်
   * - |linkQGisToGeoref|
     - QGIS ကို Georeferencer နှင့်ချိတ်ဆက်ရန်
     - |fullHistogramStretch|
     - ကြိမ်နှုန်းပြဂရပ် ဆွဲ့ဆန့်မှု အပြည့်အစုံ (Full histogram stretch)
   * - |localHistogramStretch|
     - နေရာအလိုက် ကြိမ်နှုန်းပြဂရပ် ဆွဲ့ဆန့်မှု (Local histogram stretch)
     -
     -

Table Georeferencer - Georeferencer Tool များ

သာမန်လုပ်ရိုးလုပ်စဉ် (Usual procedure)
---------------------------------------

ဓာတ်ပုံပေါ်ရှိ ရွေးချယ်ထားသည့် point တစ်ခုနှင့်သက်ဆိုင်သည့် X နှင့် Y ကိုဩဒိနိတ်များ (ဒီဂရီ၊ မိနစ်၊ စက္ကန့် သို့မဟုတ် ဒဿမ ဒီဂရီ သို့မဟုတ် projected လုပ်ထားသည့် ဒသမ မီတာ) ကိုထည့်သွင်းသည့်အခါ လုပ်ရိုးလုပ်စဉ် နှစ်မျိုးကို အသုံးပြုနိုင်ပါသည်-

* တခါတရံ ဓာတ်ပုံပေါ်တွင် တည်နေရာတန်ဖိုးများ ရေးထားသည့် ကြက်ခြေခတ်အမှတ်အသားများ ‌ဖော်ပြထားတတ်ပါသည်။ ထိုအခြေအနေတွင် တည်နေရာတန်ဖိုးများကို လက်ဖြင့်ရိုက်ထည့်နိုင်ပါသည်။
* Georeference ပြုလုပ်ထားပြီးသား layer များကို အသုံးပြုခြင်း။ ထို layer များသည် ကိုယ် georeference ပြုလုပ်ချင်သည့် ဓာတ်ပုံပေါ်ရှိ objects/feature များနှင့်တူညီသော objects/feature များပါဝင်ပြီး လိုချင်သည့် projection လည်းပါဝင်သည့် vector သို့မဟုတ် raster data များဖြစ်ပါသည်။ ဤနည်းလမ်းတွင် QGIS map canvas ထဲ ထည့်သွင်းထားသည့် georeference ပြုလုပ်ထားပြီးသား dataset ပေါ်ကို click နှိပ်ပြီး ကိုဩဒိနိတ်တန်ဖိုးများကို ထည့်သွင်းနိုင်ပါသည်။

Georeferencing အတွက် သာမန်လုပ်ရိုးလုပ်စဉ်တွင် raster ပေါ်တွင် point များစွာရွေးချယ်ခြင်း၊ ၎င်းတို့၏ ကိုဩဒိနိတ်တန်ဖိုးများ သတ်မှတ်ပေးခြင်း၊
သင့်လျော်သော Transformation အမျိုးအစားရွေးချယ်ပေးခြင်းတို့ ပါဝင်ပါသည်။ ထည့်သွင်းလိုက်သည့် parameter နှင့် data ပေါ်မှာမူတည်ပြီး Georeferencer က
world file parameter များကို တွက်ထုတ်ပေးပါသည်။ ကိုဩဒိနိတ်တန်ဖိုး များများထည့်လေလေ ရလာသည့်ဓာတ်ပုံသည် ပိုပြီးတိကျမှန်ကန်လေလေဖြစ်ပါသည်။

ပထမဆုံးအဆင့်အဖြစ် QGIS ကိုဖွင့်လိုက်ပြီး QGIS menu bar တွင်ပေါ်နေသည့် :menuselection:`Layer -->` |georefRun| :menuselection:`Georeferencer` ကို နှိပ်ပါ။ :numref:`figure_georeferencer_dialog` တွင် ပြထားသည့်အတိုင်း Georeferencer dialog ပေါ်လာပါလိမ့်မည်။

ဤဥပမာအတွက် SDGS မှ Dakota တောင်ပိုင်း၏ topo မြေပုံတစ်ချပ်ကို အသုံးပြုထားပါသည်။ နောက်ပိုင်းတွင် ဤပုံကို GRASS :file:`spearfish60` တည်နေရာမှ data များနှင့် ယှဉ်တွဲပြီးကြည့်ရှုနိုင်ပါသည်။ Topo မြေပုံကို အောက်တွင်ပေးထားသော link မှတဆင့် download ရယူပါ။ https://grass.osgeo.org/sampledata/spearfish_toposheet.tar.gz

.. _figure_georeferencer_dialog:

.. figure:: img/georef.png
   :align: center

   Georeferencer Dialog


.. _`georeferencer_entering`:

မြေပြင်ထိန်းချုပ်မှတ်များ (GCPs) ထည့်သွင်းခြင်း (Entering ground control points (GCP))
.......................................................................................

#. Reference မလုပ်ရသေးသည့် raster တစ်ခုကို georeference စလုပ်ရန်အတွက် |addRasterLayer| ခလုတ်ကို အသုံးပြုပါ။ Raster ကို dialog ၏ အဓိကလုပ်ဆောင်မည့် window တွင် ပြသနေမည်ဖြစ်သည်။ Raster ပေါ်လာသည်နှင့် reference point များစတင်ထည့်သွင်းနိုင်ပါသည်။
   
#. :numref:`figure_georeferencer_add_points` ပုံတွင်ပြထားသည့်အတိုင်း |addGCPPoint| :sup:`Add Point` ခလုတ်ကို အသုံးပြုပါ။
   အဓိကအလုပ်လုပ်သည့်နေရာတွင် point များထည့်ပြီး ကိုဩဒိနိတ်တန်ဖိုးများ ထည့်သွင်းပါ။ ဤလုပ်ငန်းစဉ်အတွက် အောက်ပါနည်းလမ်းများကို အသုံးပြုနိုင်ပါသည်-

   - Raster ဓာတ်ပုံပေါ်တွင် point တစ်ခုထောက်ပြီး X နှင့် Y ကိုဩဒိနိတ်တန်ဖိုးများကို ရိုက်ထည့်ပါ။ ထို့နောက် point ၏ CRS (coordinate reference system) ကိုလည်း ရွေးချယ်ပါ။
   - Raster ဓာတ်ပုံပေါ်တွင် point တစ်ခုထောက်ပြီး QGIS map canvas ထဲတွင်ပေါ်နေသည့် georeference ပြုလုပ်ထားပြီးသား မြေပုံပေါ်က X နှင့် Y ကိုဩဒိနိတ်တန်ဖိုးများကို ရယူရန် |pencil| :sup:`From map canvas` ခလုတ်ကို အသုံးပြုပါ။ CRS ကို အလိုအလျောက် သတ်မှတ်ပေးမည်ဖြစ်သည်။
   
#. Point များဆက်ထည့်ပါ။ အနည်းဆုံး point ၄ ခုထည့်ရမှာဖြစ်ပြီး များများပိုထည့်လျှင် ပိုကောင်းပါသည်။ GCP point များ နေရာချရန်အတွက် zoom လုပ်ခြင်း၊ နေရာရွှေ့ကြည့်ခြင်းများ လုပ်ဆောင်နိုင်ရန် တခြား tool များလည်း ရှိပါသေးသည်။

#. Point များကိုပြင်ဆင်မှုများလုပ်ရန်လိုအပ်လျှင် |moveGCPPoint| tool ကို အသုံးပြုပြီး canvas ထဲတွင်သာမက georeferencing window ထဲတွင်ပါ နေရာရွှေ့ပြင်ဆင်နိုင်ပါသည်။

.. _figure_georeferencer_add_points:

.. figure:: img/choose_points.png
   :align: center

   Raster ဓာတ်ပုံကို point များထည့်သွင်းခြင်း


မြေပုံတွင် အသစ်ထည့်လိုက်သည့် point များကို သီးသန့် text file တစ်ခု (:file:`[filename].points`) အဖြစ် raster ဓာတ်ပုံနှင့်အတူရောပြီး သိမ်းဆည်းထားပါသည်။ နောက်ပိုင်း ကိုယ် georeferece လုပ်ထားသည့်ပုံကို ပြင်ဆင်ချင်သည့်အခါ ယခုသိမ်းထားသည့် file ကိုပြန်ဖွင့် (reload) ပြီး point များဖျက်ပစ်ခြင်း၊ အသစ်ထည့်ခြင်းများကို လုပ်ဆောင်နိုင်ပါသည်။ Point file ထဲတွင် ``mapX, mapY, pixelX, pixelY`` ပုံစံဖြင့် တန်ဖိုးများပါဝင်ပါသည်။ File များကို စီမံခန့်ခွဲရန် |loadGCPpoints| :sup:`Load GCP points` နှင့် |saveGCPPointsAs| :sup:`Save GCP points as` ခလုတ်များကို အသုံးပြုနိုင်ပါသည်။

.. _`georeferencer_transformation`:

Transformation setting များ သတ်မှတ်ပေးခြင်း (Defining the transformation settings)
...................................................................................

Raster ဓာတ်ပုံတွင် GCP များထည့်ပြီးနောက် georeferencing process အတွက် transformation setting များ သတ်မှတ်ပေးရန် လိုအပ်ပါသည်။

.. _figure_georeferencer_transform:

.. figure:: img/transformation_settings.png
   :align: center

   Georeferencer အတွက် transformation setting များသတ်မှတ်ပေးခြင်း


အသုံးပြုနိုင်သော Transformation algorithm များ (Available Transformation algorithms)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ကိုယ်အသုံးပြုမည့် data ၏ အရည်အသွေး၊ နောက်ဆုံးထွက်လာမည့်ပုံတွင် ကိုယ်လက်ခံနိုင်မယ့် ပုံမညီမညာတွန့်လိမ်မှု (geometric distortion) သဘာဝနှင့် ပမာဏ၊ GCP အရေအတွက်တို့ပေါ် မူတည်ပြီး အသုံးပြုလို့ရသည့် transformation algorithm အချို့ရှိပါသည်။

ယခုလက်ရှိတွင် အောက်ပါ :guilabel:`Transformation types` (Transformation အမျိုးအစား) များကို အသုံးပြုလို့ရနိုင်ပါသည်-

*  **Linear** algorithm ကို world file တစ်ခုဖန်တီးရန်အတွက် အသုံးပြုပြီး ၎င်းသည် raster pixel ကို အမှန်တကယ် ပြောင်းလဲလိုက်ခြင်း မဟုတ်သည့်အတွက်ကြောင့် တခြား algorithm များနှင့် မတူကွဲပြားပါသည်။ ဤနည်းလမ်းသည် ဓာတ်ပုံကို နေရာမှန်အောင် လုပ်ပေးပြီး စကေးကိုလည်း တသမတ်တည်း ဖြစ်အောင် ထားပါသည်။ သို့သော် ဓာတ်ပုံလှည့်ခြင်း (နာရီလက်တံအတိုင်း/နာရီလက်တံဆန့်ကျင့်ဘက်) သို့မဟုတ် အခြားပြောင်းလဲမှုများ လုပ်ဆောင်ပေးနိုင်မည်မဟုတ်ပါ။ ကိုယ် georeference လုပ်မည့်ပုံသည် ကောင်းမွန်ညီညာသည့်ပုံဖြစ်ပြီး အသုံးပြုမည့် CRS ကိုလည်းသိလျှင် ဤနည်းလမ်းသည် အသင့်တော်ဆုံးဖြစ်ပါသည်။ အနည်းဆုံး GCP ၂ ခု လိုအပ်ပါသည်။

*  **Helmert** transformation တွင်လည်း ဓာတ်ပုံကို လှည့်နိုင်ပါသည်။ ကိုယ့်နေရာဒေသအတွက် လုပ်ထားသည့် raster ပုံကောင်းကောင်းတစ်ခု သို့မဟုတ် orthoretified လုပ်ထားသည့် ကောင်းကင်ဓာတ်ပုံ ဖြစ်သော်လည်း ကိုယ်အသုံးပြုမည့် CRS ၏ grid line များနှင့်မကိုက်ညီသဖြင့် ချိန်ညှိလိုသည့် အခါမျိုးတွင် ဤနည်းလမ်းသည် အသုံးဝင်ပါသည်။ အနည်းဆုံး GCP ၂ ခု လိုအပ်ပါသည်။

*  **Polynomial 1** algorithm သည် ပိုပြီး ယေဘုယျဆန်သည့် အပြိုင်ချိတ်ဆက်ထားသော transformation တစ်ခုကို လုပ်ဆောင်ပေးသလို ညီညီညာညာ လေးထောင့်ဆန်သည့် ပုံများတွင်လည်း ကောင်းမွန်ပါသည်။ မျဉ်းဖြောင့်များသည် အဖြောင့်အတိုင်းရှိပြီး (မျဉ်းဖြောင့်ပေါ်ရှိ point များသည် ထိုမျဉ်းပေါ်မှ သွေဖယ်မသွားခြင်းကို ဆိုလိုသည်) မျဉ်းပြိုင်များကလည်း ပြိုင်လျှက်ပဲရှိရပါမည်။ ဦးတည်ရာအမျိုးမျိုးတွင် pixel အရွယ်အစား မတူညီဘဲဖန်တီးထားသည့် မြေပုံများကို georeferencing ပြုလုပ်ရာတွင် ဤနည်းလမ်းသည် အသုံးဝင်ပါသည်။ အနည်းဆုံး GCP ၃ ခု လိုအပ်ပါသည်။

*  **Polynomial** algorithms 2-3 သည် အပြိုင်ချိတ်ဆက်ထားသည့် transformation ကို သုံးမည့်အစား ပိုပြီးယေဘုယျဆန်သည့် ဒုတိယနှင့် တတိယအဆင့် polynomial များကိုအသုံးပြုပါသည်။ ထို့ကြောင့် ဤနည်းလမ်းသည် ခုံးနေသည့် သို့မဟုတ် အခြား စနစ်တကျလိမ်ကောက်နေသည့် ပုံများကို ကိုင်တွယ်ဖြေရှင်းနိုင်ပါသည်။ ဥပမာ - ကွေးခုံးနေသည့် အစွန်းများပါဝင်သည့် ဓာတ်ပုံများ။ အနည်းဆုံး GCP ၆ မှ ၁၀ ခုထိ လိုအပ်ပါသည်။ ဓာတ်ပုံတစ်ခုလုံးတွင် ထောင့်အကျဉ်းအကျယ်များနှင့် စကေးတချို့ ပြောင်းလဲသွားနိုင်ပါသည်။ မျဉ်းဖြောင့်များ ကွေးသွားနိုင်သလို ဓာတ်ပုံ၏အစွန်းဘက်များ (သို့မဟုတ်) GCP နှင့်ဝေးသည့်နေရာများတွင် တွန့်လိမ်မှုများ ဖြစ်ပေါ်နိုင်ပါသည်။

*  **Projective** algorithm သည် မတူညီသည့်ပြင်ညီနှစ်ခုဖြစ်သော ဓာတ်ပုံနှင့် map canvas ကြားမှာ ဗဟို projection တစ်ခုကို ကိုယ်စားပြုသည့် transformation နည်းလမ်းများကို အသုံးပြုပြီး polynomial 1 ကို ယေဘုယျဆန်ဆန်နည်းလမ်းဖြင့် လုပ်‌ဆောင်ပေးပါသည်။ မျဉ်းဖြောင့်များသည် အဖြောင့်အတိုင်း ဆက်ရှိနေပေမယ့် အပြိုင်မျဉ်းများနှင့် စကေးတချို့သည် ဓာတ်ပုံ၏အခြေအနေပေါ် မူတည်ပြီးပြောင်းလဲသွားပါသည်။ ကောင်းမွန်သော မြေပုံဖြစ်ပေမယ့် ဓာတ်ပုံရိုက်သည့်အခါ တည့်တည့်ရိုက်ထားတာမဟုတ်ဘဲ ဘေးစောင်းအခြေအနေမှ ရိုက်ထားသောပုံများ သို့မဟုတ် ဘေးစောင်းအခြေအနေမှ ရိုက်ကူးထားသော ကောင်းကင်ဓာတ်ပုံများအတွက် ဤနည်းလမ်းသည် အသင့်တော်ဆုံးဖြစ်ပါသည်။ အနည်းဆုံး GCP ၄ ခု လိုအပ်ပါသည်။

*  နောက်ဆုံးတစ်ခုမှာ **Thin Plate Spline** (TPS) algorithm ဖြစ်ပြီး အတတ်နိုင်ဆုံး မျက်နှာပြင်ခွက်နေ/ခုံးနေမှုကို လျော့ချထားသည့်မျက်နှာပြင်နှင့် GCP များကိုတွဲမိရန်အတွက် များစွာသော local polynomial များကို အသုံးပြုပြီး မြေပုံကိုလိုအပ်သလို ဆွဲယူချိန်ညှိခြင်းများ လုပ်ဆောင်ပါသည်။ GCP များကိုက်ညီရန် GCP နှင့်ဝေးနေသည့်နေရာများကို သင့်လျော်သလို ရွေ့လျားမှုများပြုလုပ်ပြီး မြေပုံကို ပိုမိုကောင်းမွန်စေရန် လုပ်ဆောင်ပေးပါသည်။ သို့သော် တတ်နိုင်သမျှ မူရင်းပုံသဏ္ဍာန်ပျက်မှု နည်းအောင် လုပ်ဆောင်ပေးပါသည်။ ပျက်နေသောပုံများ၊ သဏ္ဍာန်မမှန်သောပုံများ၊ အတန်သင့်မတိကျသောပုံများ နှင့် orthorectified ကောင်းကောင်းလုပ်မထားသော ကောင်းကင်ဓာတ်ပုံများကို georeferencing လုပ်ရန်အတွက် TPS နည်းလမ်းသည် အသင့်တော်ဆုံးဖြစ်ပါသည်။ ခန့်မှန်း georeferencing လုပ်ခြင်းနှင့် projection အမျိုးအစား (အခြား parameter များ) မသိသော မြေပုံများကို projection ပြန်လုပ်သည့်နေရာတွင်လည်း အသုံးဝင်ပါသည်။ သို့သော် ကိုယ့်မြေပုံပေါ်တွင် GCP ယူမည့်နေရာများကို တခြား georeferencing လုပ်ထားပြီးသားမြေပုံပေါ်တွင် ရှိနေပြီးသား feature များနှင့် ယှဉ်တွဲပေးရန်လိုအပ်ပါသည်။ အနည်းဆုံး GCP ၁၀ ခုလိုအပ်ပြီး များသောအားဖြင့် လိုချင်သည့်ပုံကောင်းတစ်ခုရရှိရန် ၁၀ ခုထက်ပိုသုံးရတတ်ပါသည်။

TPS မှလွဲပြီး အထက်တွင်ဖော်ပြခဲ့သည့် algorithm များအားလုံးသည် အနည်းဆုံးလိုအပ်သော GCP အရေအတွက်ထက် ပိုပြီးထည့်သည့်အခါ parameter များ အလိုအလျောက်ပြောင်းလဲသွားပြီး overall residual error (အမှားအကြွင်းကျန်) အနည်းဆုံးဖြစ်အောင် လုပ်ဆောင်ပေးပါသည်။
ဤနည်းလမ်းသည် regristration error များဖြစ်သည့် point ထောက်သောအခါ အနည်းငယ်လွဲချော်မှု၊ ကိုဩဒိနိတ်တန်ဖိုးထည့်သွင်းသည့်အခါ မှားယွင်းမှု နှင့် အခြား အသေးအမွှား ပုံပျက်နေမှုများ၏ နောက်ဆက်တွဲဆိုးကျိုးများကို အနည်းဆုံးဖြစ်အောင် လုပ်ဆောင်ပေးပါသည်။ အစားထိုးစရာ အခြား GCP များမရှိသောအခါ ၎င်းကဲ့သို့ အမှားများ သို့မဟုတ် ပုံပျက်နေခြင်းများက georeference လုပ်ထားသည့်ပုံများ၏ အစွန်ဘက်တွေမှာ တွန့်လိမ်မှုများ ဖြစ်စေနိုင်ပါသည်။ သို့သော် အနည်းဆုံးလိုအပ်သော GCP အရေအတွက်ထက် ပိုထည့်သည့်အခါ ထွက်လာသည့်ပုံတွင် ခန့်မှန်းပဲ ထည့်ပေးပါသည်။ နှိုင်းယှဉ်ကြည့်သည့်အခါ TPS က ထည့်လိုက်သည့် GCP များအားလုံးကို အတိအကျတွဲပေးသော်လည်း registration error များကြောင့် အနီးအနားရှိ GCP များအကြား  သိသိသာသာပုံပျက်မှုများ ဖြစ်စေနိုင်ပါသည်။

Resampling နည်းလမ်း သတ်မှတ်ခြင်း (Define the Resampling method)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ကိုယ်ရွေးချယ်သည့် resampling အမျိုးအစားသည် ထည့်သွင်းအသုံးပြုမည့် data နှင့် လုပ်ဆောင်မည့်အဓိကရည်ရွယ်ချက်ပေါ် မူတည်ပါသည်။ Raster ၏ ကိန်းဂဏန်းများကို မပြောင်းလဲလိုလျှင် 'Nearest neighbour' ကိုရွေးချယ်သင့်ပါသည်။ နှိုင်းယှဉ်ကြည့်လျှင် 'cubic resampling' သည် အမြင်အရ ပိုပြီးအဆင်ပြေချောမွေ့သည့် ဓာတ်ပုံကိုရစေပါသည်။

Resamping နည်းလမ်း ၅ မျိုးရွေးချယ်နိုင်ပါသည်-

#. Nearest neighbour
#. Linear
#. Cubic
#. Cubic Spline
#. Lanczos

Define the transformation settings (Transformation setting များ သတ်မှတ်ခြင်း) 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Georeference ပြုလုပ်ပြီးရရှိလာမည့် raster အတွက် သတ်မှတ်ပေးစရာ နည်းလမ်းများစွာရှိပါသည်။

* Linear tranformation အမျိုးအစားသည် raster ဓာတ်ပုံကို အမှန်တကယ်ပြောင်းလဲမည်မဟုတ်သည့်အတွက် ထိုနည်းကို အသုံးပြုမှသာ |checkbox| :guilabel:`Create world file` ကို အမှန်ခြစ်ပြီးရွေးချယ်လို့ရနိုင်ပါသည်။ ဤဖြစ်စဉ်တွင် world file အသစ်တစ်ခုကိုသာ ဖန်တီးပေးသည့်အတွက် :guilabel:`Output raster` field သည် activate ဖြစ်လာမည်မဟုတ်ပါ။

* အခြား transformation အမျိုးအစားများအားလုံးအတွက် :guilabel:`Output raster` တစ်ခုသတ်မှတ်ပေးရန်လိုအပ်ပါသည်။ ဘာမှမရွေးချယ်ပဲ ဒီအတိုင်းထားလျှင် မူရင်း folder ထဲတွင် ([filename]_modified) ဟုအမည်ပေးထားသည့် file အသစ်တစ်ခုအဖြစ် ဖန်တီးပြီး မူရင်း raster နှင့်အတူတူ သိမ်းထားပေးပါသည်။

* နောက်တစ်ဆင့်အနေဖြင့် ကိုယ် georeference လုပ်မည့် raster အတွက် :guilabel:`Target SRS` (Spatial Reference System) သတ်မှတ်ပေးရပါမည်။ (:ref:`label_projections` တွင်ကြည့်ပါ)

* ဆန္ဒရှိလျှင် **pdf မြေပုံတစ်ခုထုတ်** နိုင်သလို **pdf report** တစ်ခုလည်း ထုတ်ယူနိုင်ပါသည်။ Report ထဲတွင် အသုံးပြုခဲ့သည့် transformation parameter များ၊ residual များ၏ ဓာတ်ပုံတစ်ပုံ၊ GCP များနှင့် ၎င်းတို့၏ RMS (Root Mean Square) error များ စာရင်းတို့ ပါဝင်ပါသည်။

* ထို့အပြင် |checkbox| :guilabel:`Set Target Resolution` ကို အမှန်ခြစ်ရွေးချယ်ပြီး ouput raster အတွက် pixel resolution ကို သတ်မှတ်ပေးနိုင်ပါသည်။ မူရင်းပါရှိသည့် ရေပြင်ညီနှင့် ဒေါင်လိုက် resolution မှာ ၁ ဖြစ်သည်။

* Pixel တန်ဖိုး 0 ဖြစ်နေသောနေရာများကို ဘာမှမပေါ်ပဲ transparent အဖြစ်ထားလိုလျှင် |checkbox| :guilabel:`Use 0 for transparency when needed` ကို အမှန်ခြစ်ရွေးချယ်ထားလို့ရပါသည်။ နမူနာ toposheet တွင် အဖြူရောင် ဧရိယာအားလုံးသည် transparent ဖြစ်နေပါမည်။

* နောက်ဆုံးအဆင့်အနေဖြင့် |checkbox| :guilabel:`Load in QGIS when done` ကိုအမှန်ခြစ်ရွေးချယ်ထားလျှင် transformation လုပ်ပြီးသည်နှင့် ရလာသည့် raster သည် QGIS map canvas တွင် အလိုလိုပေါ်လာမည် ဖြစ်ပါသည်။

Raster property များပြသခြင်းနှင့် လက်ခကျင့်သုံးခြင်း (Show and adapt raster properties)
........................................................................................

Georeference ပြုလုပ်ချင်သော raster ၏ :ref:`Layer properties <raster_properties_dialog>` dialog ကိုဖွင့်ပြီး :guilabel:`Settings` ထဲရှိ :guilabel:`Raster properties` ကို နှိပ်လိုက်ပါ။

.. _configure_georeferencer:

Georeferencer အား ပြင်ဆင်ခြင်း (Configure the georeferencer)
.............................................................

* GCP ကိုဩဒိနိတ်တန်ဖိုးများနှင့် ၎င်းတို့၏ ID များကို ဖော်ပြထားမည်/ဖျောက်ထားမည် ကို သတ်မှတ်ပေးနိုင်ပါသည်။
* Residual units ၊ pixel နှင့် မြေပုံ ယူနစ်များကိုလည်း ရွေးချယ်နိုင်ပါသည်။
* PDF report အတွက် ဘယ်နှင့်ညာ အနားသတ်မျဉ်းကိုသတ်မှတ်ပေးနိုင်သလို PDF မြေပုံအတွက် စာရွက်အရွယ်အစားကိုလည်း သတ်မှတ်ပေးလို့ရပါသည်။
* နောက်ဆုံးအနေဖြင့် |checkbox| :guilabel:`Show Georeferencer window docked` ကိုလည်း အမှန်ခြစ်ပြီး activate လုပ်ထားလို့ရပါသည်။

.. _`georeferencer_running`:

Transformation ပြုလုပ်ခြင်း (Running the transformation)
.........................................................

GCP များစု‌စည်းပြီး transformation setting များကို သတ်မှတ်ပြီးနောက် georeference လုပ်ထားသည့် raster အသစ်တစ်ခု ဖန်တီးရန် |start| :sup:`Start georeferencing`
ခလုပ်ကိုနှိပ်ပါ။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addGCPPoint| image:: /static/common/mActionAddGCPPoint.png
   :width: 1.5em
.. |addOgrLayer| image:: /static/common/mActionAddOgrLayer.png
   :width: 1.5em
.. |addRasterLayer| image:: /static/common/mActionAddRasterLayer.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |deleteGCPPoint| image:: /static/common/mActionDeleteGCPPoint.png
   :width: 1.5em
.. |fullHistogramStretch| image:: /static/common/mActionFullHistogramStretch.png
   :width: 1.5em
.. |gdalScript| image:: /static/common/mActionGDALScript.png
   :width: 1.5em
.. |georefRun| image:: /static/common/mGeorefRun.png
   :width: 1.5em
.. |linkGeorefToQGis| image:: /static/common/mActionLinkGeorefToQGis.png
   :width: 2.5em
.. |linkQGisToGeoref| image:: /static/common/mActionLinkQGisToGeoref.png
   :width: 2.5em
.. |loadGCPpoints| image:: /static/common/mActionLoadGCPpoints.png
   :width: 1.5em
.. |localHistogramStretch| image:: /static/common/mActionLocalHistogramStretch.png
   :width: 1.5em
.. |moveGCPPoint| image:: /static/common/mActionMoveGCPPoint.png
   :width: 1.5em
.. |pan| image:: /static/common/mActionPan.png
   :width: 1.5em
.. |pencil| image:: /static/common/pencil.png
   :width: 1.5em
.. |saveGCPPointsAs| image:: /static/common/mActionSaveGCPpointsAs.png
   :width: 1.5em
.. |start| image:: /static/common/mActionStart.png
   :width: 1.5em
.. |transformSettings| image:: /static/common/mActionTransformSettings.png
   :width: 1.5em
.. |zoomIn| image:: /static/common/mActionZoomIn.png
   :width: 1.5em
.. |zoomLast| image:: /static/common/mActionZoomLast.png
   :width: 1.5em
.. |zoomNext| image:: /static/common/mActionZoomNext.png
   :width: 1.5em
.. |zoomOut| image:: /static/common/mActionZoomOut.png
   :width: 1.5em
.. |zoomToLayer| image:: /static/common/mActionZoomToLayer.png
   :width: 1.5em
