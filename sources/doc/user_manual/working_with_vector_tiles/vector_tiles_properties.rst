.. index:: Vector Tiles, vector tiles properties
.. _`label_vector_tiles`:

*****************************************************************
Working with Vector Tiles (Vector အကွက်များဖြင့် အလုပ်လုပ်ခြင်း)
*****************************************************************

.. only:: html

   .. contents::
      :local:

What are Vector Tiles? (Vector Tile များဆိုသည်မှာ ဘယ်လိုအရာတွေလဲ)
==================================================================

Vector tile များဆိုသည်မှာ ဝက်ဘ်ဆိုဒ်ပေါ်တွင် Transfer (ကူးပြောင်းမှု) ပြုလုပ်ရန်အတွက် 
ကြိုတင်ချမှတ်ထားသော စတုရန်းပုံစံဆန်ဆန် အကွက်များအတွင်း ပထဝီဝင်နှင့်ဆိုင်သော အချက်အလက်များကို 
ထည့်သွင်းသော အရာများဖြစ်ပါသည်။ ကြိုတင် ပုံဖော်ပြသထားသော Raster map Tiles များနှင့် 
Vector map Tiles များကို စုပေါင်းထားကြပါသည်။ Vector tile server သည် ကြိုတင် ပုံဖော်ပြသထားသော 
မြေပုံကိုဖော်ပြပေးမည့်အစား Tile တစ်ခုချင်းစီရဲ့ နယ်နိမိတ်အတိုင်းဖြတ်ထုတ်ထားသော Vector map data များကို 
ဖော်ပြပေးပါသည်။ ဖြတ်ထုတ်ထားသော Tiles များသည် ပိရမစ် ပုံစံအတိုင်း (Zoom-level တိုးလေလေ Tiles အရေအတွက်များလေလေ) 
Vector tile Service ရဲ့ zoom-levels (မြင်ကွင်းအချုံ့အချဲ့) ကို ကိုယ်စားပြုပါသည်။
ထိုပုံစံကိုအသုံးပြုသည့်အတွက် Un-tiled vector maps များနှင့် နှိုင်းယှဉ်ကြည့်တဲ့အခါ Data transfer လျော့နည်းပြီး ပိုမိုမြန်ဆန်လာပါသည်။
လက်ရှိ မြင်နေရတဲ့ မြေပုံမြင်ကွင်းနှင့် လက်ရှိ Zoom-level အတွင်းမှာရှိသည့် Data များကိုသာ Transfer လုပ်ပေးရန် လိုအပ်ပါသည်။
Tiled raster maps များနှင့် နှိုင်းယှဉ်ကြည့်တဲ့အခါမှာလည်း Vector data သည် Rendered (ပုံဖော်ပြသထားသော) bitmap ထက် များစွာသေးငယ်သောကြောင့် 
Data transfer လုပ်ရာတွင် များစွာလျော့နည်းစေပါသည်။ Vector tiles များတွင် သတ်မှတ်ထားသည့် Styling information တွေမပါရှိသည့်အတွက် 
Data များကို ကြည့်ရှုဖို့ရန်အတွက် QGIS တွင် Cartographic (မြေပုံဆွဲပြင်ဆင်ခြင်းနှင့်ဆိုင်သော) Style များ ပြင်ဆင်ပေးရန် လိုအပ်ပါသည်။

.. _figure_vector_tiles_pyramidstructure:

.. figure:: img/vector_tiles_pyramid_structure.png
   :align: center

   Zoom-levels အလိုက် Vector tiles များ၏ ပိရမစ်ပုံစံ တည်ဆောက်ပုံ


Supported Formats (အသုံးပြုနိုင်သည့် Format များ)
==================================================

Vector tiles များအတွက် အသုံးပြုနိုင်သည့် Format များမှာ-

* XYZ Template များအသုံးပြုသည့် အွန်လိုင်း Source များ (HTTP/S) - ``type=xyz&url=http://example.com/{z}/{x}/{y}.pbf``
* XYZ Template များအသုံးပြုသည့် ကွန်ပျူတာအတွင်းရှိ ဖိုင်များ - ဥပမာ ``type=xyz&url=file:///path/to/tiles/{z}/{x}/{y}.pbf``
* ကွန်ပျူတာအတွင်းရှိ MBTiles (Tiles အစုများကို သိုလှောင်ထားသော file format) Database - ဥပမာ ``type=mbtiles&url=file:///path/to/file.mbtiles``

Vector tiles dataset ကို QGIS အတွင်းသို့ ထည့်သွင်းရန် :guilabel:`Data Source Manager` dialog ထဲမှ |addVectorTileLayer| :guilabel:`Vector Tile` tab
ကို အသုံးပြုပါ။ အသေးစိတ်သိရှိလိုပါက :ref:`vector_tiles` တွင် ဖတ်ရှုနိုင်ပါသည်။

.. _vectortiles_properties:

Vector Tiles Dataset Properties (Vector Tiles Dataset များ၏ ဂုဏ်သတ္တိများ)
===========================================================================

Information Properties (အချက်အလက်နှင့်ဆိုင်ရာ ဂုဏ်သတ္တိများ)
-------------------------------------------------------------

