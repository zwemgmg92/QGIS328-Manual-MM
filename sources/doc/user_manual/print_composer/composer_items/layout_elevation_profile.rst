.. index:: Layout; Elevation profile item
.. _layout_elevation_profile_item:

The Elevation Profile Item (အမြင့် အချက်အလက်ပြ Item)
=====================================================

.. only:: html

   .. contents::
      :local:


Elevation Profile item ကို layout တစ်ခုထဲတွင် :ref:`elevation profile view <label_elevation_profile_view>` (အမြင့် အချက်အလက်ပြ မြင်ကွင်း) တစ်ခုအားပြသရန် အသုံးပြုသည်။ :ref:`Item များဖန်တီးခြင်းဆိုင်ရာညွှန်ကြားချက်များ <create_layout_item>` ကိုလိုက်နာပြီး |elevationProfile| :guilabel:`Add Elevation Profile` ခလုတ်ကိုအသုံးပြု၍ နောင်တွင် :ref:`interact_layout_item` တွင်ပြသထားသည့်အတိုင်းနည်းလမ်းအတိုင်း ကိုင်တွယ်နိုင်မည့် elevation profile item အသစ်တစ်ခုကို ထည့်သွင်းပါ။

Elevation profile item အသစ်တစ်ခုတွင် ကားချပ်အလွတ်တစ်ခုကို ပုံဖော်ပြသပေးသည့် default setting များပါရှိသည်။ ၎င်း၏ဂုဏ်သတ္တိများကို :guilabel:`Item Properties` panel ထဲတွင် စိတ်ကြိုက်ပြင်ဆင်နိုင်သည်။ ဤ feature တွင် :ref:`ဘုံ ဂုဏ်သတ္တိများ <item_common_properties>` အပြင်  အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည်-

.. todo: add properties screenshot
   .. _figure_layout_elevationprofile_prop:

   .. figure:: img/elevationprofile_properties.png
   :align: center
   :width: 20em

   Elevation Profile Item Properties


Elevation profile :guilabel:`Item Properties` panel တွင် အောက်ပါလုပ်ဆောင်ချက်များပါဝင်သော top toolbar တစ်ခုကို ထည့်သွင်းထားသည်-

* Item ပုံဖော်ပြသခြင်းအား refresh လုပ်ရန်အတွက် |refresh| :sup:`Update elevation profile` 
* |copyProfileSettings| :sup:`Copy from elevation profile` - Elevation profile view တစ်ခုအားရွေးချယ်နိုင်မည့် drop-down menu တစ်ခု။ မြင်ကွင်း setting များကို Layout elevation profile item တွင် အသုံးပြုမည်ဖြစ်ပြီး နောက်တွင်ပြုပြင်မွမ်းမံနိုင်မည်ဖြစ်သည်။

Layers (Layer များ)
--------------------

:guilabel:`Layers` အုပ်စုအောက်တွင် profile item ထဲတွင် ပုံဖော်ပြသလိုသည့် tree view ထဲရှိ layer များကိုအမှန်ခြစ်ပါ။ ရွေးချယ်ထားသော layer များ၏ :guilabel:`Elevation` ဂုဏ်သတ္တိများကို သင့်လျော်စွာ ပြင်ဆင်သတ်မှတ်ထားရန် မမေ့ပါနှင့်။

Profile curve (အချက်အလက်ပြသသော မျဉ်းကွေး)
------------------------------------------

* |unchecked| :guilabel:`Controlled by atlas` - :ref:`Profile curve <elevation_profile_create>` အား လက်ရှိ atlas (စီးရီး) feature များနှင့် atlas feature များကိုပြောင်းလဲလိုက်တိုင်း update ဖြစ်သွားသော elevation profile view မှရယူမည်ဖြစ်သည်။ မျဉ်းဂျီမေတြီပုံစံ layer တစ်ခုအား အသုံးပြုလျှက် active ဖြစ်နေသော layout atlas တစ်ခု သို့မဟုတ် report တစ်ခုအတွက် လက်ရှိတွင်ထောက်ပံ့ပေးထားသည်။ 
* Data-defined (Data ဖြင့်သတ်မှတ်ထားသော) ဖြစ်နိုင်သော :guilabel:`Tolerance` (လက်ခံနိုင်မှု) အကွာအဝေးသည် layout elevation view ထဲတွင် ပြသရန်အတွက် မြင်နိုင်သော layer များ၏ feature တစ်ခုသည်  profile curve မှ မည်မျှဝေးဝေးတွင်ရှိနေသင့်သည်ကို ထိန်းချုပ်ပေးနိုင်သည်။ လက်ရှိတွင် point feature များကိုသာ ပြန်ထုတ်ပေးပါသည်။

