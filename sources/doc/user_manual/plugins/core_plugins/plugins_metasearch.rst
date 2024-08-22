.. index:: Catalog services, Metadata
   single: plugins; MetaSearch
.. _metasearch:


MetaSearch Catalog Client
==========================
.. only:: html


   .. contents::
      :local:


Introduction (မိတ်ဆက်)
-----------------------

Metasearch (ဘက်စုံရှာဖွေမှု) သည် OGC API - Records နှင့် Web (CSW) စံချိန်စံနှုန်းများအတွက် OGC Catalog Service နှစ်မျိုးလုံးကို အထောက်အကူပြုထားသော metadata catalog service များနှင့် အပြန်အလှန်လုပ်ဆောင်နိုင်သော QGIS plugin တစ်ခုဖြစ်ပါသည်။

MetaSearch သည် QGIS အတွင်းရှိ metadata catalog များကို ရှာဖွေရာတွင် လွယ်ကူပြီး အလိုအလျောက်အသုံးပြုနိုင်သည့်အပြင် အသုံးပြုရလွယ်ကူသော မျက်နှာပြင်တစ်ခုကို ပံ့ပိုးပေးထားပါသည်။

.. _figure_metasearch_results:

.. figure:: img/metasearch-splash.png
   :align: center

   MetaSearch အတွင်း ရှာဖွေမှုနှင့် service များ၏ရလဒ်များ


Working with Metadata Catalogs in QGIS (QGIS ထဲတွင် Metadata Catalog များဖြင့် ဆောင်ရွက်ခြင်း)
-----------------------------------------------------------------------------------------------

MetaSearch သည် QGIS တွင် ၎င်း၏ဆက်စပ်ရာများနှင့်အတူ default အနေဖြင့်ပါဝင်ပြီး QGIS plugin manager မှတဆင့်လုပ်ဆောင်နိုင်ပါသည်။

OGC API - Records
..................

`OGC API - Records`_ သည် ဝက်ဘ်ပေါ်တွင် ပထဝီသတင်းအချက်အလက်အရင်းအမြစ်များကို ရှာဖွေခြင်းအတွက် `OGC (Open Geospatial Consortium)`_ (အခမဲ့ရယူအသုံးပြုနိုင်သော ပထဝီဝင်သတင်းအချက်အလက်ဆိုင်ရာအဖွဲ့) စံပုံစံတစ်ခုဖြစ်ပါသည်။

CSW (Catalog Service for the Web) (CSW (ဝက်ဘ်အတွက် Catalog ဝန်ဆောင်မှု))
.........................................................................

`CSW (Catalog Service for the Web)`_ သည် အချက်အလက်၊ ဝန်ဆောင်မှုများနှင့် အခြားသောအလားအလာရှိသည့်အရင်းအမြစ်များနှင့်ပတ်သက်သော metadata များကို ရှာဖွေရန်၊ ကြည့်ရှုရန်၊ သီးသန့်ခွဲထုတ်ကြည့်ရှုရန် ယေဘုယျမျက်နှာပြင်များကို သတ်မှတ်ပေးသော `OGC (Open Geospatial Consortium)`_ သီးခြားသတ်မှတ်ချက်တစ်ခုဖြစ်ပါသည်။


Startup (စတင်ခြင်း)
....................

MetaSearch ကို စတင်ရန် |metasearch| (ဘက်စုံရှာဖွေမှု) icon ကိုနှိပ်ပါ သို့မဟုတ် QGIS ပင်မ menu မှတဆင့် :menuselection:`Web --> MetaSearch --> MetaSearch` ကိုရွေးချယ်ပါ။ Metasearch dialog ကို တွေ့မြင်ရမည်ဖြစ်ပါသည်။ ပင်မ GUI တွင် :guilabel:`Services` (ဝန်ဆောင်မှုများ)၊ :guilabel:`Search` (ရှာဖွေမှု) နှင့် :guilabel:`Settings` (ချိန်ညှိခြင်းများ) ဟူ၍ အပိုင်း (၃)ပိုင်းပါရှိပါသည်။

Managing Catalog Services (Catalog ဝန်ဆောင်မှုများကို စီမံခန့်ခွဲခြင်း)
........................................................................

.. _figure_metasearch_catalog:

.. figure:: img/metasearch-services.png
   :align: center

   Catalog ဝန်ဆောင်မှုများကို စီမံခန့်ခွဲခြင်း

