.. Purpose: This chapter aims to describe the general interaction one can have with a 
 project file that does not belong to another particular section.

.. index:: Projects
.. _`project_files`:

********************************************************************
Working with Project Files (Project Files များဖြင့် အလုပ်လုပ်ခြင်း)
********************************************************************

.. only:: html

   .. contents::
      :local:


.. index:: Projects
.. _sec_projects:

Introducing QGIS projects (QGIS Project များအကြောင်းမိတ်ဆက်ခြင်း)
==================================================================
 
QGIS တွင် လုပ်ငန်းဆောင်တာတစ်ခုခုဆောင်ရွက်နေသည့်အခြေအနေအား Project ဟုခေါ်ပြီး တစ်ကြိမ်တွင်
Project တစ်ခုတည်းကိုသာ လုပ်ဆောင်နိုင်သည်။ Setting တစ်ခုသည် Project တစ်ခုအတွက် သီးသန့်ဖြစ်နိုင်သလို Project အသစ်များအတွက် Application တစ်ခုလုံးအတွက် မူရင်း Setting များလည်းဖြစ်နိုင်ပါသည်။ (:ref:`gui_options` အခန်းတွင်
အသေးစိတ်ကြည့်ရှုနိုင်သည်။) QGIS တွင် Menu Options ၌ ပါဝင်သည့် :menuselection:`Project -->` |fileSave| :menuselection:`Save` သို့မဟုတ်
:menuselection:`Project -->` |fileSaveAs| :menuselection:`Save As...` သို့ဝင်ရောက်၍	မိမိ လုပ်ဆောင်ထားသော လုပ်ငန်းအခြေအနေအား
:ref:`QGIS project file <qgisprojectfile>` တစ်ခုအဖြစ် သိမ်းဆည်းနိုင်သည်။

.. note::

  မိမိလုပ်ဆောင်ထားသော Project ကို ထပ်မံပြောင်းလဲပြင်ဆင်မှုများ ပြုလုပ်ပါက title bar တွင် ``*`` သင်္ကေတ
  ပေါ်လာမည်ဖြစ်ပြီး ပုံမှန်အားဖြင့် အဆိုပါ ပြောင်းလဲပြင်ဆင်မှုများကို သိမ်းဆည်းလိုခြင်း ရှိ/မရှိ ကို QGIS မှ မေးမြန်းပါလိမ့်မည်။ 
  အဆိုပါလုပ်ဆောင်ချက်ကို :menuselection:`Settings --> Options --> General` Setting အောက်ရှိ
  |checkbox| :guilabel:`Prompt to save project and data source changes when required` တွင် ထိန်းချုပ်ပြင်ဆင်နိုင်ပါသည်။

ယခင် လုပ်ဆောင်ထားပြီးဖြစ်သော project များကို QGIS တွင် ပြန်ဖွင့်လိုလျှင် Browser panel ကို အသုံးပြုနိုင်သကဲ့သို့ 
:menuselection:`Project -->` |fileOpen| :menuselection:`Open...` ၊
:menuselection:`Project --> New from template` သို့မဟုတ်
:menuselection:`Project --> Open Recent -->` လမ်းကြောင်းများမှ တဆင့် ဝင်ရောက်၍လည်း ဖွင့်နိုင်သည်။

QGIS ကို စတင်ဖွင့်လိုက်ပါက Screenshot များ၊ နာမည်များ နှင့် ဖိုင်လမ်းကြောင်းများပါဝင်သည့် :guilabel:`Project Templates` များနှင့်
:guilabel:`Recent Projects` (လတ်တလော လုပ်ဆောင်ခဲ့သည့် Project များ) list များကို Project အရေအတွက် (၁၀) ခုအထိ ဖော်ပြထားပါသည်။
:guilabel:`Recent Projects` သည် လတ်တလောအသုံးပြုခဲ့သော Project များကို ပြန်လည်လုပ်ဆောင်ရာတွင် အလွန်အသုံးဝင်သည်။ Project ဖိုင် သို့မဟုတ် Project template ကို  double-click နှိပ်၍ ဖွင့်နိုင်ပြီး
Entry ကို right-click နှိပ်လိုက်ပါက :guilabel:`Pin to List` ၊ :guilabel:`Open Directory...` သို့မဟုတ် :guilabel:`Remove from List` ဟူ၍
အခြားရွေးချယ်စရာများလည်း ပေါ်လာမည်ဖြစ်သည်။ Layer တစ်ခုကို ထည့်သွင်းလိုက်ခြင်းဖြင့်လည်း Project အသစ်တစ်ခုကို အလိုအလျောက် ဖန်တီးနိုင်ပါသည်။ ထို့နောက်တွင် ဖော်ပြနေသည့် list များသည် ပျောက်ကွယ်သွားမည်ဖြစ်ပြီး map canvas ပေါ်သို့ ရောက်ရှိသွားမည်ဖြစ်ပါသည်။

