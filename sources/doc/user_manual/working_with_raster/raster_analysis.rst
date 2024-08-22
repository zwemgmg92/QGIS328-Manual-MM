.. index:: Raster analysis
.. _sec_raster_analysis:

***************************************************
Raster Analysis (Raster များအား ဆန်းစစ်လေ့လာခြင်း)
***************************************************

.. only:: html

   .. contents::
      :local:

.. index:: Raster calculator
.. _label_raster_calc:

Raster Calculator (Raster ဂဏန်းတွက်စက်)
========================================

:menuselection:`Raster` menu ထဲရှိ :menuselection:`Raster Calculator` သည် ရှိနေပြီးသား raster pixel တန်ဖိုးများ၏ အခြေခံတွက်ချက်မှုများကို လုပ်ဆောင်ပေးနိုင်ပါသည်။ (:numref:`figure_raster_calculator` တွင်ကြည့်ပါ)
တွက်ထုတ်ပြီးရလာသည့် ရလာဒ် ကို raster layer အသစ်ထဲတွင်ရေးထားပြီး GDAL-supported format အဖြစ်သိမ်းထားပေးပါတယ်။

.. _figure_raster_calculator:

.. figure:: img/raster_calculator.png
   :align: center

   Raster ဂဏန်းပေါင်းစက်


:guilabel:`Raster bands` စာရင်းထဲတွင် အသုံးပြုနိုင်သည့် ထည့်သွင်းထားသော raster layer များအားလုံးပါဝင်ပါသည်။ 
Raster expression field တွင် raster တစ်ခုထည့်ရန် Field စာရင်းထဲတွင် ၎င်း၏နာမည်ကို double click နှိပ်ပါ။ 
တွက်ချက်မှု expression များ တည်ဆောက်ရန် operator (ပေါင်း၊ နှုတ်၊ မြှောက်၊ စား) များကို အသုံးပြုနိုင်ပါသည် သို့မဟုတ် box ထဲတွင် စာရိုက်ပြီး ရေးနိုင်ပါသည်။

:guilabel:`Result layer` (ရလာဒ် layer) section တွင် ရလာဒ် (output) layer တစ်ခုသတ်မှတ်ပေးရန် အောက်ပါနည်းလမ်းများကို အသုံးပြုနိုင်ပါသည်-

* |checkbox| :guilabel:`Create on-the-fly raster instead of writing layer to disk` (ကွန်ပြူတာပေါ်တွင် layer အသစ်တစ်ခုဖန်တီးရေးသားမည့်အစား အလွယ်တကူယာယီပြပေးနိုင်သည့် on-the-fly raster တစ်ခုကို ဖန်တီးပါ)-

  * အမှန်ခြစ်မထားလျှင် output ကို ကွန်ပြူတာထဲတွင်  file အသစ်တစ်ခုအဖြစ်သိမ်းဆည်းပေးပါမည်။ :guilabel:`Output layer` သိမ်းဆည်းပေးမည့်လမ်းကြောင်း နှင့် :guilabel:`Output format` သတ်မှတ်ပေးရန် လိုအပ်ပါသည်။
	
  * အမှန်ခြစ်ထားလျှင် virtual raster layer တစ်ခု ဖန်တီးပေးပါမည်။ ၎င်းသည် ကွန်ပြူတာပေါ်ရှိ file အသစ်တစ်ခုမဟုတ်ပါ။ 
    ထို virtual layer သည် တွက်ချက်မှုလုပ်ခဲ့သည့် raster များနှင့် ချိတ်ဆက်နေဆဲ ဖြစ်ပြီး ထို မူရင်း raster များကို ဖျက်ခြင်း/နေရာရွှေ့ခြင်းများ ပြုလုပ်လျှင် virtual raster layer သည် အလုပ်လုပ်ခြင်းရပ်တန့်သွားပါမည်။ 
    :guilabel:`Layer name` တစ်ခုပေးထားနိုင်ပါသည်။ မဟုတ်လျှင် calculation expression နာမည်ဖြင့် ဖော်ပြနေမည် ဖြစ်ပါသည်။ 
    Virtual layer ကို project မှ ဖယ်ရှားလိုက်ခြင်းသည် ၎င်းကိုဖျက်လိုက်ခြင်း ဖြစ်ပါသည်။ ဒါမှမဟုတ် အမြဲတမ်းသိမ်းဆည်းထားလိုလျှင် layer ကို right-click နှိပ်ပြီး :menuselection:`Export --> Save as...` ကို အသုံးပြုနိုင်ပါသည်။

