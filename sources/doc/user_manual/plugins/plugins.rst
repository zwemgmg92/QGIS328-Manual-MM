.. index:: Plugins


.. _plugins:

********************************
QGIS Plugins (QGIS Plugin များ)
********************************

.. only:: html

   .. contents::
      :local:

QGIS ကို plugin architecture တစ်ခုဖြင့် ဒီဇိုင်းရေးဆွဲထားသောကြောင့် application တွင် feature (သွင်ပြင်လက္ခဏာ) အသစ်များနှင့် လုပ်ဆောင်ချက် (function) အသစ်များကို အလွယ်တကူထည့်သွင်းနိုင်ပါသည်။ QGIS ရှိ အချို့သော feature များကို plugin များအနေဖြင့် အကောင်အထည်ဖော်ထားကြပါသည်။ 


.. _core_and_external_plugins:

Core and External plugins (ပင်မ နှင့် ပြင်ပ plugin များ)
=========================================================

QGIS plugin များကို **Core Plugins (ပင်မ plugin များ)** သို့မဟုတ် **External Plugins (ပြင်ပ plugin များ)** များ တစ်ခုမဟုတ်တစ်ခုအဖြစ် ဖန်တီးထားကြပါသည်။ 

:ref:`Core Plugins (ပင်မ plugin များ) <core_plugins>` ကို QGIS ဖွံ့ဖြိုးတိုးတက်မှုအဖွဲ့မှ ထိန်းသိမ်းထားပြီး QGIS ဖြန့်ဝေမှုတိုင်းတွင် အလိုအလျောက်ပါဝင်သည့် အစိတ်အပိုင်းဖြစ်ပါသည်။ ၎င်းတို့ကို **C++** သို့မဟုတ် **Python** ဟုခေါ်သည့် ဘာသာစကားနှစ်မျိုးထဲမှ တစ်မျိုးဖြင့် ရေးသားထားခြင်းဖြစ်ပါသည်။  

ပြင်ပ plugin အများစုကို လက်ရှိတွင် Python ဖြင့် ရေးသားထားပါသည်။ ၎င်းတို့ကို https://plugins.qgis.org/plugins/  ရှိ 'Official' (တရားဝင်ဖြစ်သည့်) QGIS Repository (သိုလှောင်ရာနေရာ) တွင်လည်းကောင်း သို့မဟုတ် ပြင်ပ repository တွင် ရေးသားသူတစ်ဦးချင်းမှ ထိန်းသိမ်းထားခြင်းဖြင့်လည်းကောင်း သိမ်းဆည်းထားပါသည်။ Official repository တွင် plugin များအတွက် အသုံးပြုပုံ၊ အနိမ့်ဆုံး QGIS ဗားရှင်း၊ ပင်မစာမျက်နှာ၊ ရေးသားသူများနှင့် အခြားအရေးကြီးသည့်အချက်အလက်များနှင့်ပတ်သက်သည့် အသေးစိတ်မှတ်တမ်းများကို ကြည့်ရှုနိုင်မည်ဖြစ်ပါသည်။ အခြားသော ပြင်ပ repository များအတွက် မှတ်တမ်းမှတ်ရာများကို ပြင်ပ plugin များတွင် ရရှိနိုင်မည်ဖြစ်ပါသည်။ ပြင်ပ plugin နှင့်ပတ်သက်သည့် မှတ်တမ်းမှတ်ရာများမှာမူ ဤလက်စွဲစာအုပ်တွင် ပါဝင်မည်မဟုတ်ပါ။ 

Plugin တစ်ခုကို ထည့်သွင်းရန် သို့မဟုတ် စတင်အသုံးပြုရန် :menuselection:`Plugins` menu သို့သွားရောက်၍  |showPluginManager| :menuselection:`Manage and install plugins...` ကိုရွေးချယ်ပါ။ ထည့်သွင်းထားသည့် ပြင်ပ python plugin များကို အသုံးပြုနေသည့် :ref:`user profile <user_profiles>` လမ်းကြောင်း၏  :file:`python/plugins` folder အောက်တွင် ထားရှိမည်ဖြစ်ပါသည်။

