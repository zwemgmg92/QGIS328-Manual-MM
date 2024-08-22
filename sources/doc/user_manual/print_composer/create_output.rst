.. index::
   single: Printing; Export map 

.. _create-output:

****************************************************
Creating an Output (ရလာဒ်တစ်ခု ဖန်တီးခြင်း)
****************************************************

.. only:: html

   .. contents::
      :local:

:numref:`figure_layout_output` သည် ယခင် အပိုင်းတွင် ဖော်ပြခဲ့ပြီးသော layout item အမျိုးအစားအားလုံးပါဝင်သည့်  
print layout နမူနာတစ်ခုအား ပြသထားပါသည်။ 


.. _figure_layout_output:

.. figure:: img/print_composer_complete.png
   :align: center
   :width: 100%

   ပေါင်းထည့်ထားသော HTML frame နှင့် စာသားများ၊ ကိုသြဒိနိတ်အမှတ်များ၊ စကေးဘား နှင့် ဓါတ်ပုံများ၊ မြေပုံရည်ညွှန်းချက်၊ မြေပုံမြင်ကွင်း များပါဝင်သော ပုံထုတ်အပြင်အဆင် 
   

.. index:: Export as image, Export as PDF, Export as SVG

:menuselection:`Layout` menu သို့မဟုတ် toolbar မှ print layout များကို ဖိုင်ပုံစံအမျိုးမျိုးဖြင့် ထုတ်ယူနိုင်ပါသည်။ ထုတ်ယူမည့် စာရွက်အရွယ်အစားနှင့် ကြည်လင်ပြတ်သားမှု (ပုံထုတ် အရည်အသွေး) အား ပြုပြင်မွမ်းမံနိုင်ပါသည်။ 


* |filePrint| :sup:`Print` သင်္ကေတသည် ထည့်သွင်းထားသော printer driver များပေါ်မူတည်၍ layout အား ချိတ်ဆက်ထားသော printer တစ်ခု သို့မဟုတ် PostScript ဖိုင်တစ်ခုသို့ print လုပ်နိုင်မည်ဖြစ်သည်။

* |saveMapAsImage| :sup:`Export as image` သင်္ကေတသည် print layout အား :file:`PNG` ဖိုင်၊ :file:`BMP` ဖိုင်၊ :file:`TIF` ဖိုင်၊ :file:`JPG` ဖိုင်၊ နှင့် အခြားများစွာသော ဖိုင်များ ကဲ့သို့ ဓာတ်ပုံ format အဖြစ်သို့ ထုတ်ယူပေးပါသည်။ 
* |saveAsSVG| :sup:`Export as SVG` သင်္ကေတသည် :file:`SVG` (Scalable Vector Graphic) တစ်ခုအဖြစ်
  print layout အား သိမ်းဆည်းပေးပါသည်။ 
* |saveAsPDF| :sup:`Export as PDF` သင်္ကေတသည် သတ်မှတ်ထားသော print layout အား :file:`PDF` (Portable Document Format) ဖိုင်အဖြစ် တိုက်ရိုက် သိမ်းဆည်းပေးပါသည်။


Export settings (ထုတ်ယူခြင်း setting များ)
===========================================

Print layout တစ်ခုအား ထုတ်ယူသည့်အခါတိုင်း၊ အသင့်တော်ဆုံး ရလာဒ်တစ်ခုအား ရရှိရန်အတွက် QGIS မှ စစ်ဆေးရန်လိုအပ်သော ထုတ်ယူခြင်း setting များရှိပါသည်။ ထို configuration (ပြင်ဆင်သတ်မှတ်ချက်) များမှာ-

* :guilabel:`Layout` panel ၏ :ref:`Export settings <layout_export_settings>` များ ဥပမာအားဖြင့် - :guilabel:`Export resolution` (Export ၏ကြည်လင်ပြတ်သားမှု) ၊ :guilabel:`Print as raster` (Raster အဖြစ် print လုပ်ခြင်း) ၊ :guilabel:`Always export as vectors` (Vector များအဖြစ် အမြဲ export လုပ်ခြင်း) သို့မဟုတ်  :guilabel:`Save world file` (World file အဖြစ်သိမ်းဆည်းခြင်း)
* :ref:`စာမျက်နှာဆိုင်ရာဂုဏ်သတ္တိများ <page_properties>` panel ရှိ :guilabel:`Exclude page from exports` (စာမျက်နှာကို Export ထုတ်ခြင်းများမှ ချန်လှပ်ထားခြင်း)
* :ref:`Item ဂုဏ်သတ္တိများ <layout_Rendering_Mode>` panel ရှိ :guilabel:`Exclude item from exports` (Item ကို Export ထုတ်ခြင်းများမှ ချန်လှပ်ထားခြင်း)

ထို့အပြင်၊ ကြိုတင်သတ်မှတ်ထားသော စစ်ဆေးမှုများအား layout ၌ အလိုအလျောက် အသုံးပြုသွားမည်ဖြစ်ပါသည်။ လက်ရှိတွင် အဆိုပါ စစ်ဆေးမှုများတွင် စမ်းသပ်မှုများပါဝင်ပါသည်။ ယင်းတွင် စကေးဘား သည် မြေပုံ item များနှင့် မှန်မှန်ကန်ကန်ချိတ်ဆက်နေခြင်း ရှိ/မရှိ နှင့် မြေပုံ overview item များသည်လည်း မြေပုံနှင့် မှန်မှန်ကန်ကန်ချိတ်ဆက်နေခြင်း ရှိ/မရှိ တို့ ပါဝင်သည်။ စစ်ဆေးမှုများသည် မအောင်မြင်လျှင်၊ ပြဿနာနှင့်ပတ်သက်သော သတိပေးအကြံပြုချက်တစ်ခုအား ပြသပေးပါလိမ့်မည်။ 

.. _export_layout_image:

Export as Image (ဓာတ်ပုံအဖြစ် ထုတ်ယူခြင်း)
===========================================

ဓာတ်ပုံတစ်ခုအဖြစ် layout တစ်ခုအား export ထုတ်ယူရန်-