လုပ်ဆောင်နေသော Project ကို ပိတ်၍ Project အသစ်တစ်ခုစတင်လိုလျှင် :menuselection:`Project -->` |fileNew| :menuselection:`New` နှိပ်၍
စတင်နိုင်ပါသည်။ ဤသို့လုပ်ဆောင်ခြင်းဖြင့် လုပ်ဆောင်နေသော Project အား နောက်ဆုံးသိမ်းဆည်းထားသည့်ပုံစံအတိုင်း သိမ်းဆည်းသွားမည်ဖြစ်သည်။

Project အသစ်တစ်ခုကို စတင်သောအခါ ၎င်းဖိုင်ကို အမည်တစ်ခု သတ်မှတ်၍ မသိမ်းဆည်းမီအချိန် အထိ project ၏ title bar တွင်
``Untitled Project`` ဟု တွေ့မြင်ရမည်ဖြစ်သည်။

.. _figure_new_project:

.. figure:: img/new_project.png
   :align: center
 
   QGIS တွင် project အသစ်တစ်ခုကိုစတင်ခြင်း

Project file တစ်ခုအတွင်း သိမ်းဆည်းထားသော အချက်အလက်များတွင် အောက်ပါတို့ပါဝင်သည်-

* ထည့်သွင်းထားသော layer များ
* Query (သီးသန့်ခွဲထုတ်ကြည့်ရှုခြင်း) ပြုလုပ်နိုင်သော layer များ
* သင်္ကေတနှင့် ပုံစံများပါဝင်သော Layer properties များ
* Layer နှင့်ပတ်သက်သော အကြောင်းအရာမှတ်စုများ
* 2D နှင့် 3D မြေပုံမြင်ကွင်းများ
* Map view တစ်ခုချင်းစီအတွက် ပုံရိပ်ချစနစ်များ
* Map တစ်ခုချင်းစီအတွက် နောက်ဆုံးကြည့်ခဲ့သော extent (မြေပုံ၏နယ်ပယ်အကျယ်အဝန်း)
* Print ထုတ်ယူနိုင်သည့် Layouts အခင်းအကျင်းပုံစံများ
* Setting များပါဝင်သော Print ထုတ်ယူနိုင်သည့် layout ၏ အစိတ်အပိုင်းများ
* Print layout altas setting များ
* Digitize ပြုလုပ်နိုင်သည့် setting များ
* Table relation များ (ဇယားချိတ်ဆက်မှုများ)
* Project Macro များ
* Project ၏ မူရင်းပုံစံများ
* Plugins (အထူးလုပ်ဆောင်ချက်) setting များ
* Project properties ရှိ OWS setting tab မှ QGIS Server setting များ
* DB Manager တွင် သိမ်းဆည်းထားသော query များ

QGIS တွင် project ဖိုင်ကို XML ဖိုင်အမျိုးအစားဖြင့် သိမ်းဆည်းပြီး ထိုဖိုင်ကိုဖွင့်နိုင်သည့် QGIS မဟုတ်သော
အခြားနေရာတွင်လည်း ပြင်ဆင်တည်းဖြတ်နိုင်မည်ဖြစ်သည်။ (:ref:`qgisprojectfile` တွင် အ‌သေးစိတ်ကြည့်နိုင်ပါသည်) 
Project file format များကို အကြိမ်ကြိမ် update ပြုလုပ်ကြပါသည်။ ယခင် QGIS version အဟောင်းများမှ
project ဖိုင်များသည် နောက်ပိုင်းထွက်ပေါ်လာသော version အသစ်များတွင် ကိုက်ညီမှု ရှိနိုင်မည်မဟုတ်ပါ။

.. note::

  ပုံမှန်အားဖြင့် version မတူညီမှုကို သတိပေးချက်ကို တွေ့မြင်ရမည်ဖြစ်ပါသည်။ ၎င်းသတိပေးချက်ကို
  :menuselection:`Settings --> Options` ရှိ :guilabel:`General` tab မှ
  (|checkbox| :guilabel:`Warn when opening a project file saved with an older version of QGIS`)
  ကို အမှန်ခြစ်ပြုလုပ်၍ ဖွင့်ထားနိုင်ပါသည်။