စိတ်ကြိုက် C++ plugin library များသို့ လမ်းကြောင်းများကိုလည်း :menuselection:`Settings --> Options --> System` အောက်တွင် ပေါင်းထည့်နိုင်ပါသည်။ 

.. index::
   single: Plugins; Plugin manager

.. _managing_plugins:

The Plugins Dialog (Plugin များ Dialog)
========================================

.. _setting_plugins:

The Settings tab (Setting များ tab)
------------------------------------

ဘယ်ဘက် panel အောက်ခြေရှိ |transformSettings| :guilabel:`Settings` tab သည် application တွင် ဖော်ပြမည့် plugin များကို ပြင်ဆင်သတ်မှတ်နိုင်သည့် အဓိကနေရာတစ်ခုဖြစ်ပါသည်။ အောက်တွင်ဖော်ပြထားသည့်ရွေးချယ်စရာများကို အသုံးပြုနိုင်ပါသည်- 

* |checkbox| :guilabel:`Check for Updates on Startup` (စတင်အသုံးပြုချိန်တွင် update များကို စစ်ဆေးခြင်း)  QGIS တွင် ထည့်သွင်းထားသည့် plugin တစ်ခုသည် update ရရှိသည့်အချိန်တိုင်းတွင် QGIS သည် :guilabel:`Every Time QGIS starts` (QGIS စတင်သည့်အချိန်တိုင်း)၊ :guilabel:`Once a Day` (တစ်နေ့တစ်ကြိမ်)၊ :guilabel:`Every 3 Days` (သုံးရက်တစ်ကြိမ်)၊ :guilabel:`Every Week` (တစ်ပါတ်တစ်ကြိမ်)၊ :guilabel:`Every 2 Weeks` (နှစ်ပါတ်တစ်ကြိမ်) သို့မဟုတ် :guilabel:`Every month` (တစ်လတစ်ကြိမ်) အကြောင်းကြားပေးနေမည်ဖြစ်ပါသည်။ 
* |checkbox| :guilabel:`Show also Experimental Plugins` (စမ်းသပ်ဆဲ plugin များကိုလည်း ပြသခြင်း) QGIS သည် ယေဘုယျအားဖြင့် ထုတ်လုပ်သည့်အဆင့်သို့ မရောက်ရှိသေးသော ရေးဆွဲဆဲကာလ အစောပိုင်းအဆင့်များတွင် ရှိသေးသည့် plugin များကို ပြသမည်ဖြစ်ပါသည်။ ထို plugin များအတွက် ယုံကြည်စိတ်ချရသည့်ဗားရှင်း သို့မဟုတ် စမ်းသပ်ဆဲဗားရှင်းများကို ထည့်သွင်းနိုင်ပြီး ဗားရှင်းတစ်ခုမှ အခြားတစ်ခုသို့ အချိန်မရွေး ပြောင်းလဲအသုံးပြုနိုင်ပါသည်။
* |checkbox| :guilabel:`Show also Deprecated Plugins` (ဆက်လက်မရရှိနိုင်တော့သည့် plugin များကို ပြသခြင်း) ဤ plugin များကို QGIS တွင် အစားထိုးလုပ်‌ဆောင်ချက်များရှိခြင်း၊ ထိန်းသိမ်းကိုင်တွယ်မည့်သူမရှိခြင်းနှင့် QGIS တွင် ဆက်လက်မရရှိနိုင်တော့သည့် function များပေါ်တွင် မူတည်နေခြင်းတို့ကြောင့် ပုံမှန်အားဖြင့် ဆက်လက်၍ထိန်းသိမ်းပြုပြင်ခြင်းမရှိတော့ပေ။ ၎င်းတို့သည် ယေဘုယျအားဖြင့် အသုံးပြုရန်အတွက် မသင့်လျော်သည့် plugin များဖြစ်ပြီး plugin စာရင်းတွင် မီးခိုးရောင်ဖြင့် ဖော်ပြထားမည်ဖြစ်ပါသည်။ 