#. |saveMapAsImage| :sup:`Export as image` icon အား နှိပ်ပါ။
#. အသုံးပြုရန် ဓာတ်ပုံ format ၊ folder နှင့်  ဖိုင်အမည်အား ရွေးချယ်ပါ၊ (ဉပမာအားဖြင့် :file:`myill.png`) Layout တွင် စာမျက်နှာ တစ်ခုထက်မက ပါဝင်ပါက၊ စာမျက်နှာတစ်ခုစီအား စာမျက်နှာနံပါတ်နှင့်အတူ ပေးထားသော ဖိုင်အမည်ဖြင့် ဖိုင် တစ်ခုစီသို့ export လုပ်ပေးပါလိမ့်မည် (ဉပမာအားဖြင့် :file:`myill_2.png`)။
#. နောက်တစ်ဆင့်အနေဖြင့် (:guilabel:`Image Export Options`) dialog တွင်-
     
   * Print layout ၏ :guilabel:`Export resolution` နှင့် export ထုတ်ယူသော စာမျက်နှာ၏ အတိုင်းအတာများ (:guilabel:`Layout` panel ထဲတွင် သတ်မှတ်ထားသည့်အတိုင်း) အား အစားထိုးလုပ်ဆောင်နိုင်ပါသည်။ 
   * :guilabel:`Enable antialiasing` ရွေးချယ်မှုဖြင့် ဓာတ်ပုံ ပုံဖော်ပြသခြင်း အရည်အသွေးကိုလည်း ပိုမိုကောင်းမွန်စေနိုင်ပါသည်။ 
   * မိမိ ပြုလုပ်ထားသော layout အား **georeference ပြုလုပ်ထားသော ဓာတ်ပုံ** တစ်ခုအဖြစ် (ဥပမာအားဖြင့်၊ အခြား project များအား မျှဝေရန်) export ထုတ်ယူလိုလျှင်၊ |unchecked| :guilabel:`Generate world file` option အား အမှန်ခြစ်ပါ။ Export ထုတ်ယူထားသောဓာတ်ပုံနှင့် နာမည်တူပြီး extension မတူသော *ESRI World File* တစ်ခု (TIFF ဖိုင်အတွက် :file:`.tfw`၊ PNG ဖိုင်အတွက် :file:`.pnw`၊ JPEG ဖိုင်အတွက် :file:`jgw` ၊ ...) အား  ဖန်တီးပေးပါလိမ့်မည်။ ယခု option ကို :ref:`layout panel <layout_panel>` ထဲတွင် default အနေဖြင့်လည်း အမှန်ခြစ်ထားနိုင်ပါသည်။ 

     .. note::
		  စာမျက်နှာများစွာထုတ်ယူမည်ဆိုလျှင်၊ :ref:`အကိုးအကားမြေပုံ <reference_map>` ပါဝင်သော စာမျက်နှာတွင်သာ world file တစ်ခုရှိပါလိမ့်မည် (:guilabel:`Generate world file` option အား အမှန်ခြစ်ထားသည်ဟု ယူဆလျက်)။


   .. index:: Crop layout to content
   .. _crop_to_content:

   * |checkbox| :guilabel:`Crop to content` အား အမှန်ခြစ်ထားခြင်းအားဖြင့် layout ဓာတ်ပုံ output တွင် စာမျက်နှာတစ်ခုချင်းစီ၏ ပါဝင်သော အရာများ (မြေပုံ၊ မြေပုံရည်ညွှန်းချက်၊ စကေးဘား ၊ ပုံသဏ္ဍာန် ၊ အညွှန်း၊ ဓာတ်ပုံ...) အားလုံးအား ပူးတွဲထားသော အနည်းဆုံးဧရိယာ ပါဝင်သည်-

     * ဖွဲ့စည်းမှု (composition) တွင် စာမျက်နှာတစ်ခုသာပါလျှင်၊ ဖွဲ့စည်းမှု (composition) ရှိ အားလုံးပါဝင်ရန် output အား အရွယ်အစားချိန်ညှိပေးမည်ဖြစ်သည်။ ထို့နောက် ၎င်းတို့၏ နေရာတည်ရှိမှု (စာမျက်နှာ၏ အပေါ်၊ အထက်၊ အောက်၊ ဘယ်ဘက် သို့မဟုတ် ညာဘက်) အပေါ်မူတည်၍ item များအားလုံးပါဝင်စေရန် စာမျက်နှာအား လျှော့ချခြင်း သို့မဟုတ် တိုးချဲ့ခြင်း တို့ကို ပြုလုပ်နိုင်သည်။ 
	  * စာမျက်နှာများစွာပါသော layout တစ်ခုအား ထုတ်ယူမည်ဆိုလျှင်၊ ၎င်းဧရိယာထဲတွင် item များပါဝင်စေရန် စာမျက်နှာ တစ်ခုချင်းစီအား အရွယ်အစားချိန်ညှိပေးပါလိမ့်မည် (စာမျက်နှာအားလုံးအတွက် ဘယ် နှင့် ညာဘက် အခြမ်းများ၊ ထို့အပြင် ပထမစာမျက်နှာအတွက် ထိပ်ပိုင်းနှင့် နောက်ဆုံးစာမျက်နှာအတွက် အောက်ပိုင်း)။ အရွယ်အစားချိန်ညှိထားပြီးသား စာမျက်နှာတစ်ခုချင်းစီအား သီးခြားဖိုင်တစ်ခုစီအဖြစ် export ထုတ်ယူမည်ဖြစ်သည်။

	  :guilabel:`Crop to content` dialog သည် ဖြတ်ထုတ်လိုက်သော အကျယ်အဝန်းတစ်လျှောက်တွင် အနားသတ် (margin) များကိုလည်း ပေါင်းထည့်ပေးစေပါသည်။

.. _figure_layout_output_image:

.. figure:: img/image_export_options.png
   :align: center

   ဓာတ်ပုံထုတ်ယူမှု ရွေးချယ်စရာများ၊ item များ၏ extent အတိုင်း output အား အရွယ်အစားချိန်ညှိမည်ဖြစ်သည်။ 

.. tip::
   **Item များ၏ extent သည် စာရွက်၏ extent ထက်ကျော်လွန်နေသောအခါ transparency (အလင်းဖောက်နှုန်း) ကို ရရှိနိုင်သော ဓာတ်ပုံ format များကို အသုံးပြုပါ**

   Layout item များသည် စာရွက် extent အပြင်ဘက်တွင် ရောက်ရှိနေနိုင်ပါသည်။ :guilabel:`Crop to content` option ဖြင့် export ထုတ်ယူသောအခါ ရလာဒ် ဓာတ်ပုံသည် စာရွက် extent ထက် ကျော်လွန်နိုင်ပါသည်။ စာရွက် extent ၏ အပြင်ဘက် နောက်ခံများသည် transparent (အလင်းဖောက်နိုင်သော) ဖြစ်နေမည်ဖြစ်သောကြောင့် transparency (အလင်းဖောက်နှုန်း) မရရှိသော ဓာတ်ပုံ format များအတွက် (ဉပမာ၊ ``BMP`` နှင့် ``JPG`` များ)၊ transparent (အလင်းဖောက်နိုင်သော) ဖြစ်နေသော နောက်ခံအား အနက်ရောင်အပြည့်ဖြင့် ပုံဖော်ပြသပေးမည်ဖြစ်သည်။ ထိုသို့သောကိစ္စရပ်များတွင် transparency-compatible (အလင်းဖောက်မှု နှင့်တွဲဖက်သုံးနိုင်သော) format (ဉပမာ- ``TIFF``နှင့် ``PNG``) များအား အသုံးပြုပါ။ 
   

.. note:: ရှိပြီးသား Qt library နှင့် format (ဉပမာ- :file:`PNG`) က လက်ခံသည့်အခါ၊ export ထုတ်ယူလိုက်သည့် ဓာတ်ပုံများတွင် :ref:`project metadata <project_metadata>` (ရေးဆွဲသူ၊ ခေါင်းစဉ်၊ ရက်စွဲ၊ ဖော်ပြချက်...) တို့ ပါဝင်နိုင်သည်။ 

.. _export_layout_svg:

Export as SVG (SVG အဖြစ် export ထုတ်ခြင်း) 
============================================

SVG အဖြစ် layout တစ်ခုအား export ထုတ်ရန်-