QGIS တွင် project ဖိုင်တစ်ခု ကို ``.qgs`` အဖြစ် သိမ်းဆည်းလိုက်တိုင်း တူညီသည့်ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်းတစ်ခုတည်းတွင်
backup file တစ်ခုကို ``.qgs~`` ဖိုင်အမျိုးအစားဖြင့် အလိုအလျောက်သိမ်းဆည်းပြီးဖြစ်သည်။ QGIS Project အတွက်  သိမ်းဆည်းသည့်ဖိုင်အမျိုးအစားမှာ ``.qgs`` ဖြစ်သော်လည်း QGIS မှ သိမ်းဆည်းသည့်အခါတိုင်းတွင် 
ပုံမှန်အားဖြင့်  ``.qgz`` format ဖြင့်  ဖိုင်အရွယ်အစားချုံ့၍ သိမ်းဆည်းသည်။ ``.qgz`` format ဖြင့် ဖိုင်အရွယ်အစားချုံ့၍
သိမ်းဆည်းထားသည့် (zip archive) တွင် ``.qgs`` ဖိုင်နှင့်အတူ :ref:`auxiliary data <vector_auxiliary_storage>`
အတွက် ၎င်းနှင့်ဆက်စပ်လျက်ရှိသော SQLite database (``.qgd``) များပါ တွဲလျက်ပါဝင်သည်။ ထိုဖိုင်အားလုံးကို ``.qgz`` ဖိုင်အား 
unzip ပြုလုပ်၍ ရယူနိုင်ပါသည်။ 

.. note::

  :ref:`vector_auxiliary_storage` လုပ်ဆောင်ချက်သည် zip ပြုလုပ်ထားသော project ဖိုင်တွင် လိုအပ်သည့်
  auxiliary data (အကူဒေတာများ) ကိုပါ တပါတည်း ထည့်သွင်းသိမ်းဆည်းစေနိုင်သောကြောင့် လွန်စွာအသုံးဝင်သော လုပ်ဆောင်ချက်တစ်ခုဖြစ်ပါသည်။

.. _`saveprojecttodb`:

အောက်ဖော်ပြပါ menu item များ အသုံးပြု၍ Project ဖိုင်များကို PostgreSQL ၊ GeoPackage သို့မဟုတ်
Oracle databaseများမှ သိမ်းဆည်းနိုင်/ ပြန်လည် ထုတ်ယူ အသုံးပြုခြင်းများ ဆောင်ရွက်နိုင်ပါသည်-

* :menuselection:`Project --> Open from`
* :menuselection:`Project --> Save to`

ထို Menu item နှစ်ခုလုံးတွင် Project အား ထပ်မံသိမ်းဆည်းနိုင်သော နေရာများဖြစ်သည့် PostgreSQL၊ GeoPackage နှင့် Oracle များတွင်
ချိတ်ဆက်သိမ်းဆည်းနိုင်ရန် Menu အခွဲများပါရှိသည်။ ထို Menu item များကို click နှိပ်လိုက်လျှင် GeoPackage ၊ PostgreSQL ၊  schema ၊ Oracle ချိတ်ဆက်မှုများနှင့်
Project အား ချိတ်ဆက်နိုင်သည့်အပြင် အသုံးပြုသူနှင့် Project ကိုလည်း ချိတ်ဆက်နိုင်မည်ဖြစ်သည်။

GeoPackage ၊ PostgreSQL သို့မဟုတ် Oracle တို့တွင် သိမ်းဆည်းထားသော Project များကို QGIS browser panel မှ ဖွင့်၍လည်းကောင်း၊
အဆိုပါဖိုင်များကို double-click နှိပ်၍ လည်းကောင်း၊ map canvas ပေါ်သို့ ဖိဆွဲယူ၍လည်းကောင်း QGIS တွင် ထည့်သွင်းအသုံးပြုနိုင်ပါသည်။

.. _handle_broken_paths:

Handling broken file paths (လွှဲမှားနေသောဖိုင်လမ်းကြောင်းများကို ကိုင်တွယ်ခြင်း)
=================================================================================

Project ဖိုင်တစ်ခုကို ဖွင့်လိုက်သည့်အခါ မူရင်းဖိုင်တည်နေရာများအား ပြောင်းလဲခြင်း၊ အမည်ပြောင်းခြင်းများနှင့်
အချို့သော Service/Database များမရရှိနိုင်သည့်အခါမျိုးတွင် QGIS တွင် ဖွင့်မရသော data များ ပါဝင်လာတတ်သည်။
ထို data များပါဝင်ပါက :guilabel:`Handle Unavailable Layers` ဟူသည့်  Dialog window တစ်ခုပေါ်လာပြီး
ရှာမတွေ့သော Layer များကိုဖော်ပြမည်ဖြစ်သည်။ ထိုအခါ-

