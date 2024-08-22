.. _authentication_overview:

Authentication System Overview (စစ်မှန်ကြောင်းအသိအမှတ်ပြုစနစ်အားခြုံငုံသုံးသပ်ချက်)
====================================================================================

.. only:: html

   .. contents::
      :local:

.. _figure_authsystem:

.. figure:: img/auth-system-overview.png
   :align: center

   စစ်မှန်ကြောင်းအသိအမှတ်ပြုစနစ်၏တည်ဆောက်ပုံ

Authentication database (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းဆိုင်ရာ database)
-------------------------------------------------------------------------

Authentication system (စစ်မှန်ကြောင်းအသိအမှတ်ပြုစနစ်) အသစ်သည် authentication configuration များ (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းဆိုင်ရာ ပြင်ဆင်သတ်မှတ်ခြင်းများ) ကို ပုံသေအနေဖြင့် :file:`<profile directory>/qgis-auth.db` ထဲမှ SQLite database file ထဲတွင်သိမ်းဆည်းထားပါသည်။

ဤ authentication database သည် ပုံမှန် QGIS setting များနှင့် လုံးဝတစ်သီးတစ်ခြားစီဖြစ်သောကြောင့် ၎င်းကို QGIS အတွင်းရှိ အခြားအသုံးပြုသူ၏စိတ်ကြိုက်ရွေးချယ်မှုများကို မထိခိုက်စေဘဲ QGIS ထည့်သွင်းမှုများကြားတွင် ရွှေ့ပြောင်းနိုင်သည်။ Database ထဲသို့ configuration တစ်ခုကို စတင်သိမ်းဆည်းသောအခါ "configuration ID" (ကျပန်းစာလုံး ၇ လုံးပါ အက္ခရာစဉ်ဂဏန်းစာတန်းတစ်ခု) တစ်ခုကို ထုတ်ပေးမည်ဖြစ်သည်။ Configuration ကိုကိုယ်စားပြုသည့် ၎င်း ID ကို ဆက်စပ်အထောက်အထားများ (credentials) ကိုဖော်ပြခြင်းမရှိဘဲ project ဖိုင်များ၊ plugin များ သို့မဟုတ် settings file များကဲ့သို့ application အစိတ်အပိုင်းများအတွင်း ရိုးရိုးစာသားဖြင့် သိမ်းဆည်းနိုင်ပါသည်။ 


.. note::
   `qgis-auth.db` ၏ ပင်မ ဖိုင်လမ်းကြောင်းအား environment variable ဖြစ်သော ``QGIS_AUTH_DB_DIR_PATH`` ကိုသုံး၍ သတ်မှတ်နိုင်သကဲ့သို့ ဆောင်ရွက်နေစဉ်အတွင်းတွင်  command-line ရွေးချယ်မှု ``--authdbdirectory`` ဖြင့်လည်း သတ်မှတ်နိုင်ပါသည်။

Master password (မာစတာ စကားဝှက်)
---------------------------------

Database အတွင်းတွင် အရေးကြီးအချက်အလက်များကို သိမ်းဆည်းရန် သို့မဟုတ် ဝင်ရောက်ရန်အတွက် `master password` တစ်ခုအားသတ်မှတ်ထားရှိရမည်ဖြစ်သည်။ ကုဒ်ဖြင့်ဝှက်ထားသောမည်သည့်အချက်အလက်များကိုမဆို database တွင် စတင်သိမ်းဆည်းသောအခါ စနစ်သည် အသုံးပြုသူအား မာစတာစကားဝှက်အသစ်ကို တောင်းဆို၍ အတည်ပြုခိုင်းပါလိမ့်မည်။ ထိုအရေးကြီး အချက်အလက်များအား ဝင်ရောက်အသုံးပြုသည့်အခါတိုင်း အသုံးပြုသူကို မာစတာ စကားဝှက် ထည့်သွင်းခိုင်းမည်ဖြစ်သည်။ အသုံးပြုသူအနေဖြင့် စကားဝှက်ဆိုင်ရာ သိမ်းဆည်းထားသော အချက်များကို ကိုယ်တိုင်ရှင်းလင်းရန် ရွေးချယ်မထားလျှင် စကားဝှက်အား လုပ်ငန်းစဉ်၏ကျန်ရှိသောလုပ်ဆောင်မှုအတွက် သိမ်းဆည်းထားပေးမည်ဖြစ်သည်။ (application ကိုမပိတ်ပစ်မီအထိ) Authentication system အသုံးပြုမှုဥပမာများဖြစ်သော ရှိရင်း authentication configuration တစ်ခုအားရွေးချယ်ခြင်း သို့မဟုတ် server configuration တစ်ခုတွင် configuration တစ်ခုအသုံးချခြင်း (ဥပမာ WMS layer တစ်ခုထည့်သွင်းခြင်း) တို့အတွက် စကားဝှက်အား ထည့်သွင်းရန်မလိုအပ်ပါ။