#. |saveAsSVG| :sup:`Export as SVG` သင်္ကေတအား နှိပ်ပါ။
#. သိမ်းဆည်းမည့်လမ်းကြောင်း နှင့် ဖိုင်အမည် ဖြည့်ပါ (စာမျက်နှာတစ်ခုထက်မက ပါဝင်သော ဖိုင်များအတွက်ဆိုလျှင် ဖိုင်များအားလုံးအတွက် ဓာတ်ပုံ export ထုတ်ရာတွင် အခြေခံအမည်တစ်ခုအား အသုံးပြုမည်ဖြစ်သည်)
#. ထို့နောက် :guilabel:`SVG Export Options` dialog ထဲတွင် layout default :ref:`export setting များ <layout_export_settings>` အား အစားထိုးလုပ်ဆောင်နိုင်သည် သို့မဟုတ် အသစ်များအား ပြင်ဆင်သတ်မှတ်နိုင်ပါသည်။ 

   * |unchecked| :guilabel:`Export map layers as SVG groups` - QGIS မှ layer အမည်များနှင့် ကိုက်ညီသော export ထုတ်ထားသည့် item များအား layer များအတွင်း အုပ်စုဖွဲ့ပေးမည်ဖြစ်သည်။ ၎င်းသည် အကြောင်းအရာများအား လွယ်ကူစွာ နားလည်နိုင်စေပါသည်။ 
   * |unchecked| :guilabel:`Always export as vectors` - အချို့သော ပုံဖော်ပြသမှု option များသည် ပိုမိုကောင်းမွန်သောပုံဖော်ပြသမှုရရှိစေရန်အတွက် item များအား raster အဖြစ်သို့ပြောင်းလဲရန် လိုအပ်ပါသည်။ Output ဖိုင်သည် print layout အကြိုကြည့်ရှုမှု (preview) နှင့် ပုံပန်းသဏ္ဍာန်ကိုက်ညီမှုမရှိ ဖြစ်နိုင်သော vector များအဖြစ် object များကိုဆက်လက်ထားရှိရန် ယခု option အား အမှန်ခြစ်ပါ (ပိုမိုသောအသေးစိတ်များ အတွက် :ref:`layout_export_settings` အား ကြည့်ပါ)။
   * ခေါင်းစဉ်၊ ရေးဆွဲသူ၊ ရက်စွဲ၊ ဖော်ပြချက်...ကဲ့သို့သော RDF metadata များအား export ထုတ်ယူရန် |checkbox| :guilabel:`Export RDF metadata` ကိုအမှန်ခြစ်ပါ။
   * Vertex များအားလုံးအား export ထုတ်ယူလျှင် အခြား application များ၌ ထည့်သွင်းအသုံးပြုရာတွင် အဆင်မပြေမှုများရှိနိုင်သော အလွန်ရှုပ်ထွေးပြီး ဖိုင်အရွယ်အစားကြီးမားသော ရလာဒ်များ ရရှိစေပါသည်၊ ထို့ကြောင့် |checkbox| :guilabel:`Simplify geometries to reduce output file size` ကို အမှန်ခြစ်ခြင်းဖြင့် ဂျီဩမေတြီ၏ vertex (မျဉ်းအဆစ်) များအားလုံးကို export ထုတ်ယူခြင်းမှ ရှောင်ရှားပေးပါသည်။ Export resolution (ကြည်လင်ပြတ်သားမှု) ၌ သိသိသာသာ ကွဲပြားမှုမရှိသော ပိုလျှံနေသည့် မည်သည့် vertex များကိုမဆို ဖယ်ရှားရန်အတွက် layout အား export ထုတ်ယူနေစဉ်တွင် ဂျီဩမေတြီများအား ရိုးရှင်းအောင်လုပ်ပေးမည်ဖြစ်သည် (ဥပမာအားဖြင့်- export resolution သည် ``300 dpi`` ဖြစ်လျှင်၊ ``1/600 inch`` ထက် သေးငယ်သော vertex များအား ဖယ်ရှားပေးပါလိမ့်မည်)။
   * :guilabel:`Text export` အား သတ်မှတ်ပါ- အညွှန်းစာသားများအား သင့်တော်သောစာသားများ (:guilabel:`Always export texts as text objects`) အဖြစ် သို့မဟုတ် လမ်းကြောင်းများအဖြစ်သာ (:guilabel:`Always export texts as paths`) export ထုတ်/မထုတ်ကို ထိန်းချုပ်ပေးပါသည်။ ၎င်းတို့အား စာသား အဖြစ် export ထုတ်လျှင် ပြင်ပ application များတွင် ပုံမှန် စာသား အဖြစ် (ဥပမာအားဖြင့်- Inkscape) တည်းဖြတ်ပြင်ဆင်နိုင်မည်ဖြစ်သည်။ သို့သော် ပုံဖော်ပြသမှု အရည်အသွေး လျော့ချစေပြီး၊ buffer များကဲ့သို့ အချို့သော စာသား setting များ ပြုလုပ်သည့်အခါ ပုံဖော်ပြသရာတွင် ပြဿနာများရှိမည်ဖြစ်သည်။ ထို့ကြောင့် လမ်းကြောင်းများ အနေဖြင့် export ထုတ်ခြင်းအား အကြံပြုပါသည်။
   * |checkbox| :guilabel:`Crop to content` :ref:`option <crop_to_content>` အား အမှန်ခြစ်ပါ။
	* |unchecked| :guilabel:`Disable tiled raster layer exports` - ဖိုင်များအား export ထုတ်ယူသည့်အခါ၊ ကွန်ပျူတာမှတ်ဉာဏ်ကို သက်သာစေသော built-in ပါရှိပြီးသားဖြစ်သည့် raster layer ကို tile (အကွက်) များဖြင့် ပုံဖော်ပြသခြင်းအား QGIS မှ အသုံးပြုပါသည်။ တခါတရံတွင် ၎င်းသည် ထုတ်ယူလိုက်သော ဖိုင်များအတွက် raster များထဲတွင် "ဆက်ကြောင်း" (seams) များကို ဖြစ်စေသည်။ ယခု option အား အမှန်ခြစ်ခြင်းသည် အဆိုပါ ပြဿနာအား ဖြေရှင်းနိုင်လိမ့်မည်ဖြစ်သော်လည်း Export ထုတ်ယူနေစဉ် ကွန်ပျူတာမှတ်ဉာဏ် သုံးစွဲမှုများပြားမည်ဖြစ်သည်။
	 

.. _figure_layout_output_svg:

.. figure:: img/svg_export_options.png
   :align: center

   SVG Export ထုတ်ခြင်း ရွေးချယ်စရာများ 

.. note::

   ယခုလက်ရှိတွင် SVG  ရလဒ်သည် အလွန် အခြေခံကျပါသည်။ ၎င်းသည် QGIS ပြဿနာတစ်ခုမဟုတ်ပေ၊ သို့သော် ရှိနေပြီးသား Qt library ၌ ပြဿနာတစ်ခုသာလျှင်ဖြစ်သည်။ အဆိုပါအရာအား အနာဂါတ် version များတွင် ဖြေရှင်းနိုင်မည်ဟု မျှော်လင့်ပါသည်။ 


.. _export_layout_pdf:

Export as PDF (PDF အဖြစ် ထုတ်ယူခြင်း)
======================================

PDF အဖြစ် layout တစ်ခုအား export ထုတ်ယူရန်-