:guilabel:`Services` (ဝန်ဆောင်မှုများ) tab သည် ရရှိနိုင်သော catalog ဝန်ဆောင်မှုများအားလုံးကို အသုံးပြုသူမှ စီမံဆောင်ရွက်နိုင်ရန်ခွင့်ပြုပေးထားပါသည်။ MetaSearch တွင် catalog ဝန်ဆောင်မှုများပါဝင်သည့် default စာရင်းတစ်ခုရှိပြီး ၎င်းတွင် ဝန်ဆောင်မှုများကို :guilabel:`Add Default Services` ခလုတ်ကိုနှိပ်၍ ထည့်သွင်းနိုင်ပါသည်။

စာရင်းထဲရှိ Catalog ဝန်ဆောင်မှု အားလုံးကိုရှာဖွေရန် dropdown ရွေးချယ်စရာ box ကို click နှိပ်ပါ။

Catalog ဝန်ဆောင်မှု entry (ထည့်သွင်းမှု) တစ်ခုကို ပေါင်းထည့်ရန်- 


#. :guilabel:`New` ခလုတ်ကိုနှိပ်ပါ။
#. ဝန်ဆောင်မှုအတွက် :guilabel:`Name` တစ်ခုနှင့် :guilabel:`URL` (endpoint) ကိုထည့်သွင်းပါ။ မှတ်သားထားရန်မှာ OGC CSW 2.0.2 Catalog များအတွက် အခြေခံ URL (GetCapabilities URL အပြည့်အစုံမဟုတ်ပါ) သာလိုအပ်ပြီး OGC API - Records Catalog များအတွက် URL သည် စုစည်းမှု endpoint သို့ရောက်သော လမ်းကြောင်း ဖြစ်သင့်ပါသည်။
#. Catalog သည် စစ်မှန်ကြောင်းအတည်ပြုခြင်းကို လိုအပ်လျှင် သင့်တော်သော အထောက်အထား (credential) များဖြစ်သည့် :guilabel:`User name` (အသုံးပြုသူအမည်)နှင့် :guilabel:`Password` (စကားဝှက်) ကိုထည့်သွင်းပါ။
#. ထည့်သွင်းမှုများစာရင်းသို့ ဝန်ဆောင်မှုကို ပေါင်းထည့်ရန် :guilabel:`OK` ကိုနှိပ်ပါ။

ရှိနေပြီးသား Catalog Service entry (ထည့်သွင်းမှု) တစ်ခုကို ပြင်ဆင်တည်းဖြတ်ရန်-

#. ပြင်ဆင်တည်းဖြတ်လိုသော entry (ထည့်သွင်းမှု) ကိုရွေးချယ်ပါ။
#. :guilabel:`Edit` ခလုတ်ကိုနှိပ်ပါ။
#. :guilabel:`Name` သို့မဟုတ် :guilabel:`URL` တန်ဖိုးများကို မွမ်းမံပြင်ဆင်ပါ။
#. :guilabel:`OK` ကိုနှိပ်ပါ။

Catalog Service entry (ထည့်သွင်းမှု) တစ်ခုကို ပယ်ဖျက်ရန် ပယ်ဖျက်လိုသော entry (ထည့်သွင်းမှု) ကို ရွေးချယ်၍ :guilabel:`Delete` ခလုတ်ကိုနှိပ်ပါ။ Entry (ထည့်သွင်းမှု) ပယ်ဖျက်မှုကို အတည်ပြုရန် မေးမြန်းပါလိမ့်မည်။

Metasearch တွင် ချိတ်ဆက်မှုများကို XML ဖိုင်တစ်ခုသို့ ထည့်သွင်းခြင်းနှင့် သိမ်းဆည်းခြင်းများ လုပ်ဆောင်နိုင်ပါသည်။ ဤလုပ်ဆောင်မှုသည် application များအကြားတွင် setting များ မျှဝေရန် လိုအပ်သောအခါ အသုံးဝင်ပါသည်။ အောက်တွင် XML ဖိုင် format ၏ ဥပမာကို ပြသထားပါသည်။