Default အားဖြင့် QGIS သည် :guilabel:`Plugin Repositories` section ထဲတွင် ၎င်း၏ official plugin repository ကို URL ``https://plugins.qgis.org/plugins/plugins.xml?qgis=version`` နှင့်အတူ ပံ့ပိုးပေးထားပါသည် (``<version>`` သည် အသုံးပြုနေသည့် QGIS ဗားရှင်းအတိအကျကို ကိုယ်စားပြုဖော်ပြခြင်းဖြစ်သည်)။ ပြင်ပ author repository များကို ထည့်သွင်းရန် |symbologyAdd| :guilabel:`Add...` ကို click နှိပ်၍  :guilabel:`Repository Details` (Repository အသေးစိတ်) form ထဲတွင် အမည် နှင့် URL ကိုဖြည့်သွင်းရပါမည်။ URLသည် ``http://`` သို့မဟုတ်  ``file://`` အမျိုးအစားဖြစ်ပါသည်။ 

Default QGIS repository သည် လွတ်လပ်စွာဝင်ရောက်နိုင်သည့် repository ဖြစ်ပြီး ၎င်းအတွင်းသို့ ဝင်ရောက်ရန် မည့်သည့် authentication (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်း) မှ မလိုအပ်ပေ။ ကိုယ်ပိုင် plugin repository ကို အသုံးပြုရာတွင်မူ authentication (အခြေခံ authentication၊ PKI) တစ်ခု လိုအပ်ပါသည်။ :ref:`authentication` အခန်းတွင် QGIS authentication အကူအညီနှင့် ပတ်သက်သည့် အချက်အလက်များကို ရရှိနိုင်ပါသည်။

ပေါင်းထည့်ထားသည့် repository တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသည့် repository များကို အသုံးမပြုလိုလျှင် Setting tab မှ |symbologyEdit| :guilabel:`Edit...` (ပြင်ဆင်တည်းဖြတ်ခြင်း) ခလုတ်ကို အသုံးပြု၍ ပိတ်ထားနိုင်သည်။ သို့မဟုတ် |symbologyRemove| :guilabel:`Delete` (ဖျက်ခြင်း) ခလုတ်ကိုနှိပ်၍လည်း အလုံးစုံ ဖယ်ရှားပစ်နိုင်ပါသည်။ 


.. _figure_plugins_settings:


.. figure:: img/plugins_settings.png
   :align: center

   |transformSettings| :guilabel:`Settings` tab
 
Browsing the plugins (Plugin များရှာဖွေခြင်း)
----------------------------------------------

Tab များ
........ 

:guilabel:`Plugins` dialog ရှိ အပေါ်ပိုင်း tab များသည် ၎င်းတို့၏ ထည့်သွင်းခြင်း၊ ဖန်တီးခြင်း သို့မဟုတ် အဆင့်မြှင့်တင်ခြင်းအခြေအနေများအပေါ်မူတည်၍ plugin များစာရင်းကို ဖော်ပြထားခြင်းဖြစ်သည်။ Plugin setting များပေါ်မူတည်၍ ရရှိနိုင်သော tab များသည် အောက်ပါတို့ဖြစ်နိုင်ပါသည်-