ကွန်ပျူတာထဲမှ ``Wallet/Keyring`` ထဲတွင် စကားဝှက်အားသိမ်းဆည်းရန်ရွေးချယ်နိုင်သည်။

.. _figure_masterpass:

.. figure:: img/auth-password-new_enter.png
   :align: center

   မာစတာ စကားဝှက်အသစ်အားထည့်သွင်းခြင်း

.. note::

   မာစတာ စကားဝှက်ပါဝင်သော ဖိုင်လမ်းကြောင်းတစ်ခုအား environment variable ဖြစ်သော ``QGIS_AUTH_PASSWORD_FILE`` အားအသုံးပြုခြင်းဖြင့် သတ်မှတ်နိုင်သည်။
   
Managing the master password (မာစတာ စကားဝှက်အားစီမံခန့်ခွဲခြင်း)
.................................................................

တစ်ကြိမ်သတ်မှတ်ပြီးသည်နှင့် မာစတာ စကားဝှက်အား ပြန်လည်သတ်မှတ်နိုင်သည်။ ပြန်လည်သတ်မှတ်ခြင်းမပြုမီ လက်ရှိ မာစတာ စကားဝှက် အားထည့်သွင်းပေးရန်လိုအပ်မည်ဖြစ်သည်။ ဤလုပ်ငန်းစဉ်အတွင်း လက်ရှိ database တစ်ခုလုံးအား backup ပြုလုပ်ထားနိုင်ပါသည်။

.. _figure_masterpass_reset:

.. figure:: img/auth-password-reset.png
   :align: center

   မာစတာ စကားဝှက်အားပြန်လည်သတ်မှတ်ခြင်း

အသုံးပြုသူသည် မာစတာ စကားဝှက်အား မေ့သွားလျှင် ပြန်လည်ရယူနိုင်မည့် သို့မဟုတ် လွှမ်းမိုးပယ်ဖျက်နိုင်မည့် နည်းလမ်းမရှိပါ။ ထို့အပြင် မာစတာ စကားဝှက် မသိရှိဘဲ လုံခြုံအောင်ကုဒ်ဖြင့်ဝှက်ထားသော (encrypted) အချက်အလက်များကို ပြန်လည်ရယူနိုင်မည့် နည်းလမ်းမရှိပါ။

အသုံးပြုသူတစ်ဦးသည် ၎င်းတို့၏ ရှိရင်း မာစတာ စကားဝှက်အား သုံးကြိမ်တိုင် မှားယွင်းထည့်သွင်းမိလျှင် dialog သည် database အားဖျက်ပစ်ရန် မေးမြန်းပါလိမ့်မည်။

.. _figure_masterpass_pwd:

.. figure:: img/auth-password-invalid-3times.png
   :align: center

   သုံးကြိမ်တိုင် မှားယွင်းစွာထည့်ပြီးနောက်ပေါ်လာသည့် စကားဝှက်ဆိုင်ရာသတိပေးချက်

Authentication Configurations (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းဆိုင်ရာ ပြင်ဆင်သတ်မှတ်ခြင်းများ)
----------------------------------------------------------------------------------------------