#. |saveAsPDF| :sup:`Export as PDF` သင်္ကေတအား နှိပ်ပါ။ 
#. ဖိုင်လမ်းကြောင်းနှင့် ဖိုင်အမည်ကို ဖြည့်ပါ။ ပုံများ နှင့်  SVG export ထုတ်ယူမှုများနှင့်မတူပဲ layout ရှိ စာမျက်နှာများအားလုံးကို PDF ဖိုင်တစ်ခုထဲသို့ export ထုတ်ယူပေးပါသည်။ 
#. နောက်ထပ် :guilabel:`PDF Export Options` dialog တွင် layout ၏ default :ref:`export settings <layout_export_settings>` အား အစားထိုးလုပ်ဆောင်နိုင်သည် သို့မဟုတ် အသစ်များကို ပြင်ဆင်သတ်မှတ်ပေးနိုင်သည်-

   * |unchecked| :guilabel:`Always export as vectors` - အချို့သော ပုံဖော်ပြသမှု option များသည် ပိုမိုကောင်းမွန်သောပုံဖော်ပြသမှုရရှိစေရန်အတွက် item များအား raster အဖြစ်သို့ပြောင်းလဲရန် လိုအပ်ပါသည်။ Output ဖိုင်သည် print layout အကြိုကြည့်ရှုမှု (preview) နှင့် ပုံပန်းသဏ္ဍာန်ကိုက်ညီမှုမရှိ ဖြစ်နိုင်သော vector များအဖြစ် object များကိုဆက်လက်ထားရှိရန် ယခု option အား အမှန်ခြစ်ပါ (ပိုမိုသောအသေးစိတ်များ အတွက် :ref:`layout_export_settings` အား ကြည့်ပါ)။
   * |checkbox| :guilabel:`Append georeference information` - အချက်အလက်များရယူသော :ref:`reference map <reference_map>` သည် ပထမဆုံးစာမျက်နှာတွင် ရှိမှာသာ အသုံးပြုနိုင်မည်ဖြစ်သည်။
   * ခေါင်းစဉ်၊ ရေးဆွဲသူ၊ ရက်စွဲ၊ ဖော်ပြချက်...အစရှိသည့် RDF metadata များကို export ထုတ်ယူရန် |checkbox| :guilabel:`Export RDF metadata` ကိုအမှန်ခြစ်ပါ။
   * :guilabel:`Text export` အား သတ်မှတ်ပါ- အညွှန်းစာသားများအား သင့်တော်သောစာသားများ (:guilabel:`Always export texts as text objects`) အဖြစ် သို့မဟုတ် လမ်းကြောင်းများအဖြစ်သာ (:guilabel:`Always export texts as paths`) export ထုတ်/မထုတ်ကို ထိန်းချုပ်ပေးပါသည်။ ၎င်းတို့အား စာသား အဖြစ် export ထုတ်လျှင် ပြင်ပ application များတွင် ပုံမှန် စာသား အဖြစ် (ဥပမာအားဖြင့်- Inkscape) တည်းဖြတ်ပြင်ဆင်နိုင်မည်ဖြစ်သည်။ သို့သော် ပုံဖော်ပြသမှု အရည်အသွေး လျော့ချစေပြီး၊ buffer များကဲ့သို့ အချို့သော စာသား setting များ ပြုလုပ်သည့်အခါ ပုံဖော်ပြသရာတွင် ပြဿနာများရှိမည်ဖြစ်သည်။ ထို့ကြောင့် လမ်းကြောင်းများ အနေဖြင့် export ထုတ်ခြင်းအား အကြံပြုပါသည်။
	 
   * အောက်ဖော်ပြပါ အရာများအား အသုံးပြုပြီး PDF :guilabel:`Image compression` ကို ထိန်းညှိပါ- 
     
     * :guilabel:`Lossy (JPEG)` သည် default ဖြစ်သော ဖိုင်ချုံ့ခြင်း နည်းလမ်းဖြစ်သည်။ 
     * သို့မဟုတ် :guilabel:`Lossless` သည် အများစုကိစ္စရပ်များတွင် ကြီးမားသော ဖိုင်များကို ဖန်တီးပေးသော်လည်း ၎င်းသည် output များကို ပုံနှိပ်ခြင်းပြုလုပ်ရန်အတွက် သို့မဟုတ် ပြင်ပ application များတွင် post-production (နောက်ပိုင်းလုပ်ငန်းစဉ်) အတွက် အလွန်သင့်လျော်ပါသည် (Qt 5.13 နှင့် နောက်ပိုင်း ဖြစ်ရန် လိုအပ်သည်)။ 
   * Georeferenced ပြုလုပ်ထားသော PDF ဖိုင်တစ်ခုအား ထုတ်ယူလိုလျှင် |unchecked| :guilabel:`Create Geospatial PDF (GeoPDF)` အား အမှန်ခြစ်ပါ။ 
   * |unchecked| :guilabel:`Disable tiled raster layer exports` - ဖိုင်များအား export ထုတ်ယူသည့်အခါ၊ ကွန်ပျူတာမှတ်ဉာဏ်ကို သက်သာစေသော built-in ပါရှိပြီးသားဖြစ်သည့် raster layer ကို tile (အကွက်) များဖြင့် ပုံဖော်ပြသခြင်းအား QGIS မှ အသုံးပြုပါသည်။ တခါတရံတွင် ၎င်းသည် ထုတ်ယူလိုက်သော ဖိုင်များအတွက် raster များထဲတွင် "ဆက်ကြောင်း" (seams) များကို ဖြစ်စေသည်။ ယခု option အား အမှန်ခြစ်ခြင်းသည် အဆိုပါ ပြဿနာအား ဖြေရှင်းနိုင်လိမ့်မည်ဖြစ်သော်လည်း Export ထုတ်ယူနေစဉ် ကွန်ပျူတာမှတ်ဉာဏ် သုံးစွဲမှုများပြားမည်ဖြစ်သည်။
   * |checkbox| :guilabel:`Simplify geometries to reduce output file size` ကို အမှန်ခြစ်ခြင်းဖြင့် Export resolution (ကြည်လင်ပြတ်သားမှု) ၌ သိသိသာသာ ကွဲပြားမှုမရှိသော vertex များကိုမဆို ဖယ်ရှားခြင်းဖြင့် layout အား export ထုတ်ယူနေစဉ်တွင် ဂျီဩမေတြီများအား ရိုးရှင်းအောင်လုပ်ပေးမည်ဖြစ်သည် (ဥပမာအားဖြင့်- export resolution သည် ``300 dpi`` ဖြစ်လျှင်၊ ``1/600 inch`` ထက် သေးငယ်သော vertex များအား ဖယ်ရှားပေးပါလိမ့်မည်)။ ၎င်းသည် export ထုတ်ယူသောဖိုင်၏ အရွယ်အစားနှင့် ရှုပ်ထွေးမှုကို လျော့ချပေးနိုင်ပါသည် (အရွယ်အစားအလွန်ကြီးမားသော ဖိုင်များသည် အခြား application များတွင် ထည့်သွင်းအသုံးပြုရာ၌ အဆင်မပြေဖြစ်စေနိုင်ပါသည်)။

.. _figure_layout_output_pdf:

.. figure:: img/pdf_export_options.png
   :align: center

   PDF Export ရွေးချယ်စရာများ

.. note:: GeoPDF export ထုတ်ခြင်းအား ပံ့ပိုးပေးပြီး၊ သီးခြား GeoPDF ရွေးချယ်စရာအများအပြားလည်း ရရှိနိုင်ပါသည်။ 
   
   * :guilabel:`Format` (GeoPDF အမျိုးအစား - အချို့ကွဲပြားသော GeoPDF များရှိပါသည်)၊
   * :guilabel:`Include multiple map themes` (ပါဝင်စေမည့် မြေပုံ theme များကို သတ်မှတ်ပါ)၊
   * :guilabel:`Include vector feature information` (Layer များကို ရွေးချယ်ပြီး ၎င်းတို့အား ကျိုးကြောင်းဆီလျော်သော PDF အုပ်စုများအဖြစ်သို့ အုပ်စုဖွဲ့ပါ)

.. note:: Georeference ပြုလုပ်ခြင်းအား ပံ့ပိုးပေးသော format များသို့ print layout တစ်ခုအား export ထုတ်ယူခြင်း (ဉပမာအားဖြင့်- ``PDF`` နှင့် ``TIFF``) သည် default အားဖြင့် georeference ပြုလုပ်ပြီးသား ရလာဒ်တစ်ခုကို ဖန်တီးပေးပါသည်။ 

.. index:: Atlas generation

.. _atlas_generation:

Generate an Atlas (မြေပုံစီးရီးတစ်ခု ထုတ်ယူခြင်း) 
===================================================

Atlas (မြေပုံစီးရီး) လုပ်ဆောင်ချက်များသည် အလိုအလျောက်နည်းလမ်းဖြင့် မြေပုံစာအုပ်များကို ဖန်တီးနိုင်စေပါသည်။ Atlas သည် ဇယား / layer ထဲရှိ feature တစ်ခုချင်းစီ (**atlas feature**) အတွက် ရလာဒ်တစ်ခုအား ဖန်တီးရန် vector layer တစ်ခု (:guilabel:`Coverage layer`) သို့မဟုတ် ဇယားတစ်ခု၏ feature များကို အသုံးပြုပါသည်။ အသုံးအများဆုံးအရာမှာ မြေပုံ item တစ်ခုကို လက်ရှိ atlas feature သို့ zoom (အကျယ်ချဲ့) ပြုလုပ်ရန်ဖြစ်ပါသည်။ နောက်ထပ်အသုံးပြုမှုများတွင် အောက်ပါအရာတို့ပါဝင်သည်-