* |showPluginManager| :guilabel:`All` - ဖွင့်ထားသော repository များထဲတွင် ရရှိနိုင်သည့် plugin များအားလုံးကို ပြသပေးပါသည်။ 
* |pluginInstalled| :guilabel:`Installed` - ကိုယ်တိုင်ထည့်သွင်းထားသော plugin များနှင့် default အားဖြင့်ထည့်သွင်းပြီးဖြစ်ပြီး ဖယ်ရှား၍မရသော ပင်မ plugin များ နှစ်မျိုးစလုံးကို ပြသပေးပါသည်။
* |plugin| :guilabel:`Not installed` - ဖွင့်ထားသော repository များတွင် ဖယ်ရှားထားသော သို့မဟုတ် မထည့်သွင်းရသေးထည့် plugin များကို ပြသပေးပါသည်။
* |plugin-new| :guilabel:`New` - စတင်အသုံးပြုချိန်တွင် update ကို စစ်ဆေးခြင်း (:guilabel:`Check for Updates on Startup`) နောက်ဆုံးလုပ်ဆောင်ပြီးကတည်းက ဖြန့်ချိပေးသော plugin များကို ပြသပေးပါသည်။
* |plugin-upgrade| :guilabel:`Upgradeable` - Repository ထဲတွင် မကြာသေးမီက ထုတ်ထားသည့် ဗားရှင်းအသစ်ရှိသည့် ထည့်သွင်းပြီး plugin များကို ပြသပေးပါသည်။
* |pluginIncompatible| :guilabel:`Invalid` - တစ်စုံတစ်ခုသောအကြောင်း (ချိတ်ဆက်မှုလွဲချော်ခြင်း၊ plugin ထည့်သွင်းနေချိန်တွင် အမှားအယွင်းဖြစ်ခြင်း၊ QGIS ဗားရှင်းနှင့်မကိုက်ညီသည့် function များ....) ကြောင့် လက်ရှိတွင် ပျက်စီးနေသော အသုံးပြု၍မရသည့် ထည့်သွင်းထားသည့် plugin များအားလုံးကို ပြသပေးပါသည်။ 

Tab များ၏ထိပ်တွင် :guilabel:`Search` function သည် metadata အချက်အလက် (ရေးသားသူ၊ အမည်၊ ဖော်ပြချက်၊ ပူးတွဲအရာ၊.... ) များကို အသုံးပြု၍ plugin များကို ရှာဖွေရာတွင် ကူညီပေးပါသည်။

.. _figure_plugins_all:


.. figure:: img/plugins_all.png
   :align: center


   |showPluginManager| :guilabel:`All` tab မှ plugin တစ်ခုကို ရှာဖွေခြင်း


Plugin များ
............

Plugin တစ်ခုကိုရွေးချယ်လိုက်ပါက ညာဘက် panel တွင် metadata အချို့ကို ဖော်ပြထားမည်ဖြစ်သည်-

* Plugin သည် စမ်းသပ်ဆဲ သို့မဟုတ် စမ်းသပ်ဆဲဗားရှင်းကို ရရှိနိုင်ခြင်းနှင့်ပတ်သက်သည့် အချက်အလက်များ 
  (:guilabel:`Show also Experimental Plugins` ကိုအမှန်ခြစ်ထားပါက)  
* အကျဉ်းချုပ် နှင့် ရှင်းလင်းဖော်ပြချက်
* အဆင့်သတ်မှတ်၍ မဲပေးခြင်း(များ) (ကြိုက်နှစ်သက်သည့် plugin ကို မဲပေးနိုင်ပါသည်။) 
* ပူးတွဲအရာများ
* ပင်မစာမျက်နှာ၊ tracker နှင့် code repository သို့ ဝင်ရောက်နိုင်သော အသုံးဝင်သည့် လင့်ခ်များ
* ရေးသားသူ (များ) 
* Repository ထဲရှိ ဒေါင်းလုတ်ရယူနိုင်သည့်စာမျက်နှာသို့ ရောက်ရှိနိုင်သည့်လင့်ခ်နှင့်အတူ ဗားရှင်း(များ) သို့မဟုတ် ထည့်သွင်းပြီး plugin များအတွက် ကွန်ပျူတာအတွင်းရှိ folder သို့ ရောက်ရှိမည့် လမ်းကြောင်းများ 