(:menuselection:`Settings --> Options`) ၏ :guilabel:`Authentication` tab ထဲရှိ :guilabel:`Configurations` မှတစ်ဆင့် authentication configuration များကိုစီမံနိုင်သည်။

.. _figure_authconfigeditor:

.. figure:: img/auth-editor-configs2.png
   :align: center

   Configuration များဆိုင်ရာ editor

Configuration အသစ်တစ်ခုအားထည့်သွင်းရန် |symbologyAdd| ခလုတ်အား အသုံးပြုပါ။ Configuration များအားဖယ်ရှားရန် |symbologyRemove| ခလုတ်အား အသုံးပြုပါ။ ရှိရင်း configuration များအားမွမ်းမံပြင်ဆင်ရန် |symbologyEdit| ခလုတ်အား အသုံးပြုပါ။

.. _figure_authconfigeditor_add:

.. figure:: img/auth-config-create_authcfg-id.png
   :align: center

   Configuration editor အတွင်း config ကို ထည့်သွင်းခြင်း

OWS service connection တစ်ခုအား ပြင်ဆင်သတ်မှတ်ခြင်း (configuration) ကဲ့သို့သော ပေးထားသည့် service connection တစ်ခုအား configuration ပြုလုပ်သောအခါ authentication configuration စီမံခန့်ခွဲမှုအတွက် တူညီသောလုပ်ငန်းစဉ်များ (ပေါင်းထည့်ခြင်း၊ တည်းဖြတ်ပြင်ဆင်ခြင်းနှင့် ဖယ်ရှားခြင်း) တို့ကိုဆောင်ရွက်နိုင်သည်။ ထိုကိစ္စအတွက် authentication database အတွင်းမှ configuration များအား အပြည့်အဝစီမံခန့်ခွဲရန် configuration selector အတွင်းတွင် လုပ်ဆောင်ချက် ခလုတ်များရှိပါသည်။ ဤကိစ္စတွင် ပို၍ ကျယ်ပြန့်သော configuration စီမံခန့်ခွဲမှုများပြုလုပ်ရန်မလိုအပ်သည့်အတွက် QGIS options ၏ :guilabel:`Authentication` tab ထဲရှိ :guilabel:`configurations` ထဲသို့သွားရန်မလိုအပ်ပါ။ 


.. _figure_authconfigeditor_wms:

.. figure:: img/auth-selector-wms-connection.png
   :align: center

   Authentication configuration ခလုတ်များဖြစ်သော :guilabel:`Add`၊ :guilabel:`Edit` နှင့် :guilabel:`Remove` များအားပြသနေသော WMS connection dialog

Authentication configuration တစ်ခုကို ဖန်တီးခြင်း သို့မဟုတ် တည်းဖြတ်ခြင်းပြုလုပ်သောအခါ လိုအပ်သောအချက်အလက်များမှာ အမည်တစ်ခု၊ authentication နည်းလမ်း တစ်ခုနှင့်  authentication နည်းလမ်းအတွက် လိုအပ်သော အချက်အလက်မှန်သမျှတို့ ဖြစ်ကြပါသည်။ (ရရှိနိုင်သော authentication အမျိုးအစားများအကြောင်းကိုပိုမို၍ သိရှိလိုပါက :ref:`authentication_methods` တွင်ကြည့်ရှုပါ)

.. _authentication_methods:

Authentication Methods (စစ်မှန်ကြောင်းအသိအမှတ်ပြုခြင်းဆိုင်ရာနည်းလမ်းများ)
---------------------------------------------------------------------------