* အခြား layer တစ်ခုအတွက် atlas feature ကဲ့သို့ တူညီသော attribute ကို မျှဝေသုံးစွဲသော သို့မဟုတ် ၎င်း၏ ဂျီဩမေတြီအတွင်းတွင်ရှိသော feature များကိုသာ ပြသသော မြေပုံ item တစ်ခု။
* Feature များကို ထပ်တလဲလဲလုပ်ဆောင်သည့်အတိုင်း ၎င်း၏စာသားကို အစားထိုးပေးသော အညွှန်းတစ်ခု သို့မဟုတ်  HTML item တစ်ခု။
* လက်ရှိ atlas feature ၏ ဆက်စပ်နေသည့် :ref:`parent သို့မဟုတ် children <vector_relations>` feature များ၏ attribute များကို ပြသေသော ဇယား item တစ်ခု... 
  
Feature တစ်ခုချင်းစီအတွက်၊ ရလာဒ် သည် ၎င်းတို့၏ export setting များအတိုင်း စာမျက်နှာအားလုံးနှင့် item များအားလုံးအတွက် လုပ်ဆောင်မည်ဖြစ်သည်။ 


.. tip:: **ပိုမိုလိုက်လျောညီထွေဖြစ်စေရန်အတွက် variable (ကိန်းရှင်) များကိုအသုံးပြုပါ**

   QGIS တွင် များစွာသော လုပ်ဆောင်ချက်များနှင့် :ref:`variable (ကိန်းရှင်) <general_tools_variables>` များအား ပံ့ပိုးပေးထားပါသည်။ ၎င်းတို့တွင် atlas အခြေအနေအရ layout item များကို ကိုင်တွယ်နိုင်သလို layer များ၏ သင်္ကေတဆိုင်ရာများကို ကိုင်တွယ်နိုင်သည့် atlas နှင့်သက်ဆိုင်သော လုပ်ဆောင်ချက်များနှင့် variable များပါဝင်ပါသည်။ အဆိုပါ feature များကိုပေါင်းစပ်ခြင်းဖြင့် အဆင့်မြင့် မြေပုံများထုတ်လုပ်ရာတွင် များစွာအဆင်ပြေလွယ်ကူစေမည်ဖြစ်ပါသည်။

Atlas တစ်ခုထုတ်ယူရန်နှင့် atlas parameter များကို အသုံးပြုရန် :guilabel:`Atlas` panel အား &ရည်ညွှန်းပါ။ ၎င်း panel တွင် အောက်ပါတို့ ပါဝင်ပါသည် (:numref:`figure_layout_atlas` တွင် ကြည့်ပါ)-

.. _figure_layout_atlas:

.. figure:: img/atlas_properties.png
   :align: center

   Atlas Panel

* |checkbox| :guilabel:`Generate an atlas` -  Atlas ထုတ်ယူခြင်းအား ဖွင့်ပေးနိုင်သည် သို့မဟုတ် ပိတ်ပေးနိုင်သည် 
* :guilabel:`ပြင်ဆင်သတ်မှတ်ခြင်း`

  * :guilabel:`Coverage layer` |selectString| combo box တစ်ခုသည် ထပ်ခါတလဲလဲ လုပ်ဆောင်မည့် feature များပါဝင်သော ဇယား သို့မဟုတ် vector layer ကို ရွေးချယ်ခွင့်ပေးပါသည်။
  * မဖြစ်မနေလုပ်ရန်မလိုသည့် |checkbox| :guilabel:`Hidden coverage layer` ကို အမှန်ခြစ်ထားလျှင် ထုတ်လုပ်မှုဆောင်ရွက်နေစဉ်တွင် coverage layer (အခြား layer များမပါဝင်ပါ) အား ဖျောက်ထားပေးပါလိမ့်မည်။
  * မဖြစ်မနေလုပ်ရန်မလိုသည့် :guilabel:`Page name` combo box သည် feature စာမျက်နှာ (များ) ၏ နာမည်အတွက် သတ်မှတ်ရန်ဖြစ်သည်။ Coverage layer ၏ field တစ်ခုကို ရွေးချယ်နိုင်သလို	:ref:`expression <vector_expressions>` တစ်ခုလည်း သတ်မှတ်ပေးနိုင်ပါသည်။ ဤ option သည် ဗလာဖြစ်နေပါက၊ layer တွင်အသုံးပြုထားသော filter (စစ်ထုတ်မှု) နှင့်/သို့မဟုတ် sort order (အစီအစဉ်) အရ QGIS သည် internal ID တစ်ခုကို အသုံးပြုပါလိမ့်မည်။ 
  * မဖြစ်မနေလုပ်ရန်မလိုသည့် |checkbox| :guilabel:`Filter with` စာသားဧရိယာတွင် coverage layer မှ feature များကို စစ်ထုတ် (filter) ရန်အတွက် expression တစ်ခုကို သတ်မှတ်နိုင်ပါသည်။ Expression သည် ဗလာဖြစ်မနေပါက ``True`` ဖြစ်သော feature များကိုသာ ဆက်လက်လုပ်ဆောင်သွားမည်ဖြစ်သည်။
  * မဖြစ်မနေလုပ်ရန်မလိုသည့် |checkbox| :guilabel:`Sort by` သည် coverage layer ၏ field တစ်ခု သို့မဟုတ် expression တစ်ခုကို အသုံးပြု၍ coverage layer ၏ feature များကို စီစဉ် (sort) ပေးနိုင်ပါသည်။ အစီအစဉ် (sort order) (ငယ်စဉ်ကြီးလိုက် သို့မဟုတ် ကြီးစဉ်ငယ်လိုက် တစ်ခုမဟုတ်တစ်ခု) အား အပေါ်အောက် မြှားတစ်ခုကိုပြသော *Sort direction* ခလုတ်ဖြင့် သတ်မှတ်ပေးပါသည်။
* :guilabel:`Output`- ၎င်းသည် atlas တစ်ခု၏ ရလာဒ်အား ပြင်ဆင်သတ်မှတ်နိုင်မည့် နေရာဖြစ်သည်-
  
  * Atlas feature တစ်ခုချင်းစီအတွက် ဖိုင်အမည်တစ်ခုအား ပေးရန်အတွက် :guilabel:`Output filename expression` စာသားဘောက်အား အသုံးပြုပါသည်။ ၎င်းသည် expression များပေါ်တွင် အခြေခံထားပါသည်။ ၎င်းသည် ဖိုင်များစွာ သို့ ပုံဖော်ပြသခြင်းအတွက်သာလျှင် အဓိပ္ပါယ်ရှိပါသည်။
  * ရွေးချယ်ထားသော ရလာဒ်ပုံစံသည် ဖြစ်နိုင်မှုရှိလျှင် (ဉပမာအားဖြင့်- ``PDF``) |checkbox| :guilabel:`Single file export when possible` သည် ဖိုင်တစ်ခုတည်းကို ထုတ်ပေးနိုင်စေပါသည်။ ဤ field ကိုအမှန်ခြစ်ထားလျှင် :guilabel:`Output filename expression` field ၏တန်ဖိုးသည် အဓိပ္ပါယ်ရှိတော့မည်မဟုတ်ပါ။
  * |saveMapAsImage| :sup:`Export atlas as Images...`  ခလုတ်အား အသုံးပြုသည့်အခါ
	ရလာဒ်ပုံစံအား ရွေးချယ်ရန်အတွက် :guilabel:`Image export format` ရွေးချယ်နိုင်သည့်စာရင်းတစ်ခု။ 

Control map by atlas (Atlas ဖြင့် မြေပုံအား ထိန်းချုပ်ခြင်း) 
--------------------------------------------------------------