* ထည့်သွင်းထားသည့် (input) raster layer ၏ extent (အတိုင်းအတာပမာဏ) သို့မဟုတ် စိတ်ကြိုက် X, Y တည်နေရာတန်ဖိုးများကို အသုံးပြုပြီး တွက်ချက်မှုပြုလုပ်ချင်သည့်နေရာ၏ :guilabel:`Spatial extent` (တည်နေရာဆိုင်ရာ extent) ကို သတ်မှတ်ပေးပါ။
* Column (အတိုင်) နှင့် row (အတန်း) များ၏အရေအတွက်ကို အသုံးပြုပြီး layer ၏ ကြည်လင်ပြတ်သားမှု (resolution) ကို သတ်မှတ်ပါ။ 
  အကယ်၍ input layer တွင် မတူညီသည့် resolution ရှိနေပါက တန်ဖိုးများကို nearest neighbor algorithm ဖြင့် resampling ပြုလုပ်မည်ဖြစ်ပါသည်။
* |checkbox| :guilabel:`Add result to project` ကိုအမှန်ခြစ်ထားလျှင် ရလာသည့် layer သည် legend ဧရိယာတွင် အလိုလိုပေါ်လာပြီး ကြည့်ရှုလို့ရနိုင်ပါသည်။ 
  ပုံမှန်အားဖြင့် virtual raster များအတွက် အမှန်ခြစ်က ခြစ်ထားပြီးသား ဖြစ်ပါသည်။ 

:guilabel:`Operators` section တွင် အသုံးပြုနိုင်သည့် operator များအားလုံးပါဝင်ပါသည်။ Raster calculator expression box တွင် operator တစ်ခုထည့်ရန်အတွက် သင့်တော်သော ခလုတ်ကိုနှိပ်ပါ။ 
သင်္ချာတွက်ချက်မှုများ (``+``, ``-``, ``*``, ... ) နှင့် တြီဂိုနိုမေထြီဆိုင်ရာ တွက်ချက်မှုများ (``sin``, ``cos``, ``tan``, ... ) များကိုအသုံးပြုနိုင်ပါသည်။ 
အခြေအနေကို ရွေးချယ်တဲ့တွက်ချက်မှုများ (``=``, ``!=``, ``<``, ``>=``, ... ) သည် အမှားအတွက် 0 သို့မဟုတ် အမှန်အတွက် 1 ဆိုသည့် အဖြေ ၂ မျိုးကိုသာပေးပါသည်။ 
ထို့ကြောင့် ၎င်းကို တခြား operator များ၊ function များနှင့် ပူးတွဲပြီးအသုံးပြုနိုင်ပါသည်။


.. hint:: :ref:`qgisrastercalculator` algorithm ကိုလည်းကြည့်ပါ။  

Examples (ဥပမာများ)
--------------------

**Elevation (မြေမျက်နှာပြင် အနိမ့်အမြင့်) တန်ဖိုးများကို မီတာမှ ပေ စနစ်သို့ပြောင်းလဲခြင်း** 

မီတာတန်ဖိုးဖြင့်ရှိနေသည့် raster တစ်ခုကို ပေ စနစ်ဖြင့်ပြသည့် elevation raster တစ်ခုဖန်တီးခြင်းအတွက် မီတာမှ ပေ စနစ်သို့ ပြောင်းလဲခြင်းတန်ဖိုး (conversion factor) ၃.၂၈ ကို အသုံးပြုဖို့ လိုအပ်ပါသည်။ ရေးရမည့် expression မှာ-

::

 "elevation@1" * 3.28

**Using a mask (လိုချင်သောအပိုင်းကို ဖြတ်ထုတ်ခြင်း)**