* Dialog window ရှိ :guilabel:`Datasource` field ကို Click နှစ်ချက်နှိပ်၍ Layer တစ်ခုချင်းစီ၏
  ဖိုင်သိမ်းဆည်းရာလမ်းကြောင်းကို ပြောင်းလဲပြင်ဆင်ပြီး :guilabel:`Apply changes` ကို နှိပ်ပါ။
* Row တစ်ခုကို Select လုပ်၍ ဖိုင်လမ်းကြောင်းအမှန်ကို ဖော်ပြရန်အတွက် :guilabel:`Browse` ကိုနှိပ်ပြီးနောက် :guilabel:`Apply changes` ကို နှိပ်ပါ။
* Folder များကို browse ပြုလုပ်ပြီး လွှဲမှားနေသော ဖိုင်လမ်းကြောင်းများကို အလိုအလျောက်ပြင်ဆင်ရန်အတွက် :guilabel:`Auto-Find` ကိုနှိပ်ပါ။
  သို့သော် ထိုသို့အလိုအလျောက်ရှာဖွေခြင်းသည် အချိန်အနည်းငယ်ကြာနိုင်သည်။ ရှာဖွေပြီးပါက  :guilabel:`Apply changes` ကို နှိပ်ပါ။
* ပေါ်လာသော message ကို လျစ်လှူရှုကာ လွှဲမှားနေသည့်ဖိုင်လမ်းကြောင်းများပါဝင်သည့် Project ကို :guilabel:`Keep Unavailable Layers` ကိုနှိပ်၍
  ဖွင့်ပါ။ ထိုအခါ Layer များသည် :guilabel:`Layers` panel တွင် ပေါ်လာမည်ဖြစ်သော်လည်း
  :guilabel:`Layers` panel အတွင်းရှိ layer ၏ဘေးရှိ |indicatorBadLayer| :sup:`Unavailable layer!` icon ကို နှိပ်၍ဖြစ်စေ
  Layer ၏ Context menu ရှိ :guilabel:`Repair Data Source...` ကိုနှိပ်၍ဖြစ်စေ ဖိုင်လမ်းကြောင်းအမှန်ကို
  မပြောင်းမချင်း မည်သည့်ဒေတာမှ ပါဝင်မည်မဟုတ်ပါ။ 

  :guilabel:`Repair Data Source...`  tool ကို သုံး၍ ဖိုင်လမ်းကြောင်းတစ်ခုအား ပြင်ဆင်ပြီးပါက
  QGIS သည် မှားယွင်းနေသည့်ဖိုင်လမ်းကြောင်းများအားလုံးကို scan ဖတ်ပေးပြီး ပြင်ဆင်ပြီးသည့်ဖိုင်လမ်းကြောင်းနှင့်အတူတူဖြစ်သည့် အခြားသော data များကိုပါ အလိုအလျောက်ပြင်ဆင်ပေးပါမည်။

* ထိုဖိုင်လမ်းကြောင်းလွှဲမှားနေသာ Layer များကို အလုပ်လုပ်နေသော Project အတွင်းမှ
  |deleteSelected| :guilabel:`Remove Unavailable Layers` မှတဆင့် ဖယ်ရှားနိုင်သည်။ 

:ref:`skipbadlayers` option ကို သုံး၍ QGIS အား Command line မှ ဖွင့်သောအခါ Project ဖွင့်ဖွင့်ချင်း၌
ပေါ်လာတတ်သည့် :guilabel:`Handle Unavailable Layers` dialog window ကို ကျော်လွှားနိုင်ပေလိမ့်မည်။

.. _`sec_output`:

Generating output (ရလာဒ်များ ထုတ်ခြင်း)
========================================

.. index:: Print layout, Quick print, World file
   single: Output; Save as image

QGIS မှ Output များ ထုတ်ရန် နည်းလမ်းများစွာရှိရာ Project ဖိုင်သိမ်းဆည်းခြင်းအကြောင်းကို
:ref:`sec_projects` တွင် ဆွေးနွေးပြီးဖြစ်သည်။ Output ထုတ်ရန် အခြားနည်းလမ်းများမှာ အောက်ပါအတိုင်းဖြစ်သည်-