Atlas ၏ အသုံးအများဆုံးဖြစ်သောအရာမှာ coverage layer ပေါ်တွင် ထပ်ခါတလဲလဲလုပ်ဆောင်သည့်အတိုင်း လက်ရှိ atlas feature သို့ zoom ချဲ့ပေးသော မြေပုံ item ဖြစ်ပါသည်။ ၎င်းဆောင်ရွက်ချက်အား မြေပုံ item ၏ :guilabel:`Controlled by atlas` အုပ်စု ဂုဏ်သတ္တိများထဲတွင် သတ်မှတ်ထားပါသည်။ မြေပုံ item များပေါ်တွင် အသုံးချနိုင်သော setting အမျိုးမျိုးအတွက် :ref:`controlled_atlas` ကိုကြည့်ပါ။ 


.. _atlas_labels:

Customize labels with expression (Expression ဖြင့် အညွှန်းများအား စိတ်ကြိုက်ပြင်ဆင်ခြင်း)
------------------------------------------------------------------------------------------

Atlas ထပ်တလဲလဲ လုပ်ဆောင်သော feature တွင် အညွှန်းများအား လိုက်လျောညီထွေဖြစ်စေရန်အတွက် expression များအား ထည့်သွင်းနိုင်ပါသည်။ Expression အစိတ်အပိုင်း (လုပ်ဆောင်ချက်များ၊ field များ သို့မဟုတ် variable များအပါအဝင်) အား ``[%`` နှင့် ``%]`` ကြားတွင် ထားရှိရပါမည် (ပိုမိုအသေးစိတ်များအတွက် :ref:`layout_label_item` ကိုကြည့်ပါ)။

ဉပမာအားဖြင့်- ``CITY_NAME`` နှင့် ``ZIPCODE`` field များပါဝင်သော မြို့ layer တစ်ခုအတွက်
အောက်ပါအတိုင်း ထည့်သွင်းနိုင်ပါသည်- 

.. code::

   The area of [% concat( upper(CITY_NAME), ',', ZIPCODE, ' is ',
   format_number($area/1000000, 2) ) %] km2

သို့မဟုတ်၊ နောက်ထပ် အခြား ပေါင်းစပ်ခြင်းအတွက်-

.. code::

   The area of [% upper(CITY_NAME)%],[%ZIPCODE%] is
   [%format_number($area/1000000,2) %] km2

``[% concat( upper(CITY_NAME), ',', ZIPCODE, ' is ',  format_number($area/1000000, 2) ) %]`` သည် အညွှန်းထဲတွင် အသုံးပြုသော expression တစ်ခုဖြစ်ပါသည်။ Expression နှစ်ခုစလုံးသည် ထုတ်လုပ်လိုက်သော atlas ထဲတွင် အောက်ဖော်ပြပါ အညွှန်းအမျိုးအစားဖြင့် ရလာဒ်ရရှိမည်ဖြစ်သည်- 
::

  The area of PARIS,75001 is 1.94 km2


.. _atlas_data_defined_override:

Explore Data-defined override buttons with atlas (Atlas ဖြင့် data သတ်မှတ်ထားသော အစားထိုးလုပ်ဆောင်ခြင်းခလုတ်များအား ရှာဖွေဖော်ထုတ်ခြင်း)
-----------------------------------------------------------------------------------------------------------------------------------------

ရွေးချယ်ထားသော setting အား အစားထိုးလုပ်ဆောင်ရန် |dataDefine|:sup:`Data defined override` button အား အသုံးပြုနိုင်သော နေရာများစွာရှိပါသည်။ ၎င်း widget နှင့်ပတ်သက်သော အသေးစိတ်များအတွက် :ref:`data_defined` တွင် ကြည့်နိုင်ပါသည်။ 

အောက်ဖော်ပြပါနမူနာများအတွက် atlas ထုတ်ယူခြင်းတွင် QGIS နမူနာ dataset ၏ :file:`Regions` layer အားအသုံးပြု၍ :guilabel:`Coverage layer` အဖြစ် ရွေးချယ်ပါသည်။ မြေပုံ item တစ်ခုနှင့် အညွှန်း item တစ်ခုပါဝင်သော page layout တစ်ခုတည်းအဖြစ် ၎င်းကို ယူဆထားပါသည်။

ဒေသ နယ်ပယ်အကျယ်အဝန်း၏အမြင့် (မြောက်-တောင်) သည် ၎င်း၏ အကျယ် (အရှ့-အနောက်) ထက် ပိုကြီးသည့်အခါ၊ စာရွက်အသုံးပြုမှုအနေအထားအား ကောင်းမွန်စေရန်အတွက် *Landscape* အား သုံးမည့်အစား *Portrait* အား အသုံးပြုသင့်ပါသည်။ |dataDefine| :sup:`Data Defined Override` ခလုတ်ဖြင့် စာရွက်အနေအထားကို ပြောင်းလဲသတ်မှတ်နိုင်ပါသည်။ 

Panel အား ဖွင့်ရန် စာမျက်နှာပေါ်တွင် right-click နှိပ်ပြီး :guilabel:`Page Properties` အား ရွေးချယ်ပါ။ ဒေသ ဂျီဩမေတြီပေါ်တွင် မူတည်သော expression တစ်ခုအားအသုံးပြုပြီး ပြောင်းလဲနိုင်သော ဦးတည်ရာအဖြစ် သတ်မှတ်လိုလျှင် :guilabel:`Orientation` field ၏ |dataDefine| ခလုတ်ကိုနှိပ်၍ :guilabel:`Expression string builder` dialog ပွင့်လာစေရန် :guilabel:`Edit...` ကိုရွေးချယ်ပါ။ ထို့နောက် အောက်ဖော်ပြပါ expression ကို ရိုက်ထည့်ပါ-

.. code::

   CASE WHEN bounds_width(@atlas_geometry) > bounds_height(@atlas_geometry)
   THEN 'Landscape' ELSE 'Portrait' END

ယခုဆိုလျှင် :ref:`atlas အားအကြိုကြည့်ရှုခြင်း <atlas_preview>` ပြုလုပ်လျှင်၊ စာရွက်သည် ၎င်းဘာသာ အလိုအလျောက် ဦးတည်မည်ဖြစ်သည်၊ သို့သော် item နေရာချထားခြင်းများမှာ အကောင်းဆုံးအနေအထား ဖြစ်မည်မဟုတ်ပါ။ ဒေသတစ်ခုချင်းစီအတွက် layout item များ၏ တည်နေရာကိုလည်း ပြန်လည်နေရာချထားရန် လိုအပ်ပါသည်။ မြေပုံ item အတွက် ၎င်း၏ :guilabel:`Width` (အကျယ်) ဂုဏ်သတ္တိ၏ |dataDefine| ခလုတ်ကိုအသုံးပြု၍ အောက်ဖော်ပြပါ expression ဖြင့် ပြောင်းလဲနိုင်အောင် သတ်မှတ်နိုင်ပါသည်- 

.. code::

   @layout_pagewidth - 20

ထိုနည်းတူစွာပင်၊ မြေပုံ item အရွယ်အစားအား ကန့်သတ်ရန် :guilabel:`Height` (အမြင့်) ဂုဏ်သတ္တိ၏ |dataDefine| ခလုတ်ဖြင့် အောက်ဖော်ပြပါ expression အား အသုံးပြုပါ- 

.. code::

   @layout_pageheight - 20

မြေပုံ item များအား စာမျက်နှာအလယ်၌ ထားရှိရန်အတွက်၊ ၎င်း၏ :guilabel:`အကိုးအကား point` အား ဘယ်ဘက်အထက် radio ခလုတ်တွင် သတ်မှတ်ပြီး၊ ၎င်း :guilabel:`X` နှင့် :guilabel:`Y` တည်နေရာများ အတွက် ``10`` အား ရိုက်ထည့်ပါ။ 