ရရှိနိုင်သော authentication များအတွက် QGIS တွင် data provider plugin များကိုထောက်ပံ့ပေးသည့်နည်းအတိုင်းတူညီစွာဖြင့် C++ plugin များကို အသုံးပြုထားသည်။ ရွေးချယ်နိုင်သည့် Authentication နည်းလမ်းသည် resource/provider အတွက် လိုအပ်သော ဝင်ရောက်ခွင့်၊ ဥပမာ HTTP(S) သို့မဟုတ် database၊ နှင့် QGIS code နှင့် plugin နှစ်ခုစလုံးတွင်ထောက်ပံ့ပေးခြင်းရှိ/မရှိ တို့နှင့်ဆက်စပ်နေသည်။ ထို့ကြောင့် အချို့ authentication နည်းလမ်း plugin များကို authentication configuration selector ပြထားသည့်နေရာတိုင်းတွင် အသုံးပြု၍ရချင်မှရနိုင်ပါမည်။ ရရှိနိုင်သော authentication plugin များအပြင် ၎င်းတို့နှင့် ကိုက်ညီသော resource/provider များ၏ စာရင်းအား :menuselection:`Settings --> Options` ထဲသို့သွားရောက်၍ :guilabel:`Authentication` tabထဲမှ |options| :guilabel:`Installed Plugins` ခလုတ်အား click နှိပ်ပြီး ဝင်ရောက်ကြည့်ရှုနိုင်သည်။

.. _figure_authmethod:

.. figure:: img/auth-method-listing.png
   :align: center

   ရရှိနိုင်သည့် authentication နည်းလမ်း plugin များစာရင်း

QGIS အား recompile (ပြန်လည်စုစည်းရေးသား) လုပ်ရန်မလိုဘဲ authentication plugin အသစ်များကိုဖန်တီးနိုင်ပါသည်။ လက်ရှိတွင် C++ ဖြင့်သာ plugin များကိုထောက်ပံ့ပေးခြင်းကြောင့် အသစ်ဖန်တီးထားသော plugin အား အသုံးပြုနိုင်စေရန် QGIS အား restart လုပ်ရန်လိုအပ်ပါလိမ့်မည်။ Plugin အား လက်ရှိ ထည့်သွင်းထားသော QGIS တွင် ပေါင်းထည့်ရန် စီစဉ်ထားပါက ထို plugin သည် အသုံးပြုနေသော QGIS ဗားရှင်းနှင့် ကိုက်ညီမှုရှိစေရန် သေချာပါစေ။ 

.. _figure_authmethod_http:

.. figure:: img/auth-config-create_basic-auth.png
   :align: center

   အခြေခံ HTTP authentication configs

.. _figure_authmethod_esritoken:

.. figure:: img/auth-config-create_esritoken.png
   :align: center

   ESRI Token authentication configs

.. _figure_authmethod_oauth2:

.. figure:: img/auth-config-create_oauth2.png
   :align: center

   OAuth2 authentication configs

.. _figure_authmethod_pki:

.. figure:: img/auth-config-create_pem-der-paths.png
   :align: center

   PKI paths authentication configs

.. _figure_authmethod_pkcs:

.. figure:: img/auth-config-create_pkcs12-paths.png
   :align: center

   PKI PKCS#12 file paths authentication configs

.. _figure_authmethod_stored:

.. figure:: img/auth-config-create_stored-identity2.png
   :align: center

   သိမ်းဆည်းထားသော Identity authentication configs

.. note::

   Resource URL သည် လက်ရှိတွင် *အကောင်အထည်မပေါ်သေးသော* feature တစ်ခုဖြစ်ပြီး ၎င်းသည် ပေးထားသော URL တစ်ခုမှ resource များသို့ချိတ်ဆက်သောအခါ သီးသန့် configuration တစ်ခုအား နောက်ဆုံးတွင် အလိုအလျောက်ရွေးချယ်ခံရစေရန် ဆောင်ရွက်ပေးနိုင်မည်ဖြစ်သည်။

Master Password and Auth Config Utilities (မာစတာစကားဝှက် နှင့် Auth Config အသုံးဝင်ခြင်းများ )
-----------------------------------------------------------------------------------------------

:guilabel:`Authentication` tab ထဲရှိ options menu (:menuselection:`Settings --> Options`) အောက်တွင် authentication database နှင့် configurations များကို စီမံခန့်ခွဲနိုင်မည့်မြောက်များစွာသော utility (အသုံးဝင်ခြင်း) လုပ်ဆောင်ချက်များရှိပါသည်-

.. _figure_authconfiutils:

.. figure:: img/auth-editor-configs_utilities-menu.png
   :align: center

   Utilities menu