:guilabel:`Information` tab သည် ဖတ်ရှုရုံသာ ဖြစ်ပြီး လက်ရှိအလွှာရဲ့ အကျဉ်းချုပ်အချက်အလက်နှင့် 
Metadata ကို ခပ်မြန်မြန်ကြည့်ရှုနိုင်သည့် စိတ်ဝင်စားစရာနေရာတစ်ခုဖြစ်ပါသည်။ ကြည့်ရှုလို့ရနိုင်သည့် အချက်အလက်များမှာ-

* အလွှာဖန်တီးသူပေါ်မူတည်ပြီး - အမည်၊ URI၊ အရင်းအမြစ်ပုံစံနှင့် ဖိုင်လမ်းကြောင်း၊ Zoom-levels အရေအတွက်
* Coordinate Reference System (CRS) - အမည်၊ ယူနစ်၊ နည်းလမ်း၊ တိကျမှု၊ အကိုးအကား
* :ref:`ဖြည့်သွင်းထားသည့် metadata <vectortilesmetadatamenu>` မှအချက်အလက်များ - အသုံးပြုခွင့်၊ အကျယ်အဝန်း၊ အချိတ်အဆက်များ၊ ဆက်သွယ်ရန်လိပ်စာများ၊ သမိုင်းကြောင်း အစရှိသည်…

Symbology and Label Properties (မြေပုံ သင်္ကေတများနှင့် အညွှန်းတပ်ခြင်း ဆိုင်ရာ ဂုဏ်သတ္တိများ)
-----------------------------------------------------------------------------------------------

.. _figure_vector_tile_symbology:

.. figure:: img/vector_tiles_symbology.png
   :align: center

   Vector Tile အလွှာ၏ Symbology

Vector tiles များတွင် Point၊ Line နှင့် Polygon များပါဝင်သည့်အတွက် ၎င်းတို့၏သက်ဆိုင်ရာ Symbols များ ရရှိနိုင်ပါသည်။ 
:guilabel:`Vector Tiles Connection` ကိုဖန်တီးရာတွင် Cartographic Style အတွက် :guilabel:`Style URL` 
ကိုအသုံးပြုရန် လိုအပ်ပါသည်။ :guilabel:`OK`ကို နှိပ်ပြီးတဲ့အခါ |symbology| :guilabel:`Symbology` tab တွင် 
ချက်ချင်းမြင်တွေ့ရမည်ဖြစ်သည်။


ကိုယ်ပိုင် Cartographic Style ဖန်တီးမည်ဆိုလျှင် Features များအတွက် :ref:`စည်းမျဉ်းအချို့ <rule_based_rendering>` ကို သတ်မှတ်ပေးပြီး 
ထို Style နှင့် Label ကို အသုံးပြုနိုင်ပါသည်။ :numref:`figure_vector_tile_symbology` တွင် OpenStreetMap ``landuse`` အလွှာအတွက် Style နှင့် Label ကို 
ပြင်ဆင်ထားသည်ကို မြင်တွေ့ရမည်ဖြစ်ပါသည်။ ဒီမှာဆိုရင် ``suburb`` ဆိုသည့် Class (အတန်းအစား) အတွက် အပြင်အဆင်များ ပြုလုပ်ထားပါသည်။
ပိုမိုပြီးကြည့်ရှုရအဆင်ပြေစေရန် စည်းမျဉ်းအများစုကို ရွေးချယ်ထားခြင်းမရှိပါဘူး။

အောက်ခြေတွင် :guilabel:`Current Zoom` (လက်ရှိ Zoom အခြေအနေ) ကိုပြသထားပါသည်။ သတ်မှတ်ထားသည့် Zoom level တွင်သာ မြင်ရနိုင်သည့် Rules များကို စစ်ထုတ်ရန်အတွက်
:guilabel:`Visible rules only` ကို အမှန်ခြစ်ပေးထားပါ။ ထိုသို့ပြုလုပ်ခြင်းဖြင့် ရှုပ်ထွေးသော Vector Styling များလုပ်ဆောင်ခြင်းနှင့် အဆင်မပြေဖြစ်စေသော
Rules များကို ဖော်ထုတ်ရာတွင် လွယ်ကူစေပါသည်။ Style နှင့် Labelling သည် Zoom level ပေါ်တွင် မူတည်နေနိုင်ပါသည်။

Styles များကို Import (ထည့်သွင်း) ပြုလုပ်ရန်အတွက်လည်း ရွေးချယ်စရာရှိပါသည်။ Import ပြုလုပ်လို့ရသည့် Styles ပုံစံတွေမှာ-

* :guilabel:`QML` ဖိုင်များ (:ref:`qgisstylefile`)
* :guilabel:`MapBox GL Json` Style ပုံသဏ္ဍာန် ဖိုင်များ

.. index:: Metadata, Metadata editor, Keyword
.. _vectortilesmetadatamenu:

Metadata Properties (Metadata ဂုဏ်သတ္တိများ)
---------------------------------------------

|editMetadata| :guilabel:`Metadata` tab တွင် အလွှာနဲ့ပတ်သက်သည့် Metadata report ကို ဖန်တီးခြင်းနှင့် ပြင်ဆင်ခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။ 
ပိုမိုသိရှိလိုသည်များအတွက် :ref:`metadatamenu` တွင် ကြည့်ရှုပါ။


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addVectorTileLayer| image:: /static/common/mActionAddVectorTileLayer.png
   :width: 1.5em
.. |editMetadata| image:: /static/common/editmetadata.png
   :width: 1.2em
.. |symbology| image:: /static/common/symbology.png
   :width: 2em