.. code-block:: xml


  <?xml version="1.0" encoding="UTF-8"?>
  <qgsCSWConnections version="1.0">
      <csw type="OGC CSW 2.0.2" name="Data.gov CSW" url="https://catalog.data.gov/csw-all"/>
      <csw type="OGC CSW 2.0.2" name="Geonorge - National CSW service for Norway" url="https://www.geonorge.no/geonetwork/srv/eng/csw"/>
      <csw type="OGC CSW 2.0.2" name="Geoportale Nazionale - Servizio di ricerca Italiano" url="http://www.pcn.minambiente.it/geoportal/csw"/>
      <csw type="OGC CSW 2.0.2" name="LINZ Data Service" url="http://data.linz.govt.nz/feeds/csw"/>
      <csw type="OGC CSW 2.0.2" name="Nationaal Georegister (Nederland)" url="http://www.nationaalgeoregister.nl/geonetwork/srv/eng/csw"/>
      <csw type="OGC CSW 2.0.2" name="RNDT - Repertorio Nazionale dei Dati Territoriali - Servizio di ricerca" url="http://www.rndt.gov.it/RNDT/CSW"/>
      <csw type="OGC CSW 2.0.2" name="UK Location Catalogue Publishing Service" url="http://csw.data.gov.uk/geonetwork/srv/en/csw"/>
      <csw type="OGC CSW 2.0.2" name="UNEP/GRID-Geneva Metadata Catalog" url="http://metadata.grid.unep.ch:8080/geonetwork/srv/eng/csw"/>
  </qgsCSWConnections>


Entry (ထည့်သွင်းမှု) များပါဝင်သည့် စာရင်းတစ်ခုကို ထည့်သွင်းအသုံးပြုရန်-

#. :guilabel:`Load` ခလုတ်ကိုနှိပ်လိုက်လျှင် window အသစ်တစ်ခုကို တွေ့ရမည်ဖြစ်ပါသည်။
#. :guilabel:`Browse` ခလုတ်ကိုနှိပ်၍ အသုံးပြုလိုသော entry (ထည့်သွင်းမှု) များ၏ XML ဖိုင်ကို ညွှန်းပေးပါ။
#. :guilabel:`Open` ကိုနှိပ်လိုက်လျှင် entry (ထည့်သွင်းမှု) များ၏စာရင်းကို မြင်တွေ့ရမည်ဖြစ်ပါသည်။
#. စာရင်းမှ အသုံးပြုလိုသော entry (ထည့်သွင်းမှု) များကိုရွေးချယ်၍ :guilabel:`Load` ကိုနှိပ်ပါ။

ဝန်ဆောင်မှုအမျိုးအမည်သတ်မှတ်ခြင်း၊ ဝန်ဆောင်မှုပံ့ပိုးသူနှင့် ဆက်သွယ်ရန်အချက်အလက်ကဲ့သို့သော ရွေးချယ်ထားသည့် Catalog ဝန်ဆောင်မှုနှင့်ပတ်သက်သော အချက်အလက်များကို ကြည့်ရှုရန် :guilabel:`Service Info` ကိုနှိပ်ပါ။ အကယ်၍ raw API response (ဆာဗာမှ ရရှိလာသည့် API ဒေတာအကြမ်း) ကို ကြည့်လိုပါက :guilabel:`Raw API Response` ခလုတ်ကို နှိပ်ပါ။ ထိုအခါ ဆာဗာ၏အချက်အလက်များကို JSON အကြမ်း သို့မဟုတ် XML ဖိုင် format ဖြင့် ဖော်ပြနေသည့် သီးခြား window တစ်ခုပေါ်လာမည်ဖြစ်သည်။


Searching Catalog Services (Catalog ဝန်ဆောင်မှုများကို ရှာဖွေခြင်း)
....................................................................

.. _figure_metasearch_search:

.. figure:: img/metasearch-search.png
   :align: center

   Catalog ဝန်ဆောင်မှုများကို ရှာဖွေခြင်း

:guilabel:`Search` tab တွင် data နှင့် ဝန်‌ဆောင်မှုများအတွက် Catalog ဝန်ဆောင်မှုများကို စစ်ထုတ်ရှာဖွေရန်၊ အမျိုးမျိုးသော ရှာဖွေမှု parameter များကိုသတ်မှတ်ရန်နှင့် ရလာဒ်များကို ကြည့်ရှုရန် ခွင့်ပြုပေးထားပါသည်။

အောက်ပါ ရှာဖွေမှု parameter များကို ရရှိနိုင်ပါသည်-