စာမျက်နှာအလယ်ရှိ မြေပုံအပေါ်တွင် ခေါင်းစဉ်တစ်ခုအား ပေါင်းထည့်ကြည့်ကြပါစို့။ အညွှန်း item အား ရွေးချယ်ပြီး၊ ရေပြင်ညီ ချိန်ညှိမှုအား |radioButtonOn| :guilabel:`Center` သို့ ထားပါ။ ထို့နောက် အညွှန်းများအား ညာဘက်သို့ ရွေ့ပြီး၊ :guilabel:`အကိုးအကား point` အတွက် အလယ် ခလုတ်ကို ရွေးချယ်ကာ :guilabel:`X` field အတွက် အောက်ဖော်ပြပါ expression ကိုထည့်ပါ- 

.. code::

   @layout_pagewidth / 2

အခြား layout item များအားလုံးအတွက် ၎င်းတို့အား အလျားလိုက်ပုံ (landscape) နှင့် ဒေါင်လိုက်ပုံ (portrait) နှစ်ခုစလုံးအတွက် မှန်ကန်စွာနေရာချထားစေရန် အလားတူနည်းလမ်းအတိုင်း တည်နေရာကို သတ်မှတ်နိုင်ပါသည်။ Feature attribute များဖြင့် ခေါင်းစဉ်ကို စိတ်ကြိုက်ပြင်ဆင်ခြင်း (:ref:`atlas_labels` ဥပမာကို ကြည့်ပါ)၊ ဓာတ်ပုံများပြောင်းလဲခြင်း၊ စာမျက်နှာအနေအထားအလိုက် မြေပုံရည်ညွှန်းချက် ကော်လံ အရေအတွက်များအား ပြန်လည်ချိန်ညှိခြင်းကဲ့သို့သော ထပ်မံချိန်ညှိမှုများကိုလည်း လုပ်ဆောင်နိုင်ပါသည်။

ဤနေရာတွင် ဖော်ပြထားသော သတင်းအချက်အလက်များသည် data ဖြင့်သတ်မှတ်ပြီး အစားထိုးလုပ်ဆောင်သော option များ Multiple_format_map_series_using_QGIS_2.6_ နှင့်ပတ်သက်သော အကောင်းဆုံး blog (အင်္ဂလိပ်နှင့် ပေါ်တူဂီဘာသာ) ၏ နောက်ဆုံးအခြေအနေဖော်ပြချက်တစ်ခုဖြစ်ပါသည်။ 

Data ဖြင့်သတ်မှတ်ပြီး အစားထိုးလုပ်ဆောင်မှု ခလုတ်များအား အသုံးပြုခြင်းအတွက် အခြားဥပမာမှာ  ပြောင်းလဲနိုင်သော ရုပ်ပုံအား အသုံးပြုခြင်းပင်ဖြစ်သည်။ အောက်ဖော်ပြပါ ဥပမာများအတွက်၊ binary field အမျိုးအစားဖြင့် ``logo`` ဟုခေါ်သော BLOB field တစ်ခုပါဝင်သော geopackage layer တစ်ခုကို အသုံးပြုထားပါသည် (:ref:`vector_create_geopackage` တွင် ကြည့်ပါ)။ Feature အားလုံးအတွက် :ref:`atlas_preview` တွင်ဖော်ပြထားသည့်အတိုင်း atlas အား ထပ်ခါတလဲလဲပြုလုပ်နိုင်စေရန် မတူညီသော ရုပ်ပုံတစ်ခုကို သတ်မှတ်ထားပါသည်။ ပြုလုပ်ရမည်မှာ print layout တွင် ရုပ်ပုံအား ထည့်ရန်ဖြစ်ပြီး၊ atlas မာတိကာရှိ ၎င်း၏ :guilabel:`Item properties` သို့သွားရောက်ရန်ဖြစ်သည်။ အဆိုပါနေရာတွင် :guilabel:`Main Properties` ၏ :guilabel:`Image source` ကဏ္ဍရှိ data-defined override ခလုတ်အား ရှာတွေ့နိုင်မည်ဖြစ်သည်။ 


.. _figure_image_source:

.. figure:: img/picture_image_source.png
   :align: center

:guilabel:`Expression String Builder` အား ဖွင့်ရန်အတွက် အောက်ဖော်ပြပါ window ထဲတွင် :guilabel:`Edit` အားရွေးချယ်ပါ။ :guilabel:`Fields and values` ကဏ္ဍမှ geopackage layer ထဲတွင် အဓိပ္ပါယ်သတ်မှတ်ထားသော BLOB field အား တွေ့ရှိနိုင်မည်ဖြစ်သည်။ Field နာမည် :file:`logo` အား click နှစ်ချက်နှိပ်ပြီး :guilabel:`OK` ကို နှိပ်ပါ။ 

 
.. _figure_expression_blob_picture_atlas:
 
.. figure:: img/expression_blob_picture_atlas.png
   :align: center

:guilabel:`Coverage layer` အဖြစ် ရွေးချယ်ထားသော geopackage layer မှ BLOB field ထဲရှိ ထည့်သွင်းထားသည့်အရာများပေါ်တွင် atlas သည် ထပ်ခါတလဲလဲ လုပ်ဆောင်မည်ဖြစ်သည် (:ref:`atlas_preview` တွင် အခြားညွှန်ကြားချက်များအား ရှာဖွေနိုင်ပါသည်)။

ထိုဥပမာ ၂ ခုသည် Atlas ဖြင့် အဆင့်မြင့် setting အချို့အား မည်သို့ အသုံးပြုနိုင်သည်ကို ဖော်ပြထားသော ဥပမာ ၂ ခု ဖြစ်ပါသည်။ 

.. _atlas_preview:

Preview and generate an atlas (Atlas တစ်ခုအား အကြိုကြည့်ရှုခြင်းနှင့် ထုတ်လုပ်ခြင်း)
-------------------------------------------------------------------------------------

.. _figure_layout_atlas_preview:

.. figure:: img/atlas_preview.png
   :align: center

   Atlas အကြိုကြည့်ရှုခြင်း toolbar

Atlas setting များအား ပြင်ဆင်သတ်မှတ်ပြီး layout item များ (မြေပုံ၊ ဇယား၊ ဓာတ်ပုံ.....) ကို ၎င်းနှင့် ချိတ်ဆက်ပြီးသည်နှင့် စာမျက်နှာအားလုံး၏ အကြိုကြည့်ရှုခြင်းတစ်ခုအား :menuselection:`Atlas --> Preview Atlas` ကိုရွေးချယ်ခြင်း သို့မဟုတ် |atlas| :sup:`Preview Atlas` icon အားနှိပ်ခြင်းဖြင့် ဖန်တီးနိုင်ပါသည်။ ထို့နောက် feature များအားလုံးကို လမ်းညွှန်ပြသနိုင်ရန် မြှားများကိုအသုံးပြုနိုင်မည်ဖြစ်ပါသည်။ 


* |atlasFirst| :sup:`First feature` (ပထမဆုံး feature)
* |atlasPrev| :sup:`Previous feature` (ပြီးခဲ့သော feature)
* |atlasNext| :sup:`Next feature` (နောက်ထပ် feature)
* |atlasLast| :sup:`Last feature` (နောက်ဆုံး feature)

သီးခြား feature တစ်ခုကို ရွေးချယ်ပြီး အကြိုကြည့်ရှုရန် combo box အား အသုံးပြုနိုင်ပါသည်။ Atlas :guilabel:`Page name` option ထဲတွင် သတ်မှတ်ထားသော expression ပေါ်မူတည်ပြီး combo box သည် atlas feature နာမည်များကို ပြသပေးမည်ဖြစ်ပါသည်။

ရိုးရှင်းသော ဖွဲ့စည်းမှုများအတွက်၊ atlas တစ်ခုအား နည်းလမ်းများစွာဖြင့် ထုတ်လုပ်နိုင်ပါသည် (ထပ်မံသိလိုပါက :ref:`create-output` တွင် ကြည့်ရှုပါ)- :menuselection:`Layout` menu အသုံးပြုမည့်အစား :menuselection:`Atlas` menu သို့မဟုတ် toolbar မှ tool များအား အသုံးပြုပါ။

