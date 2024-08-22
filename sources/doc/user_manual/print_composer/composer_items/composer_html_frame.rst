.. index:: HTML frame
.. _layout_html_item:

The HTML Frame Item (HTML ဘောင် Item)
======================================

.. only:: html

   .. contents::
      :local:

Website တစ်ခု၏ အကြောင်းအရာများကို ပြသသည့် frame တစ်ခု ကိုထည့်နိုင်သကဲ့သို့ ကိုယ်ပိုင်  HTML စာမျက်နှာကို ဖန်တီး၍ style ပြင်ဆင်ပြီး ၎င်းကို ပြသနိုင်သည်။ :ref:`Item များဖန်တီးခြင်း ညွှန်ကြားချက်များ <create_layout_item>` ကို လိုက်နာပြီး |addHtml| :guilabel:`Add HTML` ကိုသုံး၍ ရုပ်ပုံတစ်ခုကိုထည့်နိုင်ပြီး ၎င်းကို :ref:`interact_layout_item` (Layout item များနှင့်အပြန်အလှန်လုပ်ဆောင်ခြင်း) တွင်တွေ့ရသည့်အတိုင်း စီမံခန့်ခွဲနိုင်သည်။ မှတ်သားထားရမည်မှာ HTML frame ကို ဖန်တီးချိန်တွင်ရှိသော layout export resolution (ကြည်လင်ပြတ်သားမှု) ဖြင့် HTML scale ကိုထိန်းချုပ်ထားပါသည်။

HTML item အား ၎င်း၏ :guilabel:`Item Properties` ကို အသုံးပြု၍ စိတ်ကြိုက်ပြင်ဆင်နိုင်ပါသည်။ :ref:`Items common properties <item_common_properties>` များအပြင် ဤ feature တွင် အောက်ပါ လုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_html` ကိုကြည့်ပါ)-

.. _figure_layout_html:

.. figure:: img/html_properties.png
   :align: center

   HTML Frame၊ Item ဂုဏ်သတ္တိများ Panel


HTML Source (HTMLရင်းမြစ်)
---------------------------

HTML frame :guilabel:`Item Properties` panel ၏ :guilabel:`HTML Source` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိပါသည် (:numref:`figure_layout_html_ppt` ကိုကြည့်ပါ)-
 

.. _figure_layout_html_ppt:

.. figure:: img/html_source.png
   :align: center

   HTML frame ၊ HTML Source ဂုဏ်သတ္တိများ

* :guilabel:`URL` အကွက်တွင် အင်တာနက် browser မှ ကူးယူခဲ့သော web စာမျက်နှာတစ်ခု၏ URL ကို ထည့်သွင်းနိုင်သည် သို့မဟုတ် :guilabel:`...` :sup:`Browse` ခလုတ်ကို အသုံးပြု၍ HTML ဖိုင်တစ်ခုကို ရွေးချယ်နိုင်သည်။ Table တစ်ခု၏ attribute field ထဲရှိအကြောင်းအရာများမှ URL တစ်ခုအားထည့်သွင်း၍ဖြစ်စေ ပုံမှန် expression တစ်ခုကို အသုံးပြု၍ဖြစ်စေ |dataDefine| :sup: `Data-defined override` ခလုတ်ကိုလည်း အသုံးပြုနိုင်ပါသည်။
* :guilabel:`Source` ထဲရှိ textbox တွင် HTML tag အချို့ဖြင့် စာသားရိုက်ထည့်နိုင်သည် သို့မဟုတ် HTML စာမျက်နှာတစ်ခုလုံးကို ထည့်သွင်းဖော်ပြနိုင်သည်။
* လက်ရှိနှစ်ကိုပြသရန် အရင်းအမြစ် textbox တွင် ``[%Year($now)%]`` ကဲ့သို့သော expression တစ်ခုကို ပေါင်းထည့်ရန် :guilabel:`Insert or Edit an Expression...` ခလုတ်အား အသုံးပြုနိုင်ပါသည်။ ဤခလုတ်သည် radiobutton :guilabel:`Source` ကိုရွေးချယ်လိုက်သောအခါမှသာ အသက်ဝင်ပါသည်။ Expression အားထည့်သွင်းပြီးနောက် HTML frame အား refresh မလုပ်မီ textbox ထဲမှတစ်နေရာရာတွင် click နှိပ်ပါ မဟုတ်လျှင် expression ကို ဆုံးရှုံးပါလိမ့်မည်။
* ထည့်သွင်းခဲ့သော expression ၏ ရလာဒ်ကို ကြည့်ရန် |checkbox| :guilabel:`Evaluate QGIS expressions in HTML code` ကို Activate လုပ်ပါ။ မလုပ်လျှင် expression ကိုသာတွေ့ရပါမည်။ 
* HTML frame (များ) ကို refresh လုပ်ရန်နှင့် အပြောင်းအလဲများ၏ ရလာဒ်ကိုကြည့်ရှုရန် :guilabel:`Refresh HTML` ခလုတ်ကို အသုံးပြုပါ။


Frames (ဘောင်များ)
-------------------

HTML frame :guilabel:`Item Properties` panel ၏ :guilabel:`Frames` အုပ်စုတွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_html_frames` ကိုကြည့်ပါ)-

