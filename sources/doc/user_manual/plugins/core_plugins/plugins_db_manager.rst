.. index:: DB Manager
.. _dbmanager:

DB Manager Plugin (Database စီမံခန့်ခွဲသည့်အရာ Plugin)
=======================================================

DB Manager Plugin သည် QGISမှ လက်ခံနိုင်သော spatial (တည်နေရာဆိုင်ရာ) database များ (PostGIS၊  SpatiaLite၊ GeoPackage၊ Oracle Spatial၊ Virtual layers) ကို အသုံးပြုသူမျက်နှာပြင် (user interface) တစ်ခုတည်းတွင် ပေါင်းစပ်ပြီး စီမံခန့်ခွဲနိုင်သည့် အဓိကကိရိယာတစ်ခုဖြစ်ပါသည်။ |dbManager| :sup:`DB Manager` plugin သည် လုပ်ဆောင်ချက်အမျိုးမျိုးကိုလည်း ပံ့ပိုးပေးထားပါသည်။ QGIS browser မှ DB manager သို့ Layer များကို ဆွဲထည့်နိုင်ပြီး ထို Layer ကို spatial database အတွင်းသို့ ထည့်သွင်းပေးမည်ဖြစ်သည်။ Spatial database တစ်ခုနှင့်တစ်ခုကြား ဇယားများကို ဖိဆွဲ၍ ထည့်သွင်းနိုင်ပါသည်။

.. _figure_db_manager:

.. figure:: img/db_manager.png
   :align: center

   DB Manager dialog


:menuselection:`Database` menu သည် မူရင်းရှိပြီးသား database တစ်ခုနှင့် ချိတ်ဆက်ပေးနိုင်ပြီး SQL window ကို စတင်ခြင်းနှင့် DB Manager Plugin မှ ထွက်ခြင်းတို့ကို လုပ်ဆောင်နိုင်သည်။ မူရင်းရှိပြီးသား database နှင့် ချိတ်ဆက်ပြီးပါက :menuselection:`Schema` (PostGIS /PostgreSQL ကဲ့သို့သော DBMSs အတွက်သင့်လျော်သော) နှင့် :menuselection:`Table` menu များ ပေါ်လာမည်ဖြစ်ပါသည်။ 

:menuselection:`Schema` menu တွင် schema များကို ဖန်တီးရန်နှင့် ဖျက်ပစ်ရန်အတွက် (အလွတ်ဖြစ်လျှင်သာ)  tool များပါဝင်ပြီး အကယ်၍ ဆက်စပ်တည်ရှိမှုရအရ ဖွဲ့စည်းပုံ (topology) များကို ရရှိနိုင်မည်ဆိုပါက (ဥပမာ- PostGIS topology) :guilabel:`TopoViewer` တစ်ခုကို စတင်နိုင်မည်ဖြစ်ပါသည်။ 

:menuselection:`Table` သည် ဇယားများကို ပြင်ဆင်တည်းဖြတ်ခြင်း၊ ဖန်တီးခြင်းတို့ကို လုပ်ဆောင်စေနိုင်ပြီး မြင်ကွင်းနှင့် ဇယားများကို ဖျက်ပစ်နိုင်ပါသည်။ ၎င်းသည် ဇယားများအတွင်းရှိ data များကို ဖျက်ပစ်နိုင်ပြီး schema များအကြား ဇယားများကို ရွှေ့ပြောင်းနိုင်ပါသည်။ ထို့အပြင် ရွေးချယ်ထားသည့် ဇယားအတွက် :guilabel:`Vacuum Analyze` (နေရာလွတ်ဆန်းစစ်မှု) ကိုလည်း လုပ်ဆောင်နိုင်ပါသည်။ *Vacuum* သည် နေရာလွတ်များကို ပြန်လည်ရယူနိုင်ပြီး ပြန်လည်အသုံးပြုစေခြင်းဖြစ်ပြီး *analyze* သည် query တစ်ခုကိုလုပ်ဆောင်ရန် အထိရောက်ဆုံးနည်းလမ်းကိုဆုံးဖြတ်ရာတွင်အသုံးပြုသည့် စာရင်းအင်းအချက်အလက်များကို အဆင့်မြှင့်တင်ပေးခြင်းဖြစ်သည်။ :guilabel:`Change Logging...` (ပြောင်းလဲမှုများကို မှတ်တမ်းတင်ခြင်း)သည် ဇယားတွင် ပြောင်းလဲမှုများကို မှတ်တမ်းတင်သိမ်းဆည်းရန် ပံ့ပိုးပေးခြင်းဖြစ်သည်။ နောက်ဆုံးအနေဖြင့် :guilabel:`Import Layer/File...` (Layer/ဖိုင်ကို ထည့်သွင်းခြင်း) နှင့် :guilabel:`Export to File...` (ဖိုင်တစ်ခုအဖြစ် ထုတ်ယူခြင်း) တို့ကိုလည်း ပြုလုပ်နိုင်ပါသည်။     

.. note:: 
   DB Manager ကိုအသုံးပြု၍  PostgreSQL Database တစ်ခု၏ ဇယားများနှင့် column များအတွက် မှတ်ချက်များထည့်ပေးနိုင်ပါသည်။ 

