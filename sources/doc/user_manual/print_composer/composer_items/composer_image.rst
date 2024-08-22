.. index:: Image, Picture, Layout; Image item, Layout; North arrow

The Marker, Picture and North Arrow Items (အမှတ်အသား၊ ရုပ်ပုံနှင့် မြောက်အရပ်ပြမြှား Item များ)
================================================================================================

.. only:: html

.. contents::
   :local:

Print layout (ပုံထုတ်အပြင်အဆင်) ထဲရှိ မြေပုံများ သို့မဟုတ် legend (မြေပုံရည်ညွှန်းချက်) များနှင့်အတူ မြေပုံကိုပိုမိုနားလည်နိုင်စေရန်အတွက် ရုပ်ပုံများနှင့် မှတ်ချက်စာများထည့်သွင်းနိုင်ပါသည်။ ထိုသို့ပြုလုပ်ရန် QGIS တွင် အမျိုးမျိုးသော tool များပါရှိသည်-

* :ref:`picture item <layout_picture_item>` - Raster ရုပ်ပုံတစ်ခု သို့မဟုတ် SVG file တစ်ခုဖြင့် layout အားအလှဆင်ပေးသည်။ (ဥပမာ- logo များ၊ ရုပ်ပုံများ၊ မြောက်အရပ်ပြမြှားများ ...အစရှိသည်)
* :ref:`north arrow item <layout_northarrow_item>` - မြောက်အရပ်ပြမြှားပုံတစ်ခုဖြင့် ကြိုတင် သတ်မှတ်ထားသော ရုပ်ပုံ item တစ်ခု 
* :ref:`marker item <layout_marker_item>` - QGIS vector :ref:`သင်္ကေတများ <symbol-selector>` ဖြင့် layout ကိုအလှဆင်နိုင်သည်။ ၎င်းကို မြေပုံတစ်ခုပေါ်တွင်အမှတ်အသားများထားရှိရန် သို့မဟုတ် အဆင့်မြင့် စိတ်ကြိုက် မြေပုံရည်ညွှန်းချက်များကိုဖန်တီးရန် အသုံးပြုနိုင်သည်။


.. _layout_picture_item:

The Picture Item (ရုပ်ပုံ Item)
--------------------------------

:ref:`Item များဖန်တီးခြင်းညွှန်ကြားချက် <create_layout_item>` ကိုလိုက်နာ၍ file manager ထဲမှရုပ်ပုံတစ်ခုကို ဖိဆွဲကာ canvas ပေါ်တွင်လွှတ်ချခြင်းဖြင့် ရုပ်ပုံတစ်ခုကိုထည့်သွင်းနိုင်သကဲ့သို့ :kbd:`Ctrl+V` သို့မဟုတ် :menuselection:`Edit --> Paste` အားအသုံးပြုခြင်းဖြင့် layout ထဲသို့ တိုက်ရိုက်ကူးထည့်ခြင်းဖြင့်လည်းကောင်း၊ |addImage| :sup:`Add Picture` ကိုအသုံးပြုခြင်းဖြင့်လည်းကောင်း ရုပ်ပုံတစ်ခုကို ထည့်သွင်းနိုင်ပါသည်။ ထို့နောက် ၎င်းကို :ref:`interact_layout_item` တွင်ရှင်းပြထားသည့်အတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။


.. index:: Picture database, Rotated north arrow