* **Input master password** - မည်သည့် authentication database command မျှဆောင်ရွက်ရန်မလိုဘဲ မာစတာစကားဝှက်အား ရိုက်ထည့်နိုင်မည့် dialog အားဖွင့်ပေးခြင်းဖြစ်သည်။
* **Clear cached master password** - အကယ်၍ မာစတာစကားဝှက်အားသတ်မှတ်ထားရှိပြီးလျှင် ၎င်းအား ပြန်ဖြုတ်ပေးခြင်းဖြစ်သည်။
* **Reset master password** - မာစတာစကားဝှက်အား ပြောင်းလဲရန်(လက်ရှိစကားဝှက်ကို သိရပါမည်) နှင့် connection များအားလုံး၏ လက်ရှိ database အား backup (မလုပ်လျှင်လဲရသည်) ပြုလုပ်ရန် dialogတစ်ခုကိုဖွင့်ပေးခြင်းဖြစ်သည်။ 
* **Clear network authentication access cache** - ချိတ်ဆက်မှုများအားလုံး၏ authentication cache အားရှင်းလင်းပေးခြင်းဖြစ်သည်။
* **Automatically clear network authentication access cache on SSL errors** - Connection cache သည် ချိတ်ဆက်မှု မအောင်မြင်သောအခါတွင်လည်း ချိတ်ဆက်မှုများအတွက် authentication data အားလုံးကို သိမ်းဆည်းထားသည်။ Authentication configuration များသို့မဟုတ် certification authorities များကိုပြောင်းလဲသောအခါ authentication cache ကိုရှင်းလင်းသင့်သည် သို့မဟုတ် QGIS ကို restart လုပ်သင့်ပါသည်။ ဤရွေးချယ်မှုအားဖွင့်ထားခြင်းဖြင့် SSL အမှားအယွင်းတစ်ခုပေါ်ပေါက်၍ connection ကိုဖျက်သိမ်းရန် ရွေးချယ်လိုက်သည့် အခါတိုင်း authentication cache အား အလိုအလျောက်ရှင်းလင်းပြီးဖြစ်သွားပါလိမ့်မည်။
* **Integrate master password with your Wallet/Keyring** - မာစတာစကားဝှက်အား ကိုယ်ပိုင် Wallet/Keyring ထဲသို့ ထည့်ပေးသည်။
* **Store/update the master password in your Wallet/Keyring** - Wallet/Keyring ထဲတွင် ပြောင်းလဲထားသော မာစတာစကားဝှက်အား update ပြုလုပ်ပေးသည်။
* **Clear the master password from your Wallet/Keyring** - Wallet/Keyring မှ မာစတာစကားဝှက်အားဖျက်ပေးပါသည်။
* **Enable password helper debug log** - Authentication နည်းလမ်းများ၏ မှတ်တမ်းအချက်အလက်များအားလုံးပါဝင်မည်ဖြစ်သော debug tool တစ်ခုအားဖွင့်ပေးခြင်းဖြစ်သည်။
* **Clear cached authentication configurations** - Configuration များ၏ internal lookup cache များကိုရှင်းလင်းပေးခြင်းဖြင့် ကွန်ရက်ချိတ်ဆက်မှုများအား အရှိန်မြှင့်တင်ပေးသည်။ ထိုသို့ရှင်းလင်းရာတွင် QGIS ပြန်လည်စတင်သည့်အခါ လိုအပ်မည့် QGIS ၏ အဓိကကွန်ရက်ဝင်ရောက်ခွင့် (core network access) manager မှ cache များကိုရှင်းပစ်မည်မဟုတ်ပါ။
* **Remove all authentication configurations** - အခြားသိမ်းဆည်းထားသည့် မှတ်တမ်းများကိုဖယ်ရှားခြင်းမပြုဘဲနှင့် configuration မှတ်တမ်းအားလုံး၏ database အားရှင်းလင်းပေးသည်။
* **Erase authentication database** - လက်ရှိ database ကို backup ပြုလုပ်ရန် နှင့် database ဇယားဖွဲ့စည်းပုံအား အပြည့်အစုံ ပြန်လည်တည်ဆောက်ရန် အချိန်ဇယားဆွဲပေးခြင်းဖြစ်သည်။ Project loading ကဲ့သို့သော အခြားလုပ်ငန်းစဉ်များမှ database ယာယီပျောက်ဆုံးခြင်းကြောင့် အနှောင့်အယှက်များနှင့် ပြဿနာများ မရှိစေရန် လုပ်ဆောင်ချက်များကို နောင်တချိန်အတွက် အချိန်ဇယားဆွဲထားခြင်းဖြစ်သည်။


  .. _figure_authconfiutilsdb:

  .. figure:: img/auth-db-erase.png
     :align: center

     DB ဖျက်ရန်အတည်ပြုချက် menu