* :guilabel:`Keywords` (အဓိကစကားလုံးများ) - လွတ်လပ်သော စာသားရှာဖွေမှု အဓိကစကားလုံးများ၊
* :guilabel:`From`- စစ်ထုတ်ရှာဖွေခြင်းကို ဆောင်ရွက်မည့် Catalog ဝန်ဆောင်မှု၊
* **Bounding box** - စစ်ထုတ် (filter) ရန် စိတ်ဝင်စားသည့် ပထဝီဝင်တည်နေရာ၊ :guilabel:`Xmax` (အများဆုံး X တန်ဖိုး)၊ :guilabel:`Xmin` (အနည်းဆုံး X တန်ဖိုး)၊ :guilabel:`Ymax` (အများဆုံး Y တန်ဖိုး)နှင့် :guilabel:`Ymin` (အနည်းဆုံး Y တန်ဖိုး) များသတ်မှတ်ခြင်းဖြင့် ဆောင်ရွက်ပါသည်။ Global ရှာဖွေမှုကို ပြုလုပ်ရန် :guilabel:`Set Global` ကိုနှိပ်ပါ။ မြင်နိုင်သော ဧရိယာအတွင်း ရှာဖွေမှုတစ်ခုကိုပြုလုပ်ရန် :guilabel:`Map Extent` (မြေပုံနယ်ပယ်အကျယ်အဝန်း) ကိုနှိပ်ပါ သို့မဟုတ် တန်ဖိုးများကို ရိုက်ထည့်ပါ။

:guilabel:`Search` ခလုတ်ကိုနှိပ်ခြင်းသည် ရွေးချယ်ထားသော Metadata Catalog ကို ရှာဖွေပါလိမ့်မည်။ ရှာဖွေထားသော ရလာဒ်များကို စာရင်းတစ်ခုတွင်ပြသပေးထားပြီး ၎င်းတို့ကို ဇယားတိုင် (column) ခေါင်းစဉ်ကိုနှိပ်၍ sort (စဉ်) လုပ်နိုင်ပါသည်။ ရှာဖွေမှု ရလာဒ်များအောက်ရှိ လမ်းညွှန်ခလုတ်များဖြင့် ၎င်းရှာဖွေမှု ရလာဒ်များကို ညွှန်ပြပေးနိုင်ပါသည်။

ရလာဒ်တစ်ခုကိုရွေးချယ်၍-

* :guilabel:`View Raw API Response` ခလုတ်ကိုနှိပ်ပါက ဝန်ဆောင်မှုတုန့်ပြန်ချက်များကို JSON အကြမ်း သို့မဟုတ် XML ဖိုင် format ဖြင့် ဖော်ပြသည့် window တစ်ခုပေါ်လာမည်ဖြစ်သည်။ 
* အကယ်၍ metadata မှတ်တမ်းတွင် ဆက်စပ်နေသည့် bounding box (နယ်ပယ်အတိုင်းအတာ) ရှိပါက ၎င်းဘောင်၏ footprint (အောက်ခြေအရာ) ကို မြေပုံပေါ်တွင် တွေ့မြင်ရမည်ဖြစ်ပါသည်။
* မှတ်တမ်းကို click နှစ်ချက်နှိပ်ခြင်းအားဖြင့် ဆက်စပ်နေသောဝင်ရောက်နိုင်သည့်လင့်များပါဝင်သော metadata မှတ်တမ်းကို ပြသပေးမည်ဖြစ်ပါသည်။
* အကယ်၍ မှတ်တမ်းသည် WMS/WMTS၊ WFS၊ WCS၊ ArcGIS REST စသည့်တို့ကဲ့သို့သော အသုံးပြုနိုင်သည့် ဝက်ဘ်ဝန်ဆောင်မှုတစ်ခုဖြစ်လျှင် :guilabel:`Add Data` ခလုတ်ကို အသုံးပြုနိုင်မည်ဖြစ်ပါသည်။ အဆိုပါခလုတ်ကို နှိပ်လိုက်လျှင် Metasearch သည် အဆိုပါထည့်သွင်းလိုက်သည့်အချက်အလက်သည် ဆီလျော်မှုရှိသော OWS တစ်ခုဖြစ်/မဖြစ်ကို အတည်ပြုသွားပါမည်။ ထို့နောက် ဝန်ဆောင်မှုကို သင့်လျော်ကိုက်ညီသော QGIS ဆက်သွယ်မှုစာရင်းထဲသို့ ထည့်သွင်းသွားမည်ဖြစ်ပြီး သင့်လျော်သော ဆက်သွယ်မှု dialog ကိုတွေ့မြင်နိုင်မည်ဖြစ်ပါသည်။