Chart ranges (ကားချပ် အပိုင်းအခြားများ)
----------------------------------------

Layout elevation profile item တစ်ခုသည် ၎င်းအခြေပြုထားသည့် elevation profile ၏မြင်ကွင်းအပြည့်အား မဖြစ်မနေပြသမည်မဟုတ်ပါ။ အောက်ပါတို့ကို ထည့်သွင်း၍ ပုံဖော်ပြသမည့် ဧရိယာအား ကန့်သတ်ထားနိုင်သည်-

* X ဝင်ရိုးပေါ်တွင် profile curve စမှတ်မှ :guilabel:`Minimum distance` (အနည်းဆုံးအကွာအဝေး) နှင့် :guilabel:`Maximum distance` (အများဆုံးအကွာအဝေး) 
* Y ဝင်ရိုးပေါ်တွင်  :guilabel:`Minimum elevation` (အနည်းဆုံး အမြင့်) နှင့် :guilabel:`Maximum elevation` (အများဆုံး အမြင့်)

Distance and elevation axes (အကွာအဝေးနှင့် အမြင့် ဝင်ရိုးများ)
---------------------------------------------------------------

:guilabel:`Distance axis` နှင့် :guilabel:`Elevation axis` အုပ်စုများတွင် elevation profile item ပေါ်တွင် X ဝင်ရိုး နှင့် Y ဝင်ရိုးအသီးသီး၌ grid များအား အနည်းငယ်မျှပြောင်းလဲနိုင်ရန် ရွေးချယ်စရာများရှိသည်-

* :guilabel:`Major interval` (ကြားကွက်လပ် အကြီး) တစ်ခု နှင့် :guilabel:`Minor interval` (ကြားကွက်လပ် အငယ်) နှစ်ခုစလုံးတို့ဖြင့် ဝင်ရိုးပေါ်တွင် အတိုင်းအတာများကို အမှတ်အသားဖြင့်ပြခြင်း
* သက်ဆိုင်ရာ :guilabel:`Major grid lines` (Grid လိုင်းအကြီး) နှင့် :guilabel:`Minor grid lines` (Grid လိုင်းအငယ်) တို့တွင်အသုံးပြုမည့် မျဉ်းသင်္ကေတများ 
* ဝင်ရိုးပေါ်ရှိ အတိုင်းအတာပြ အမှတ်အသားများကို မည်သို့ အညွှန်းတပ်သင့်သည် (:guilabel:`Label interval`) အပြင် ၎င်းတို့၏ :guilabel:`Label format` (အညွှန်း format) နှင့် :guilabel:`Label font` (အညွှန်းစာလုံးဖောင့်)

Chart area (ကားချပ်ဧရိယာ)
--------------------------

:guilabel:`Chart area` အောက်တွင် elevation profile plot အား အမှန်တကယ်ပြသထားသည့် ဧရိယာကို ပုံဖော်ပြသခြင်းအား ပြင်ဆင်သတ်မှတ်နိုင်သည်-

* :guilabel:`Background` (နောက်ခံ) ဖြည့်ရန်သင်္ကေတတစ်ခု
* :guilabel:`Border` (နယ်နိမိတ်) မျဉ်းသင်္ကေတတစ်ခု
* Elevation profile item နယ်နိမိတ်မှ အနားသတ်များ


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |copyProfileSettings| image:: /static/common/mActionCopyProfileSettings.png
   :width: 1.5em
.. |elevationProfile| image:: /static/common/mActionElevationProfile.png
   :width: 1.5em
.. |refresh| image:: /static/common/mActionRefresh.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