Using authentication configurations (Authentication configuration များကို အသုံးပြုခြင်း)
-----------------------------------------------------------------------------------------

ပုံမှန်အားဖြင့် WMS ကဲ့သို့သော ကွန်ရက်ဝန်ဆောင်မှုများအတွက် authentication configuration တစ်ခုကို configuration dialog တစ်ခုထဲမှ ရွေးချယ်ပါသည်။ သို့သော်လည်း selector widget အား authentication လိုအပ်သည့်နေရာတိုင်းတွင်ထားရှိနိုင်သကဲ့သို့ တတိယပါတီ PyQGIS သို့မဟုတ် C++ plugin များကဲ့သို့ non-core functionality  (စနစ်၏အဓိကလုပ်ဆောင်မှုများတွင်မပါဝင်သောအရာများ) ထဲတွင်လည်းထားရှိနိုင်သည်။

Selector အားအသုံးပြုနေစဉ်တွင် မည်သည့်အရာကိုမျှရွေးချယ်မထားပါက၊ ရွေးချယ်နိုင်သည့် configuration များမရှိပါက သို့မဟုတ် database ထဲတွင် ယခင်ထည့်သွင်းခဲ့သော configuration အားရှာမတွေ့တော့ပါက pop-up menu control ထဲတွင် :guilabel:`No authentication` ဟု ပြသနေမည်ဖြစ်သည်။ 

:guilabel:`Type` နှင့် :guilabel:`Id` အကွက်များတွင် authentication နည်းလမ်းနှင့်  config’s ID တို့အား အသီးသီးဖော်ပြထားမည်ဖြစ်ပြီး ၎င်းတို့သည် ဖတ်ရုံနိုင်သာဖြစ်ပါသည်။

.. _figure_authconfigselector:

.. figure:: img/auth-selector-no-authentication.png
   :align: center

   Authentication မပါဝင်သည့် Authentication configuration selector

.. _figure_authconfigselector_pkcs:

.. figure:: img/auth-selector-pkcs12-authentication.png
   :align: center

   ရွေးချယ်ထားသည့် config ဖြင့် Authentication configuration selector

Python bindings (Python ပေါင်းစပ်ခြင်းများ)
--------------------------------------------

``QgsAuthCrypto`` class မှလွဲ၍ အခြား class များနှင့် public function များအားလုံးတွင် sip (Scalable Interactive Python) binding များရှိကြပါသည်။ အဘယ့်ကြောင့်ဆိုသော် မာစတာစကားဝှက်အား hash လုပ်ခြင်း (သီးသန့် algorithm တစ်ခုကို အသုံးပြု၍ မူရင်းမာစတာစကားဝှက်ကို သတ်မှတ်ထားသောပုံစံရှိသည့် စာကြောင်းအဖြစ်သို့ ပြောင်းလဲခြင်း) နှင့် authentication database အား ကုဒ်ဝှက်ခြင်း တို့ကဲ့သို့သောလုပ်ငန်းစဉ်များအား  Python မှတစ်ဆင့်မဟုတ်ဘဲ အဓိက app မှ စီမံခန့်ခွဲသင့်သောကြောင့်ဖြစ်သည်။ Python ဝင်ရောက်အသုံးပြုခွင့်နှင့်ပတ်သက်သည်များအတွက် :ref:`authentication_security_considerations` တွင် ကြည့်ရှုပါ။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