:guilabel:`Plugin Manager` dialog သည် plugin များ၏ နောက်ဆုံးဗားရှင်းများနှင့် ချိတ်ဆက်ဆောင်ရွက်နိုင်မည်ဖြစ်သည်။ ဖွင့်ထားသည့်အခါတွင် နောက်ဆုံးထွက်သည့် ယုံကြည်စိတ်ချရသည့် ဗားရှင်းထက် ပို၍အသစ်ဖြစ်သော ဗားရှင်းရှိမှသာ စမ်းသပ်ဆဲဗားရှင်းကို ပြသမည်ဖြစ်ပါသည်။ Active ဖြစ်နေသော tab ပေါ်မူတည်၍ ရွေးချယ်ထားသည့် plugin သည် ထည့်သွင်းခြင်းရှိသည်ဖြစ်စေ၊ မရှိသည်ဖြစ်စေ အောက်ဖော်ပြပါ ရွေးချယ်စရာအချို့ကို ဖော်ပြမည်ဖြစ်ပါသည်- 

* :guilabel:`Install` - ရွေးချယ်ထားသည့် plugin ၏ နောက်ဆုံးထွက်သည့် ယုံကြည်စိတ်ချရသည့်ဗားရှင်းကို ထည့်သွင်းခြင်းဖြစ်သည်။
* :guilabel:`Install Experimental Plugin` - ရွေးချယ်ထားသည့် plugin ၏ စမ်းသပ်ဆဲဗားရှင်းကို ထည့်သွင်းခြင်းဖြစ်သည်။
* :guilabel:`Reinstall Plugin` - Plugin ၏ တူညီသော ယုံကြည်စိတ်ချရသည့်ဗားရှင်းကို ပြန်လည်ထည့်သွင်းခြင်း (ဥပမာ- ထည့်သွင်းအသုံးပြုရန် ကျရှုံးပြီးနောက်) ဖြစ်သည်။
* :guilabel:`Reinstall Experimental Plugin` - Plugin ၏ တူညီသော ယုံကြည်စိတ်ချရသည့်ဗားရှင်းကို ပြန်လည်ထည့်သွင်းခြင်း (ဥပမာ- ထည့်သွင်းအသုံးပြုရန် ကျရှုံးပြီးနောက်) ဖြစ်သည်။
* :guilabel:`Upgrade Plugin`- ရွေးချယ်ထားသည့် plugin ကို နောက်ဆုံးထွက်သည့် ယုံကြည်စိတ်ချရသော ဗားရှင်းသို့ အဆင့်မြှင့်တင်ခြင်းဖြစ်သည်။
* :guilabel:`Upgrade Experimental Plugin` - ရွေးချယ်ထားသော plugin ကို ၎င်း၏စမ်းသပ်ဆဲဗားရှင်းသို့ အဆင့်မြှင့်တင်ခြင်းဖြစ်သည်။
* :guilabel:`Upgrade All` - ထည့်သွင်းထားသည့် plugin များအားလုံးကို (ယခင်ဗားရှင်းသည် ယုံကြည်စိတ်ချရသည့်ဗားရှင်း သို့မဟုတ် စမ်းသပ်ဆဲဗားရှင်းဖြစ်မဖြစ်ပေါ် မူတည်၍) ၎င်းတို့၏ ပိုမိုအသစ်ဖြစ်သော ယုံကြည်စိတ်ချရသည့်ဗားရှင်း သို့မဟုတ် စမ်းသပ်ဆဲဗားရှင်းသို့ အဆင့်မြှင့်တင်ခြင်းဖြစ်သည်။ 
* :guilabel:`Downgrade Plugin` - Plugin ၏ စမ်းသပ်ဆဲဗားရှင်းမှ ယခင်ယုံကြည်စိတ်ချရသည့်ဗားရှင်းသို့ ရွှေ့ပြောင်းခြင်းဖြစ်သည်။
* :guilabel:`Downgrade Experimental Plugin` - Plugin ၏ စမ်းသပ်ဆဲဗားရှင်းမှ ၎င်း၏ နောက်ဆုံးထုတ်ပြန်ထားသည့် စမ်းသပ်ဆဲဗားရှင်းသို့ ရွှေ့ပြောင်းပေးပါသည်။ ၎င်းသည်  မထုတ်ပြန်ရသေးသည့်ဗားရှင်းနှင့် လုပ်ဆောင်သည့်အခါတွင် တွေ့ရမည်ဖြစ်ပါသည်။ 
* :guilabel:`Uninstall Plugin` - အသုံးပြုသူပရိုဖိုင်မှ ထည့်သွင်းထားသည့် plugin များကို ဖယ်ရှားခြင်းဖြစ်သည်။