* ရုပ်ပုံများဖန်တီးခြင်း - ရုပ်ပုံများ ထုတ်ယူနိုင်ရန်  :menuselection:`Project --> Import/Export -->` |saveMapAsImage| :menuselection:`Export Map to Image...` မှတဆင့်
  Map Canvas အား ဓာတ်ပုံအဖြစ် ပြောင်းလဲထုတ်ယူနိုင်ပြီး မိမိကြိုက်နှစ်သက်သော စကေး (Scale)၊ 
  အရွယ်အစားနှင့် ကြည်လင်ပြတ်သားမှု (Resolution) ကို PNG ၊ JPG ၊ TIFF အစရှိသော Format များအနက် ကြိုက်နှစ်သက်ရာ ရုပ်ပုံ Format ကို
  ရွေး၍ ထုတ်နိုင်သည်။ ထိုရုပ်ပုံတွင် ပထဝီဝင်ဆိုင်ရာအချက်အလက်များ ပါဝင်စေလိုလျှင် |checkbox| :guilabel:`Append georeference information (embedded or via world file)`
  ကို အမှန်ခြစ်ပြုလုပ်၍ ထုတ်နိုင်သည်။ (မြေပုံထုတ်ယူခြင်းအတွက် :ref:`exportingmapcanvas` တွင် အ‌သေးစိတ်လေ့လာနိုင်ပါသည်)
* PDF ဖိုင်အဖြစ် ပြောင်းလဲထုတ်ယူခြင်း - Map Canvas အား  PDF ဖိုင်အဖြစ် ပြောင်းလဲထုတ်ယူရန်
  :menuselection:`Project --> Import/Export --> Export Map to PDF...` အတိုင်း အလွယ်တကူ ထုတ်ယူနိုင်ပြီး 
  မိမိကြိုက်နှစ်သက်သော စကေး (Scale)၊ အရွယ်အစားနှင့် ကြည်လင်ပြတ်သားမှု (Resolution)ကို Simplication နှင့်
  Georeferencing ကဲ့သို့သော အခြား Setting များနှင့်အတူ ရွေးချယ်၍ ပြောင်းလဲထုတ်ယူနိုင်သည်။ (မြေပုံထုတ်ယူခြင်းအတွက်
  :ref:`exportingmapcanvas` တွင် အ‌သေးစိတ်လေ့လာနိုင်ပါသည်)
* DXF ဖိုင်အဖြစ် ပြောင်းလဲထုတ်ယူခြင်း - Project ကို DXF ဖိုင်အဖြစ် ပြောင်းလဲထုတ်ယူလိုလျှင်
  :menuselection:`Project --> Import/Export --> Export Project to DXF...` အတိုင်း ပြုလုပ်ပါက
  Dialog window တစ်ခုပေါ်လာမည်ဖြစ်ပြီး ထို dialog တွင် ကြိုက်နှစ်သက်ရာ 'Symbology mode' ၊ 'Symbology scale' နှင့် 
  vector layers တို့ကို ရွေးချယ်၍  DXF ဖိုင်အဖြစ် ထုတ်ယူနိုင်မည်ဖြစ်သည်။ 'Symbology mode' တွင် QGIS မှ ရရှိနိုင်သည့် symbol (သင်္ကေတ) များကို မှန်ကန်တိကျစွာ ထုတ်ယူနိုင်သည်။ (DXF ဖိုင်အသစ်ဖန်တီးခြင်း အခန်းကို :ref:`create_dxf_files` တွင် အသေးစိတ်လေ့လာနိုင်ပါသည်)
* မြေပုံဒီဇိုင်းများရေးဆွဲခြင်း - Project မြေပုံများအား စိတ်ကြိုက်ပြင်ဆင်ရေးဆွဲနိုင်ရန်
  :menuselection:`Project -->` |newLayout| :menuselection:`New Print Layout...` အတိုင်းဝင်လိုက်ပါက
  Dialog window တစ်ခုပေါ်လာမည်ဖြစ်ပြီး ထို dialog တွင် လက်ရှိ မြေပုံမြင်ကွင်းကို ပြင်ဆင်ရေးဆွဲခြင်း၊ print ထုတ်ခြင်းများပြုလုပ်နိုင်ပါသည်။
  (မြေပုံများပြင်ဆင်ရေးဆွဲခြင်းအခန်းကို :ref:`label_printlayout` တွင် အ‌သေးစိတ်လေ့လာနိုင်ပါသည်)


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |deleteSelected| image:: /static/common/mActionDeleteSelected.png
   :width: 1.5em
.. |fileNew| image:: /static/common/mActionFileNew.png
   :width: 1.5em
.. |fileOpen| image:: /static/common/mActionFileOpen.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |fileSaveAs| image:: /static/common/mActionFileSaveAs.png
   :width: 1.5em
.. |indicatorBadLayer| image:: /static/common/mIndicatorBadLayer.png
   :width: 1.5em
.. |newLayout| image:: /static/common/mActionNewLayout.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em