|addImage| :sup:`Add Picture` အားအသုံးပြုသောအခါ ရုပ်ပုံသည် ၎င်း၏ :guilabel:`Item Properties` panel အားအသုံးပြု၍ စိတ်ကြိုက်ပြင်ဆင်နိုင်သည့် frame အလွတ်တစ်ခုဖြစ်ပါလိမ့်မည်။ ဤ feature တွင် :ref:`item များ၏ common ဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည်-


Main properties (အဓိကဂုဏ်သတ္တိများ)
....................................

.. _figure_layout_image:

.. figure:: img/picture_mainproperties.png
   :align: center

   Picture Item ဂုဏ်သတ္တိများ panel

ရုပ်ပုံအတွက် ဓာတ်ပုံအမျိုးအစားနှစ်ခုမှာ-

* :guilabel:`Raster Image` - ဖိုင်ရွေးချယ်မှု widget တစ်ခုကိုအသုံးပြု၍ data များရယူနိုင်သည်။ :guilabel:`...` :sup:`Browse` ခလုတ်ကို အသုံးပြု၍ ကွန်ပျုတာရှိ file တစ်ခုကိုရွေးချယ်ပါ သို့မဟုတ် text field ထဲတွင် ဖိုင်လမ်းကြောင်းအားတိုက်ရိုက်ထည့်သွင်းပါ။ ရုပ်ပုံတစ်ခုသို့ ညွှန်းပေးမည့် URL (အင်တာနက်လိပ်စာ) ကိုလည်းထည့်သွင်းထားနိုင်သည်။ သက်ဆိုင်ရာပုံကို layout ထဲတွင်လည်း :ref:`embed (ထည့်သွင်းမြှုပ်နှံ) <embedded_file_selector>` လုပ်ထားနိုင်သည်။

  |dataDefine| :sup:`data defined override` ခလုတ်ကိုသုံး၍ feature attribute တစ်ခုမှဖြစ်စေ ပုံမှန် expression တစ်ခုကိုအသုံးပြုခြင်းမှဖြစ်စေ ရုပ်ပုံအရင်းအမြစ်ကို သတ်မှတ်နိုင်ပါသည်။
   
* :guilabel:`SVG Image` - :menuselection:`Settings --> Options --> System --> SVG Paths` ထဲရှိ Default အနေဖြင့်ပေးထားသော SVG library များအသုံးပြုခြင်းဖြစ်သည်။ သို့သော်လည်း အခြားမည်သည့် file ကိုမဆို အသုံးပြုနိုင်ပြီး file ရွေးချယ်မှုသည် raster ပုံရိပ်များအတွက်ကဲ့သို့ပင် ဖြစ်သည်။ SVG parameter များကိုလည်း dynamic (ပြောင်းလဲနိုင်သော) အဖြစ်သတ်မှတ်ထားနိုင်သည်။

  .. _parameterized_svg:

  QGIS တွင် ပါဝင်သည့် (default) :file:`.SVG` file များကိုစိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။ ဆိုလိုသည်မှာ :guilabel:`SVG Parameters` အုပ်စုထဲရှိ သက်ဆိုင်ရာ feature များကိုသုံး၍ မူရင်းချိန်ညှိမှုများအပြင် အခြား :guilabel:`Fill color` (အဖြည့်အရောင်)၊ :guilabel:`Stroke color` (လိုင်းအရောင်) နှင့် :guilabel:`Stroke width` (လိုင်းအထူ) များကိုအလွယ်တကူအသုံးပြုနိုင်သည်။ ဤဂုဏ်သတ္တိသည် :ref:`data-defined <data_defined>` (Data ဖြင့်သတ်မှတ်ထားသော) လည်းဖြစ်နိုင်ပါသည်။
  
  အကယ်၍ ဤဂုဏ်သတ္တိများကို မရရှိနိုင်သော :file:`.SVG` file တစ်ခုကို ထည့်မိပါက ဥပမာအားဖြင့် ဖောက်ထွင်းမြင်နိုင်မှုကဲ့သို့ feature များကို ထောက်ပံ့ပေးရန်အတွက် အောက်ပါ tag များ file တွင် ထည့်သွင်းရန်လိုအပ်ပါသည်-

  * `fill-opacity="param(fill-opacity)"`
  * `stroke-opacity="param(outline-opacity)"`

  ပိုမိုအသေးစိတ်ကျသည့်အချက်အလက်များကို :ref:`svg_symbol` တွင်ဖော်ပြထားသည်။

.. note:: ဓာတ်ပုံ file တစ်ခု (Raster သို့မဟုတ် SVG) ကို layout စာမျက်နှာထဲသို့ ဖိဆွဲ၍ထည့်ခြင်းသည် သက်ဆိုင်ရာ setting များပါဝင်သော layout ရုပ်ပုံတစ်ခုကို ဖန်တီးပေးမည်ဖြစ်သည်။


Size and placement (အရွယ်အစားနှင့်နေရာချထားမှု)
................................................

.. _figure_layout_picture_sizeplacement:

.. figure:: img/picture_sizeplacement.png
   :align: center

   Layout ထဲရှိ ရုပ်ပုံများ၏ အရွယ်အစားနှင့် နေရာချထားမှုဆိုင်ရာ ဂုဏ်သတ္တိများ

:guilabel:`Resize mode` option ဖြင့် frame ၏အရွယ်အစားပြန်လည်သတ်မှတ်လိုက်သောအခါ ရုပ်ပုံများကိုမည်သို့ပြသမည်ကို သတ်မှတ်နိုင်သည် -

* ``Zoom`` - ရုပ်ပုံ၏ ရှုထောင့်အချိုးကို ထိန်းထား၍ ဓာတ်ပုံအား frame နှင့် ကိုက်ညီစေရန် ချဲ့/ချုုံ့ ခြင်းပြုလုပ်ပေးသည်။ 
* ``Stretch`` - ဓာတ်ပုံအား frame ထဲတွင်ဝင်ဆံ့စေရန် ဆွဲဆန့်ပေးသည်။
* ``Clip`` - ဤ mode ကို raster ဓာတ်ပုံများအတွက်သာ အသုံးပြုပါသည်။ ဓာတ်ပုံ၏အရွယ်အစားကို စကေးပြောင်းလဲခြင်းမရှိဘဲ မူလဓာတ်ပုံအရွယ်အစားအတိုင်းထားရှိ၍ frame ဖြင့် clip (တိဖြတ်) လိုက်ခြင်းဖြစ်သည်။ ထို့ကြောင့် frame အတွင်းရှိသော ဓာတ်ပုံ၏ အပိုင်းကိုသာ မြင်ရပါမည်။ 
* ``Zoom and resize frame`` - Frame တွင်ဝင်ဆံ့စေရန် ဓာတ်ပုံကိုချဲ့လိုက်ခြင်းဖြစ်ပြီး ရရှိလာသော ဓာတ်ပုံ အတိုင်းအတာများနှင့် ကိုက်ညီစေရန် frame အရွယ်အစားကို ပြန်လည်သတ်မှတ်ခြင်းဖြစ်သည်။
* ``Resize frame to image size`` - ဓာတ်ပုံ၏မူလအရွယ်အစားနှင့်ကိုက်ညီစေရန် frame ၏အရွယ်အစားကိုသတ်မှတ်လိုက်ခြင်းဖြစ်သည် (စကေးပြောင်းလဲခြင်းမလုပ်ပါ)။


ရွေးချယ်ထားသည့် :guilabel:`Resize mode` ပေါ်မူတည်၍ :guilabel:`Placement` နှင့် :guilabel:`Image rotation` option များကိုပိတ်ထားနိုင်သည်။ :guilabel:`Placement` ဖြင့် ဓာတ်ပုံအား ၎င်း၏ frame အတွင်း ထားရှိရန်တည်နေရာ ကိုရွေးချယ်နိုင်သည် (အပေါ်/အလယ်/အောက် နှင့် ဘယ်/အလယ်ဗဟို/ညာ)။

.. _layout_images_rotation:

Image rotation (ဓာတ်ပုံများ လှည့်ခြင်း)
........................................

:guilabel:`Image rotation` field ဖြင့် ဓာတ်ပုံများကို လှည့်ပေးနိုင်ပါသည်။ |checkbox| :guilabel:`Sync with map` ကိုအမှန်ခြစ်ပေးထားခြင်းဖြင့် ရွေးချယ်ထားသည့်မြေပုံ item တွင်အသုံးပြုထားသော အလှည့် (rotation) အတိုင်း ဓာတ်ပုံများသည်လည်း လှည့်နေမည်ဖြစ်သည်။

မည်သည့်ရုပ်ပုံကိုမဆို မြောက်အရပ်ပြမြှားတစ်ခုကဲ့သို့အလုပ်လုပ်စေနိုင်ရန် အဆင်ပြေသော feature တစ်ခုဖြစ်သည်။ :guilabel:`North alignment` သည်-

* **Grid north**- နိုင်ငံလုံးဆိုင်ရာ/ဒေသန္တရ grid ၏ အလယ်ဗဟို (central) meridian နှင့်အပြိုင်ရှိသော grid မျဉ်းတစ်ခု၏လားရာ အတိုင်း
* **True north**- လောင်ဂျီတွဒ်မျဉ်း ၏ meridian တစ်ခု၏လားရာအတိုင်း ဖြစ်နိုင်သည်။

ရုပ်ပုံ၏ အလှည့် တွင် declination (အောက်သို့လျော့ကျခြင်း) :guilabel:`Offset` (အရွေ့) တစ်ခုကိုလည်းအသုံးပြုနိုင်သည်။

.. _figure_layout_picture_imagerotation:

.. figure:: img/picture_imagerotation.png
   :align: center

   Layout ရုပ်ပုံများလှည့်ခြင်းဆိုင်ရာ ဂုဏ်သတ္တိများ


.. index:: North arrow
.. _layout_northarrow_item:

The North Arrow Item (မြောက်အရပ်ပြမြှား Item)
----------------------------------------------

:ref:`Item များဖန်တီးခြင်းညွှန်ကြားချက် <create_layout_item>` ကိုလိုက်နာ၍ |northArrow|:sup:`Add North Arrow` ခလုတ်ဖြင့် မြောက်အရပ်ပြမြှားတစ်ခုကိုထည့်သွင်းနိုင်ပြီး ၎င်းကို :ref:`interact_layout_item` တွင်ဖော်ပြထားသည့် နည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်သည်။

မြောက်အရပ်ပြမြှားများသည် ဓာတ်ပုံများဖြစ်သောကြောင့် :guilabel:`North Arrow` တွင် :ref:`picture item <layout_picture_item>` ကဲ့သို့ပင်တူညီသောဂုဏ်သတ္တိများရှိပါသည်။ အဓိကကွာခြားချက်များမှာ-

* Item ကိုထည့်သွင်းသောအခါ frame အလွတ်တစ်ခုအစား default မြောက်အရပ်ပြမြှားတစ်ခုကို အသုံးပြုပါသည်။
* Default အားဖြင့် မြောက်အရပ်ပြမြှားအား မြေပုံ item တစ်ခုနှင့် sync လုပ်ထားသည် - :guilabel:`Sync with map` property သည် မြောက်အရပ်ပြမြှားအား ရေးဆွဲမည့် မြေပုံဖြစ်သည်။ အကယ်၍မရှိပါက :ref:`reference map <reference_map>` (ရည်ညွှန်းမြေပုံ) အားရယူအသုံးပြုမည်ဖြစ်သည်။
   
.. note::

   မြောက်အရပ်ပြမြှားပုံ များစွာတွင် မြှား၌ 'N' စာလုံးမထည့်သွင်းထားပါ။ အချို့ဘာသာစကားများတွင် 'N' စာလုံးကို North အဖြစ်အသုံးမပြုကြသည့်အတွက် ထည့်သွင်းမထားခြင်းဖြစ်သည်။
   
.. _figure_layout_image_north:

.. figure:: img/north_arrows.png
   :align: center

   SVG library တွင်ပေးထားသော ရွေးချယ်နိုင်သည့် မြောက်အရပ်ပြမြှားများ

.. _layout_marker_item:

The Marker Item (အမှတ်အသား Item)
---------------------------------

အမှတ်အသားတစ်ခုကိုထည့်သွင်းရန် |addMarker| :sup:`Add Marker` ခလုတ်ကိုရွေးချယ်၍ စာမျက်နှာပေါ်တွင် click နှိပ်ပါ။ Default အမှတ်သင်္ကေတတစ်ခုကိုထည့်သွင်းပြီးဖြစ်သွားပါမည်။ ထို့နောက် ၎င်းကို :ref:`interact_layout_item` တွင် ဖော်ပြထားသည့်အတိုင်း ကိုင်တွယ်နိုင်မည်ဖြစ်ပါသည်။ သို့သော် သတိပြုရမည်မှာ အခြား item များနှင့်မတူညီသည့်အချက်အနေနှင့် ၎င်းအမှတ်အသား၏အရွယ်အစားသည် ထည့်သွင်းမြှုပ်နှံထားသည့် သင်္ကေတများ၏ ဂုဏ်သတ္တိများအတိုင်းဖြစ်သောကြောင့် ပေးထားသော item ၏အရွယ်အစားကိုပြန်လည်ချိန်ညှိရမည်ဖြစ်သည်။

:guilabel:`Item Properties` panel မှတစ်ဆင့် အမှတ်အသား item များကိုစိတ်ကြိုက်ပြင်ဆင်နိုင်မည်ဖြစ်သည်။ :ref:`Item များ၏ common ဂုဏ်သတ္တိများ <item_common_properties>` အပြင် အောက်ပါတို့ကိုလည်းလုပ်ဆောင်နိုင်ပါသည် -


* သင်္ကေတဆိုင်ရာ :ref:`widget လုပ်ဆောင်နိုင်စွမ်းများ <symbol-selector>` အားလုံးကို မီခို၍ :guilabel:`Symbol` ကို ပြုပြင်မွမ်းမံနိုင်သည်။
* မြောက်အရပ်ပြမြှား၏လုပ်ဆောင်ချက်အတိုင်းပင် အမှတ်အသား၏ အလှည့် အား မြေပုံ item ၏အလှည့် နှင့် sync ပြုလုပ်နိုင်သည် (:ref:`layout_images_rotation` ကိုကြည့်ပါ)။ မြေပုံအလှည့်အား နဂိုရှိပြီးသား အမှတ်အသားသင်္ကေတ လှည့်ခြင်းမှန်သမျှ နှင့်ပေါင်းစပ်လိုက်မည်ဖြစ်သည် (ထို့ကြောင့် ဥပမာအားဖြင့်- တြိဂံအမှတ်အသားတစ်ခုကို အထက်သို့တည့်တည့်ညွှန်ပြစေရန် 90° လှည့်ပါက ၎င်းသည် မြောက်အရပ်ပြမြှား mode တွင်လည်း ကောင်းမွန်စွာအလုပ်လုပ်နေဆဲ ဖြစ်ပါလိမ့်မည်)။

.. _figure_layout_marker:

.. figure:: img/marker_mainproperties.png
   :align: center

   အမှတ်အသား item အတွက်စိတ်ကြိုက်ပြင်ဆင်နိုင်သော ဂုဏ်သတ္တိများ

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addImage| image:: /static/common/mActionAddImage.png
   :width: 1.5em
.. |addMarker| image:: /static/common/mActionAddMarker.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |northArrow| image:: /static/common/north_arrow.png
   :width: 1.5em