ထည့်သွင်းပြီး plugin တစ်ခုသည် ၎င်း၏ဘယ်ဘက်တွင် |checkbox| အမှန်ခြစ်ပုံစံတစ်ခုကို ပြသမည်ဖြစ်ပြီး ၎င်းကို အမှန်ခြစ်ဖြုတ်လိုက်ပါက ယာယီအားဖြင့် ထို plugin ကိုပိတ်ထားနိုင်မည်ဖြစ်သည်။  

စာရင်း (list) ထဲရှိ plugin ပေါ်တွင် right-click နှိပ်၍ metadata အမျိုးမျိုးဖြင့် plugin များကို စီ (sort) နိုင်မည်ဖြစ်ပါသည်။ အသစ်ပေါ်လာမည့် အစီအစဉ်အတိုင်း tab အားလုံးတွင် အသုံးပြုသွားပါမည်။ Sort လုပ်ခြင်း ရွေးချယ်စရာများမှာ-  


* :guilabel:`Sort by Name` (အမည်အလိုက်စီခြင်း)
* :guilabel:`Sort by Downloads` (ဒေါင်းလုတ်ရယူခြင်းဖြင့်စီခြင်း) 
* :guilabel:`Sort by Vote` (မဲဖြင့်စီခြင်း)
* :guilabel:`Sort by Status` (ဖြစ်စဉ်အလိုက်စီခြင်း) 
* :guilabel:`Sort by Date Created` (ဖန်တီးထားသည့်နေ့ဖြင့် စီခြင်း) 
* :guilabel:`Sort by Date Updated` (အဆင့်မြှင့်တင်သည့်နေ့ဖြင့် စီခြင်း)


The Install from ZIP tab (ZIP မှ ထည့်သွင်းခြင်း tab) 
------------------------------------------------------

|installPluginFromZip| :guilabel:`Install from ZIP` tab တွင် plugin များကို zip ဖိုင်အမျိုးအစားဖြင့် ထည့်သွင်းရန် ဖိုင်ရွေးချယ်သည့် widget တစ်ခုကို ရရှိမည်ဖြစ်သည်၊ ဥပမာအားဖြင့်- ၎င်းတို့၏ repository မှ တိုက်ရိုက်ဒေါင်းလုတ်ရယူထားသည့် plugin များဖြစ်သည်။ ကုဒ်ဖြင့်ဝှက်ထားသည့် (encrypt) ဖိုင်များကိုလည်း အသုံးပြုနိုင်ပါသည်။


.. _figure_plugins_install_zip:


.. figure:: img/plugins_install_zip.png
   :align: center

   |installPluginFromZip| :guilabel:`Install from zip` tab
  
.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |installPluginFromZip| image:: /static/common/mActionInstallPluginFromZip.png
   :width: 1.5em
.. |plugin| image:: /static/common/plugin.png
   :width: 1.5em
.. |plugin-new| image:: /static/common/plugin-new.png
   :width: 1.5em
.. |plugin-upgrade| image:: /static/common/plugin-upgrade.png
   :width: 1.5em
.. |pluginIncompatible| image:: /static/common/plugin-incompatible.png
   :width: 1.5em
.. |pluginInstalled| image:: /static/common/plugin-installed.png
   :width: 1.5em
.. |showPluginManager| image:: /static/common/mActionShowPluginManager.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
.. |transformSettings| image:: /static/common/mActionTransformSettings.png
   :width: 1.5em