:menuselection:`Atlas --> Print Atlas` ဖြင့် မြေပုံဖွဲ့စည်းမှုများကို တိုက်ရိုက် ပုံနှိပ်ထုတ်ယူနိုင်သည် ဟု ဆိုလိုပါသည်။ :menuselection:`Atlas --> Export Atlas as PDF...` အား အသုံးပြုပြီး PDF ဖိုင်လည်း ဖန်တီးနိုင်ပါသည်။ |checkbox| :guilabel:`Single file export when possible` အား ရွေးချယ်ထားသည်မှလွဲ၍ ထုတ်လုပ်လိုက်သော PDF ဖိုင်များအားလုံးအတွက် သိမ်းဆည်းရန်လမ်းကြောင်းတစ်ခုအား ပေးရပါလိမ့်မည်။ ဤဖြစ်စဉ်တွင် ဖိုင်အမည်တစ်ခုအား ပေးရန် မေးမြန်းပါလိမ့်မည်။ 

:menuselection:`Atlas --> Export Atlas as Images...` သို့မဟုတ် :menuselection:`Atlas --> Export Atlas as SVG...` tool ဖြင့် folder တစ်ခုကိုရွေးချယ်ရပါမည်။ Atlas feature ဖွဲ့စည်းမှုတစ်ခုချင်းစီ၏ စာမျက်နှာတစ်ခုချင်းစီအား :guilabel:`Atlas` panel ထဲတွင် သတ်မှတ်ထားသော ဓာတ်ပုံဖိုင် format သို့မဟုတ် SVG format သို့ export ထုတ်ယူမည်ဖြစ်သည်။ 

.. note::
   
   စာမျက်နှာများစွာပါဝင်သော output များဖြင့်၊ atlas တစ်ခုသည် :ref:`reference_map` ပါဝင်ပြီး world file တစ်ခုရရှိမည့် စာမျက်နှာထဲတွင်သာ layout တစ်ခုကဲ့သို့ ပြုမူဆောင်ရွက်မည်ဖြစ်သည် (feature output တစ်ခုချင်းစီအတွက်)။

.. tip:: **သီးခြား atlas feature တစ်ခုကို print ပြုလုပ်ပါ**

  Atlas feature တစ်ခုတည်း၏ ဖွဲ့စည်းမှုအား print သို့မဟုတ် export ပြုလုပ်လိုလျှင် ကြိုတင် ကြည့်ရှုခြင်းအား စတင်ပါ၊ drop-down စာရင်းထဲရှိ အလိုရှိသော feature ကိုရွေးချယ်ပြီး :menuselection:`Layout --> Print` အား click နှိပ်ပါ (သို့မဟုတ် လက်ခံနိုင်သော ဖိုင် format တစ်ခုခုသို့ :menuselection:`Export...` ပြုလုပ်ပါ)။

.. _Multiple_format_map_series_using_QGIS_2.6: https://sigsemgrilhetas.wordpress.com/2014/11/09/series-de-mapas-com-formatos-multiplos-em-qgis-2-6-parte-1-multiple-format-map-series-using-qgis-2-6-part-1

.. _relations_in_atlas:

Use project defined relations for atlas creation (Atlas ဖန်တီးခြင်းအတွက် project မှသတ်မှတ်ထားသော ဆက်နွယ်ချက်များကို အသုံးပြုခြင်း)
-----------------------------------------------------------------------------------------------------------------------------------

HTML နှင့်  Javascript ကျွမ်းကျင်သူများအတွက် GeoJSON object များပေါ်တွင် လုပ်ဆောင်နိုင်မည်ဖြစ်ပြီး QGIS project မှ သတ်မှတ်ထားသော ဆက်နွယ်ချက်များအား အသုံးပြုနိုင်မည်ဖြစ်ပါသည်။ ဤနည်းလမ်းကိုအသုံးပြုခြင်းနှင့် HTML ထဲသို့ တိုက်ရိုက်ထည့်သွင်းသော expression များအား အသုံးပြုခြင်းအကြား ခြားနားချက်မှာ ဤနည်းလမ်းကိုအသုံးပြုခြင်းသည် ၎င်းနှင့်လုပ်ကိုင်ဆောင်ရွက်ရန် ဖွဲ့စည်းပုံသေချာမရှိသော GeoJSON feature အပြည့်အစုံအား ပေးထားခြင်းပင်ဖြစ်သည်။ ဆိုလိုသည်မှာ GeoJSON feature ကိုယ်စားပြုမှုများပေါ်တွင် လုပ်ကိုင်ဆောင်ရွက်နိုင်သော ရှိနေပြီးသား Javascript library များနှင့်လုပ်ဆောင်ချက်များအား အသုံးပြုနိုင်မည်ဖြစ်သည်။ 

အောက်ဖော်ပြပါ code များတွင် သတ်မှတ်ထားသည့်ဆက်နွယ်ချက်မှ ဆက်စပ် child (အခွဲ) feature များအားလုံးပါဝင်ပါသည်။ JavaScript ``setFeature`` function အား အသုံးပြုခြင်းသည် မိမိနှစ်သက်ရာ format (စာရင်းများ၊ ဇယားများ၊ အစရှိသည်) ဖြင့် ဆက်နွယ်ချက်ကို ကိုယ်စားပြုသော လိုက်လျောညီထွေဖြစ်သော HTML အား ဖန်တီးနိုင်စေပါသည်။ နမူနာ code တွင် ဆက်စပ် child feature များ၏ ပြောင်းလဲနိုင်သော စာရင်းအား ဖန်တီးခြင်းဖြစ်ပါသည်။ 

.. code:: html

   // Declare the two HTML div elements we will use for the parent feature id
   // and information about the children
   <div id="parent"></div>
   <div id="my_children"></div>

   <script type="text/javascript">
      function setFeature(feature)
      {
        // Show the parent feature's identifier (using its "ID" field)
        document.getElementById('parent').innerHTML = feature.properties.ID;
        //clear the existing relation contents
        document.getElementById('my_children').innerHTML = ''; 
        feature.properties.my_relation.forEach(function(child_feature) {
        // for each related child feature, create a list element
        // with the feature's name (using its "NAME" field)
          var node = document.createElement("li");
          node.appendChild(document.createTextNode(child_feature.NAME));
          document.getElementById('my_children').appendChild(node);
        });
      }
   </script>

Atlas ဖန်တီးနေစဉ်အတွင်း၊ parent (မူရင်း) feature များပါဝင်သော coverage layer ပေါ်တွင် ထပ်ခါတလဲလဲ လုပ်ဆောင်မှုတစ်ခု ရှိပါလိမ့်မည်။ စာမျက်နှာတစ်ခုစီတွင် parent identifier နောက်၌ ဆက်စပ် child feature များ၏စာရင်းတစ်ခုအား တွေ့မြင်ရပါလိမ့်မည်။ 

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |atlas| image:: /static/common/mIconAtlas.png
   :width: 1.5em
.. |atlasFirst| image:: /static/common/mActionAtlasFirst.png
   :width: 1.5em
.. |atlasLast| image:: /static/common/mActionAtlasLast.png
   :width: 1.5em
.. |atlasNext| image:: /static/common/mActionAtlasNext.png
   :width: 1.5em
.. |atlasPrev| image:: /static/common/mActionAtlasPrev.png
   :width: 1.5em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dataDefine| image:: /static/common/mIconDataDefine.png
   :width: 1.5em
.. |filePrint| image:: /static/common/mActionFilePrint.png
   :width: 1.5em
.. |radioButtonOn| image:: /static/common/radiobuttonon.png
   :width: 1.5em
.. |saveAsPDF| image:: /static/common/mActionSaveAsPDF.png
   :width: 1.5em
.. |saveAsSVG| image:: /static/common/mActionSaveAsSVG.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em
.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