:guilabel:`Providers` window သည် QGIS မှ လက်ခံနိုင်သော ရှိပြီးသား database များအားလုံးကို ပြုစုထားပါသည်။ Double-click နှိပ်ခြင်းဖြင့် database များနှင့် ချိတ်ဆက်နိုင်ပြီး right mouse ခလုတ်ကို နှိပ်ခြင်းဖြင့် နဂိုရှိပြီးသား ဇယားများနှင့် schema များကို အမည်ပြောင်းလဲခြင်းနှင့် ဖျက်ပစ်ခြင်းများ ပြုလုပ်နိုင်ပါသည်။ ဇယားများကို context menu မှတဆင့် QGIS canvas သို့လည်း ပေါင်းထည့်နိုင်ပါသည်။ 

Database နှင့်ချိတ်ဆက်ပြီးလျှင် DB Manager ၏ **အဓိက** window တွင် tab ၄ ခုကို မြင်တွေ့ရမည်ဖြစ်ပါသည်။ :guilabel:`Info` tab တွင် ဇယားနှင့် ၎င်း၏ဂျီဩမေတြီဆိုင်ရာ အချက်အလက်များအပြင် နဂိုရှိပြီးသား field များ၊ ကန့်သတ်ချက်များနှင့် ညွှန်းကိန်းများကိုလည်း တွေ့မြင်နိုင်မည်ဖြစ်ပါသည်။ ရွေးချယ်ထားသည့်ဇယားတွင် တည်နေရာညွှန်းကိန်းတစ်ခုကို ဖန်တီးနိုင်ပါသည်။ :guilabel:`Table` tab သည် ဇယားကို ဖော်ပြနေမည်ဖြစ်ပြီး :guilabel:`Preview` tab သည် ဂျီဩမေတြီများကို အကြိုကြည့်ရှုခြင်း (preview) အဖြစ် ပုံဖော်ပြသပေးပါသည်။ :guilabel:`SQL Window` ကို ဖွင့်လိုက်ပါက ၎င်းသည် tab အသစ်တစ်ခုအဖြစ် ပေါ်လာမည်ဖြစ်သည်။


Working with the SQL Window (SQL Window ဖြင့် အလုပ်လုပ်ခြင်း)
--------------------------------------------------------------

DB Manager ကို အသုံးပြု၍ spatial database နှင့်ပတ်သက်သည့် SQL query များကို လုပ်ဆောင်နိုင်ပါသည်။ Query များကို သိမ်းဆည်းခြင်းနှင့် ထည့်သွင်းခြင်းတို့ကို ပြုလုပ်နိုင်ပြီး :guilabel:`SQL Query Builder` (SQL query တည်ဆောက်ပေးသည့်အရာ) သည် query များကို ပုံသေနည်းထုတ်ရာတွင် ကူညီပေးပါသည်။  :guilabel:`Load as new layer` (Layer အသစ်အဖြစ် ထည့်သွင်းခြင်း) ကို အမှန်ခြစ်ခြင်းနှင့်  :guilabel:`Column(s) with unique values` (ထူးခြားသည့်သီးသန့်တန်ဖိုးများပါဝင်သည့် column များ)၊  :guilabel:`Geometry column` (ဂျီဩမေတြီ column)နှင့် :guilabel:`Layer name (prefix)` (Layer အမည် (အစစကားလုံး)) တို့ကို သတ်မှတ်ခြင်းအားဖြင့် ရရှိလာမည့် တည်နေရာကိုလည်း ကြည့်နိုင်ပါသည်။ :kbd:`Ctrl+R` သို့မဟုတ် :guilabel:`Execute` (စေခိုင်းလုပ်ဆောင်ခြင်း) ကို click နှိပ်ခြင်းဖြင့် လုပ်ဆောင်မည့် SQL ၏ အပိုင်းတစ်ခုကိုသာ execute လုပ်ဆောင်ရန် SQL ၏ထိုအစိတ်အပိုင်းကို ပေါ်လွင်စေရန် အရောင်တင်ဖော်ပြ (highlight) ပေးမည်ဖြစ်ပါသည်။  

:guilabel:`Query History` ခလုတ်သည် provider နှင့် database တစ်ခုချင်းစီ၏ နောက်ဆုံး query အခု (၂၀) ကို သိမ်းဆည်းပေးမည်ဖြစ်သည်။ 

Entry တစ်ခုကို click နှစ်ချက်နှိပ်ခြင်းဖြင့် SQL window တွင် string (စာသား) ကို ပေါင်းထည့်ပေးမည်ဖြစ်သည်။


.. _figure_db_manager_queries:


.. figure:: img/db_manager_sql.png
   :align: center

   DB Manager SQL window တွင် SQL query များကို စေခိုင်းလုပ်ဆောင်ခြင်း

.. note:: 
  
   Virtual Layers (Layer တု) များ ဖန်တီးရန်အတွက်လည်း SQL Window ကို အသုံးပြုနိုင်ပါသည်။ ဤဖြစ်စဉ်တွင် database ကိုရွေးချယ်မည့်အစား SQL Window ကို မဖွင့်မီ  **Virtual Layers** အောက်ရှိ **QGIS Layers** ကို ရွေးချယ်ရပါမည်။ အသုံးပြုရမည့် SQL syntax (ဝါကျဖွဲ့စည်းပုံ) များအတွက် ညွှန်ကြားချက်များကို သိရှိရန် :ref:`vector_virtual_layers` (Virtual layer များဖန်တီးခြင်း) တွင် ကြည့်ရှုနိုင်ပါသည်။ 



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em