Raster တစ်ခုမှ လိုချင်သောအပိုင်းများကို ဖြတ်ထုတ်ချင်သည့်အခါ (ဥပမာ - 0 မီတာနှင့်အထက် ပိုမြင့်သောနေရာများကိုသာစိတ်ဝင်စားသောအခါ) အသုံးပြုလိုသည့်အပိုင်းကိုသာဖြတ်ထုတ်ပေးမည့် mask တစ်ခုဖန်တီးပြီး raster ကို ဖြတ်ထုတ်လို့ရပါသည်။ 
ရေးရမည့် expression မှာ-

::

  ("elevation@1" >= 0) * "elevation@1"

တခြားနည်းဖြင့်ပြောရရင် 0 နှင့်အထက်တန်ဖိုးရှိသည့် cell (pixel) တိုင်းအတွက် မူရင်းတန်ဖိုးကို ၁ ဖြင့်မြှောက်ပြီး အဖြေကို ၁ ဖြစ်အောင်လုပ်ပေးပါသည်။ 
မဟုတ်လျှင် တန်ဖိုးသည် 0 ပဲဖြစ်နေပါမည်။ ဒီနည်းဖြင့် ဖြတ်ထုတ်မည့် mask ကို လုပ်နေစဉ်မှာပဲ အလိုအလျောက် (ယာယီ) ဖန်တီးလိုက်ပါသည်။

::

  ("elevation@1" >= 0) * "elevation@1"

**Raster တစ်ခုကို အတန်းအစားခွဲခြင်း**

Raster တစ်ခုကို အတန်းစားခွဲလိုလျှင် ဥပမာ - elevation အတန်းအစား ၂ မျိုးခွဲခြားလိုလျှင် (မီတာ၅၀အောက် နှင့် မီတာ၅၀နှင့်အထက်) raster မှာ ၁ နှင့် ၂ ဆိုပြီး တန်ဖိုးနှစ်ခုထွက်လာစေရန် အောက်ပါ expression ကို အသုံးပြုနိုင်ပါသည်-

::

  ("elevation@1" < 50) * 1 + ("elevation@1" >= 50) * 2

တခြားနည်းဖြင့်ပြောရရင် တန်ဖိုး ၅၀ အောက်ရောက်နေသော cell (pixel) တိုင်းကို တန်ဖိုး ၁ အဖြစ်သတ်မှတ်ပေးပါသည်။ တန်ဖိုး ၅၀ နှင့်အထက်ရှိနေသော cell အားလုံးကို တန်ဖိုး ၂ အဖြစ်သတ်မှတ်ပေးပါသည်။

သို့မဟုတ် ``IF`` operator ကိုလည်း အသုံးပြုနိုင်ပါသည်။

::

  if ( elevation@1 < 50 , 1 , 2 )

.. index::
   single: Raster; Align Raster
.. _label_raster_align:

Raster Alignment (Raster များအား ချိန်ညှိခြင်း)
================================================

ဤ tool တွင် raster အများကြီးကို တစ်ပြိုင်တည်း ထည့်နိုင်ပြီး အားလုံးကိုပြည့်စုံစွာ ချိန်ညှိပေးနိုင်ပါသည်။ ညှိပေးသောအရာများမှာ-

* CRS တူညီသွားစေရန် reproject လုပ်ပေးခြင်း
* Cell အရွယ်အစားတူညီသွားစေရန် resample လုပ်ပေးခြင်းနှင့် grid ထဲတွင် offset လုပ်ပေးခြင်း
* အလုပ်လုပ်မည့်နေရာအား တူညီအောင်ပိုင်းဖြတ်ပေးခြင်း
* လိုအပ်လျှင် တန်ဖိုးများကို စကေးပြန်ညှိပေးခြင်း တို့ဖြစ်ပါသည်။

Raster များအားလုံးကို file အသစ်များအဖြစ် သိမ်းဆည်းထားပေးပါမည်။