.. _figure_metasearch_metadata:

.. figure:: img/metasearch-record-metadata.png
  :align: center

  Metadata မှတ်တမ်း ပြသခြင်း

Settings (ချိန်ညှိခြင်းများ)
.............................

.. _figure_metasearch_setting:


.. figure:: img/metasearch-settings.png
   :align: center

   MetaSearch ချိန်ညှိခြင်းများ

Metasearch ကို အောက်ဖော်ပြပါ :guilabel:`Setting` များဖြင့် ပိုမိုကောင်း‌မွန်အောင် ဆောင်ရွက်နိုင်ပါသည်-

* :guilabel:`Server Timeout` (ဆာဗာချိတ်ဆက်ချိန်ကုန်ဆုံးခြင်း) - Metadata catalog များကို ရှာဖွေသောအခါ ဆက်သွယ်ချိတ်ဆက်ရန်ကြိုးစားမှုကို တားဆီးသည့် စက္ကန့်အရေအတွက်ဖြစ်ပြီး default တန်ဖိုးမှာ ၁၀ စက္ကန့်ဖြစ်ပါသည်။
* :guilabel:`Disable SSL verification` (SSL အတည်ပြုခြင်းကို ပိတ်ထားခြင်း) - SSL အတည်ပြုခြင်းကို ပိတ်ထားနိုင်သည့် ရွေးချယ်မှုတစ်ခုဖြစ်ပါသည်။
* :guilabel:`Results paging` (ရလဒ်များကို စာမျက်နှာဖြင့်ဖော်ပြခြင်း) - Metadata catalog များကို ရှာဖွေသောအခါ စာမျက်နှာတစ်ခုတွင် ဖော်ပြမည့် ရလာဒ်အရေအတွက် ဖြစ်ပါသည်။ Default တန်ဖိုးမှာ ၁၀ ဖြစ်သည်။


Catalog Server Errors (Catalog ဆာဗာချို့ယွင်းမှုများ)
------------------------------------------------------

Catalog သည် အချို့သောအခြေအနေများတွင် MetaSearch တွင်မလုပ်ဆောင်ဘဲ ဝက်ဘ်ဆိုက်ရှာဖွေမှု (web browser) တစ်ခုတွင် ဆောင်ရွက်ပါလိမ့်သည်။ ဤကဲ့သိုဖြစ်ရခြင်းမှာ Catalog ဆာဗာ၏ configuration/ setup ကြောင့် ဖြစ်နိုင်ပါသည်။ Catalog ဆာဗာ‌ပံ့ပိုးသူများသည် ၎င်းတို့၏ configuration တွင် URL များကို တသမတ်တည်းဖြစ်နေစေရန်နှင့် နောက်ဆုံးအခြေအနေ (update) ဖြစ်နေစေရန် လုပ်ဆောင်သင့်ပါသည်(၎င်းသည်  HTTP -> HTTPS ပြန်လည်လမ်းညွှန်သည့်အခြေအနေများတွင် အဖြစ်များသည်)။ ထိုပြဿနာ၏ အသေးစိတ်ရှင်းလင်းချက်များနှင့် ဖြေရှင်းနည်းကို `pycsw FAQ item`_ တွင် ဆက်လက်ကြည့်ရှုပါ။ FAQ item သည် pycsw သီးသန့်ဖြစ်သော်လည်း ၎င်းသည် အခြား Catalog ဆာဗာများတွင် ယေဘုယျအနေဖြင့်လည်း အသုံးပြုနိုင်ပါသည်။


.. _`OGC API - Records`: https://ogcapi.ogc.org/records
.. _`CSW (Catalog Service for the Web)`: https://www.ogc.org/standards/cat
.. _`OGC (Open Geospatial Consortium)`: https://www.ogc.org
.. _`pycsw FAQ item`: https://pycsw.org/faq/#my-pycsw-install-doesnt-work-at-all-with-qgis



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.


.. |metasearch| image:: /static/common/MetaSearch.png
   :width: 1.5em