.. _figure_layout_html_frames:

.. figure:: img/html_frame.png
   :align: center

   HTML frame၊ Frame ၏ဂုဏ်သတ္တိများ

* :guilabel:`Resize mode` ကိုအသုံးပြု၍ HTML အကြောင်းအရာများကို မည်သို့ ပုံဖော်ပြသမည်ကိုရွေးချယ်နိုင်သည်-

  * ``Use existing frames`` သည် ပထမဆုံး frame နှင့် ပေါင်းထည့်ထားသော frame များတွင်သာ ရလာဒ်ကို ပြပေးသည်။
  * ``Extend to next page`` သည် web စာမျက်နှာတစ်ခုလုံးကို ပြသရန် လိုအပ်သလောက် frame များ (နှင့်သက်ဆိုင်ရာ စာမျက်နှာများ) ကိုဖန်တီးမည်ဖြစ်သည်။ Frame တစ်ခုချင်းစီကို layout ပေါ်တွင် ရွှေ့ပြောင်းနိုင်ပါသည်။ Frame တစ်ခုအား အရွယ်အစားပြောင်းလဲခြင်းဖြင့် web စာမျက်နှာကို အခြား frame များကြားတွင် ပိုင်းခြားသွားမည်ဖြစ်သည်။ Web စာမျက်နှာနှင့် အံဝင်ခွင်ကျဖြစ်စေရန် နောက်ဆုံး frame ကိုဖြတ်တောက်ရမည်ဖြစ်သည်။
  * ``Repeat on every page`` သည် စာမျက်နှာတိုင်းတွင် အရွယ်အစားတူ frame များဖြင့် web စာမျက်နှာ၏ ဘယ်ဘက်အပေါ်ပိုင်းကို repeat (ထပ်ခါတလဲလဲလုပ်ဆောင်) လုပ်ပေးမည်ဖြစ်သည်။
  * ``Repeat until finished`` သည် ``Extend to next page`` ရွေးချယ်မှုကဲ့သို့ပင် frame များကိုလိုအပ်သလောက်ဖန်တီးမည်ဖြစ်ပြီး ခြွင်းချက်အနေနှင့် အရွယ်အစားတူ frame များကိုသာဖန်တီးမည်ဖြစ်သည်။ 

* ရွေးချယ်ထားသော frame နှင့် အရွယ်အစားတူ အခြား frame ကို ထည့်ရန် :guilabel:`Add Frame` ခလုတ်ကို အသုံးပြုပါ။ HTML စာမျက်နှာသည် ပထမဆုံး frame တွင် မဆံ့ပါက :guilabel:`Resize mode` သို့မဟုတ် :guilabel:`Use existing frames` ကိုအသုံးပြုသောအခါ ၎င်းသည်နောက် frame တစ်ခုသို့ ဆက်လက်၍သွားမည်ဖြစ်သည်။
* |checkbox| :guilabel:`Don't export page if frame is empty` ကိုအမှန်ခြစ်ပေးထားခြင်းဖြင့် frame တွင် HTML အကြောင်းအရာများမပါရှိဘဲ စာမျက်နှာအား export လုပ်မိခြင်းမှကာကွယ်ပေးမည်ဖြစ်သည်။ မြေပုံများ၊ စကေးဘားများ၊ ရည်ညွှန်းချက်များ စသည်တို့ကဲ့သို့ အခြား layout item များအား ရလာဒ်ထဲတွင် မြင်ရလိမ့်မည်မဟုတ်ဟု ဆိုလိုခြင်းဖြစ်ပါသည်။
* |checkbox| :guilabel:`Don't draw background if frame is empty` ကိုအမှန်ခြစ်ပေးထားခြင်းဖြင့် frame အလွတ်ဖြစ်နေချိန်တွင် HTML frame ကို မဆွဲမိစေရန်ကာကွယ်ပေးမည်ဖြစ်သည်။
 