ပထမဆုံးအနေဖြင့် :menuselection:`Raster --> Align Raster...` မှ tool များကိုဖွင့်ပြီး QGIS ထဲတွင်ရှိနေပြီးသား raster တစ်ခုကိုရွေးချယ်ရန် |symbologyAdd| :sup:`Add new raster` ခလုတ်ကို နှိပ်ပါ။
Alignment ပြုလုပ်ပြီးနောက် raster ကို သိမ်းဆည်းထားရန် output file တစ်ခုရွေးချယ်ပါ။ 
:guilabel:`Cell အရွယ်အစားအရ တန်ဖိုးများကို စကေးပြန်ပြောင်းရန်`လိုအပ်လျှင် resampling နည်းလမ်းကို ရွေးချယ်ပါ။ Resampling နည်းလမ်းများမှာ- (:numref:`figure_raster_align_edit` ပုံတွင်ကြည့်ပါ)


* **Nearest Neighbor**
* **Bilinear (2x2 kernel)**
* **Cubic (4x4 kernel)** - လေးထောင့်တုံး Convolution ခန့်မှန်းခြင်း
* **Cubic B-Spline (4x4 kernel)** - လေးထောင့်တုံး B-Spline ခန့်မှန်းခြင်း
* **Lanczos (6x6 kernel)** - Lanczos windowed sinc interpolation
* **Average** - NODATA မဟုတ်တဲ့ pixel တွေအားလုံး၏ ပျမ်းမျှကို တွက်ချက်ခြင်း
* **Mode** - နမူနာ point အားလုံး၏ မကြာခဏ ဖော်ပြတတ်သော တန်ဖိုးကို ရွေးချယ်ခြင်း
* NODATA မဟုတ်သော piexl များအားလုံး၏ **Maximum** ၊ **Minimum** ၊ **Mediane** ၊ **First Quartile (Q1)** သို့မဟုတ် **Third Quartile (Q3)**

.. _figure_raster_align_edit:

.. figure:: img/raster_align_edit.png
   :align: center

   Raster Resampling များရွေးချယ်ခြင်း

အဓိက :guilabel:`Align raster` dialog ထဲတွင် raster layer များ၏ စာရင်းမှ :sup:`Edit file settings` (file setting များတည်းဖြတ်ပြင်ဆင်ခြင်း) သို့မဟုတ် 
|symbologyRemove| :sup:`Remove an existing file` (ရှိနေပြီးသား file တစ်ခုကိုဖယ်ရှားခြင်း) တို့ကိုလုပ်ဆောင်နိုင်ပါသေးသည်။ တစ်ခုထက်ပိုသည့် ရွေးချယ်စရာများလည်း ရှိပါသေးသည်- (:numref:`figure_raster_align` တွင်ကြည့်ပါ)

* :guilabel:`Reference Layer` ကို ရွေးချယ်ပါ၊
* :guilabel:`CRS` အသစ်တစ်ခုသို့ ပြောင်းလဲပါ၊
* မတူညီသည့် :guilabel:`Cell အရွယ်အစား` တစ်ခုကိုပြောင်းသုံးပါ၊
* မတူညီသည့် :guilabel:`Grid Offset` တစ်ခုကိုပြောင်းသုံးပါ၊
* :guilabel:`Clip to Extent` (Extent အတိုင်း ဖြတ်ထုတ်ခြင်း) - ကိုယ်ကသတ်မှတ်‌ပေးသည့် extent ဖြစ်နိုင်သလို layer တစ်ခု၏ extent သို့မဟုတ် map canvas ၏ extent လည်း ဖြစ်နိုင်ပါသည်၊
* :guilabel:`Output Size` (ရလာဒ်၏အရွယ်အစား)၊
* :guilabel:`Add aligned raster to the map canvas` (Map canvas ထဲသို့ align ပြုလုပ်ပြီးသား raster များထည့်ခြင်း)

.. _figure_raster_align:

.. figure:: img/raster_align.png
   :align: center

   Raster များအား Alignment ပြုလုပ်ခြင်း


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |symbologyEdit| image:: /static/common/symbologyEdit.png
   :width: 1.5em
.. |symbologyRemove| image:: /static/common/symbologyRemove.png
   :width: 1.5em