Use smart page breaks and User style sheet (သေသပ်သော စာမျက်နှာ အခွဲများနှင့် အသုံးပြုသူ style စာရွက်များ အသုံးပြုခြင်း)
------------------------------------------------------------------------------------------------------------------------

HTML frame :guilabel:`Item Properties` panel မှ :guilabel:`Use smart page breaks` dialog နှင့် :guilabel:`User style sheet` dialog တို့တွင် အောက်ပါလုပ်ဆောင်ချက်များပါရှိသည် (:numref:`figure_layout_html_breaks` ကိုကြည့်ပါ)-

.. _figure_layout_html_breaks:

.. figure:: img/html_breaks.png
   :align: center

   HTML frame၊ Smart page break များနှင့် User style sheet ဂုဏ်သတ္တိများ

* HTML frame အတွင်းရှိ အကြောင်းအရာများအား စာကြောင်းတစ်ကြောင်း၏အလယ်တွင် ပြတ်သွားခြင်းမရှိဘဲ နောက် frame တစ်ခုသို့ ကောင်းမွန်ချောမွေ့စွာ ဆက်သွားနိုင်စေရန်အတွက် |checkbox| :guilabel:`Use smart page breaks` ကို Activate လုပ်ပါ။  
* HTML ထဲတွင် page break နေရာများကိုတွက်ချက်သည့်အခါ ခွင့်ပြုမည့် :guilabel:`Maximum distance` အားသတ်မှတ်ပါ။ ဤအကွာအဝေးသည် အကောင်းဆုံး break တည်နေရာကိုဆုံးဖြတ်တွက်ချက်ပြီးနောက် frame တစ်ခု၏အောက်ခြေတွင် ခွင့်ပြုထားသော အများဆုံးနေရာလွတ်ပမာဏဖြစ်သည်။ ပိုကြီးသောတန်ဖိုးတစ်ခုကိုသတ်မှတ်ခြင်းဖြင့် page break နေရာများရွေးချယ်ရာတွင် ပိုမိုကောင်းမွန်သောရလာဒ်ရရှိနိုင်သော်လည်း frame များ၏ အောက်ခြေတွင်နေရာအလေအလွင့်ပိုများလာနိုင်သည်။ :guilabel:`Use smart page breaks` ကိုဖွင့်ထားချိန်တွင်သာ ၎င်းကိုအသုံးပြုပါသည်။
* Cascading (ပမာဏများများနှင့်လျင်လျင်မြန်မြန် အောက်သို့ကျနေသော) style sheet များတွင် တွေ့ရလေ့ရှိသော HTML style များကို အသုံးပြုရန် |checkbox| :guilabel:`User style sheet` ကိုအမှန်ခြစ်ပေးပါ။ ``<h1>`` ခေါင်းစီး tag ၏အရောင်ကိုအစိမ်းရောင်သို့ပြောင်းရန် နှင့် စာပိုဒ် tags ``<p>`` များတွင်ပါဝင်သော စာသားများ၏ စာလုံးပုံစံနှင့် စာလုံးအရွယ်အစားကို သတ်မှတ်ရန် အောက်တွင် style code ဥပမာတစ်ခုကိုပေးထားပါသည်။

  .. code-block:: css

     h1 {color: #00ff00;
     }
     p {font-family: "Times New Roman", Times, serif;
        font-size: 20px;
     }

* Style sheet setting များ၏ ရလာဒ်ကိုကြည့်ရှုရန် :guilabel:`Update HTML` ခလုတ်ကို အသုံးပြုပါ။ 

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |addHtml| image:: /static/common/mActionAddHtml.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
