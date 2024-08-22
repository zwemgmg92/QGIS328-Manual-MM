Interpolation (ရှိပြီသားအချက်အလက်များအပေါ်အခြေခံ၍ ဖြည့်သွင်းတွက်ထုတ်ခြင်း)
===========================================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisheatmapkerneldensityestimation:

Heatmap (kernel density estimation) (သိပ်သည်းမှုပြမြေပုံ (kernel သိပ်သည်းမှုခန့်မှန်းတွက်ချက်ခြင်း))
-----------------------------------------------------------------------------------------------------

Kernel density estimation နည်းလမ်းကိုအသုံးပြုပြီး input point vector layer တစ်ခု၏ သိပ်သည်းမှုပြ မြေပုံ (heatmap) တစ်ခုကိုဖန်တီးပေးပါသည်။

Point အစုအဖွဲ့ပမာဏများများဖြင့် တည်နေရာတစ်ခုတည်းရှိ point များ၏အရေအတွက်ပေါ်အခြေခံပြီး သိပ်သည်းမှုကိုတွက်ချက်ပြီး ရလာဒ်အနေဖြင့် ပိုများသောတန်ဖိုးများကို ရစေပါသည်။ သိပ်သည်းမှုပြမြေပုံ ကိုအသုံးပြုခြင်းဖြင့် *hotspots (ထူးခြားဖြစ်ပျက်နေရာများ)* နှင့် point အစုအဖွဲ့ဖြစ်နေခြင်းများကို လွယ်ကူစွာရှာဖွေနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point layer**
     - ``INPUT``
     - [vector: point]
     - သိပ်သည်းမှုပြမြေပုံ အတွက်အသုံးပြုရန် point vector layer
   * - **Radius** (**အချင်းဝက်**)
     - ``RADIUS``
     - [number]

       Default: 100.0
     - Map ယူနစ်များဖြင့် သိပ်သည်းမှုပြမြေပုံ၏ ရှာဖွေမှု အချင်းဝက်အကျယ် (သို့မဟုတ် kernel band အကျယ်)။ အချင်းဝက်သည် point ၏လွှမ်းမိုးမှုကိုသိနိုင်သော point ပတ်ပတ်လည်အကွာအဝေးကို သတ်မှတ်ပေးပါသည်။ ဂဏန်းတန်ဖိုးပိုကြီးလေ ပိုပြီးချောမွေ့လေဖြစ်ပါသည်၊ သို့သော် ဂဏန်းတန်ဖိုးပိုသေးလျှင် ပိုကောင်းသော အသေးစိတ်မှုများနှင့် point သိပ်သည်းမှု ပြောင်းလဲခြင်းများကို ပြသနိုင်ပါသည်။
   * - **Output raster size** (**Output raster အရွယ်အစား**)
     - ``PIXEL_SIZE``
     - [number]

       Default: 0.1
     - Layer ယူနစ်များဖြင့် output raster ၏ pixel အရွယ်အစား။
   
       GUI ထဲတွင် row အရေအတွက် (``Number of rows``)/ column အရေအတွက် (``Number of columns``) **သို့မဟုတ်** pixel အရွယ်အစား ( ``Pixel Size X`` / ``Pixel Size Y``) တို့ဖြင့် အရွယ်အစားကို သတ်မှတ်နိုင်ပါသည်။ Row နှင့် column များအရေအတွက်ကိုပိုများအောင် လုပ်ခြင်းသည် cell အရွယ်အစားကိုလျော့ချပြီး output raster ၏ file အရွယ်အစားကို ကြီးလာစေပါသည်။ ``Rows``၊ ``Columns``၊ ``Pixel Size X`` နှင့် ``Pixel Size Y`` ထဲရှိတန်ဖိုးများကို တပြိုင်တည်း update လုပ်ဆောင်ပေးပါသည် - row အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ခြင်းသည် column အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ပေးပြီး cell အရွယ်အစားကို တစ်ဝက်လျှော့ချပေးပါသည်။ Output raster ၏ extent (အကျယ်အဝန်း) သည် မူရင်းအတိုင်း (ခန့်မှန်း) သာဆက်ရှိနေပါမည်။
   * - **Radius from field** (**Column မှ အချင်းဝက်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``RADIUS_FIELD``
     - [tablefield: numeric]
     - Input layer ၏ attribute column တစ်ခုမှ feature တစ်ခုချင်းစီအတွက် ရှာဖွေမည့် အချင်းဝက်ကိုသတ်မှတ်ပေးပါသည်။
   * - **Weight from field** (**Column မှ အလေးပေးမှု**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``WEIGHT_FIELD``
     - [tablefield: numeric]
     - Input feature များကို attribute field တစ်ခုဖြင့် အလေးပေးနိုင်အောင် လုပ်ဆောင်ပေးပါသည်။ ရလာဒ် သိပ်သည်းမှုပြမြေပုံပေါ်တွင် အချို့သော feature များလွှမ်းမိုးမှုကို မြှင့်တင်ရန် ၎င်းကိုအသုံးပြုနိုင်ပါသည်။
   * - **Kernel shape** (**Kernel ပုံသဏ္ဍာန်**)
     - ``KERNEL``
     - [enumeration]

       Default: *0*
     - Point တစ်ခုမှ အကွာအဝေး တိုးလာသည်နှင့် Point တစ်ခု၏ လွှမ်းမိုးမှုကျသွားသော နှုန်းကိုထိန်းချုပ်ပေးပါသည်။ Kernel အမျိုးမျိုးသည် မတူညီသောနှုန်းဖြင့် ပျက်စီးကြပါသည်။ ထို့ကြောင့် triweight kernel သည် point နှင့်အကွာအဝေးပိုနီးသော feature များကို ပိုအလေးပေးပါသည်။ ထို့နောက် Epanechnikov kernel ကိုလုပ်ဆောင်ပါသည်။ အကျိုးဆက်အားဖြင့် triweight သည် “ပိုမိုထင်ရှားသော” ထူးခြားဖြစ်ပျက်နေရာများ ကိုဖန်တီးပေးပြီး Epanechnikov သည် “ပိုမိုပြေပြစ်သော” ထူးခြားဖြစ်ပျက်နေရာများကိုဖန်တီးပေးပါသည်။
       
       အသုံးပြုနိုင်သော ပုံသဏ္ဍာန်များစွာရှိပါသည် (အခြားသတင်းအချက်အလက်များအတွက် `Wikipedia page <https://en.wikipedia.org/wiki/Kernel_(statistics)#Kernel_functions_in_common_use>`_ တွင်ကြည့်ပါ)

       * 0 --- Quartic
       * 1 --- Triangular
       * 2 --- Uniform
       * 3 --- Triweight
       * 4 --- Epanechnikov

   * - **Decay ratio (Triangular kernels only)** (**ပျက်စီးမှုအချိုး (Triangular kernel များသာ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``DECAY``
     - [number]

       Default: *0.0*
     - Feature မှ အကွာအဝေးကြောင့် feature တစ်ခုမှသိပ်သည်းမှု မည်သို့လျော့သွားသည်ကို အခြားထိန်းချုပ်မှုများလုပ်ဆောင်ရန် Triangular kernels ဖြင့်အသုံးပြုနိုင်ပါသည်။

	     * တန်ဖိုး 0 (=အနည်းဆုံး) ကိုအသုံးပြုလျှင် သိပ်သည်းမှုသည် အသုံးပြုထားသည့် အချင်းဝက်၏ အလယ်ဗဟိုတွင် များနေပြီး အစွန်ဘက်များတွင် လုံးဝမရှိတော့ပါ။
	     * တန်ဖိုး 0.5 ကိုအသုံးပြုလျှင် အချင်းဝက်၏အစွန်တွင်ရှိသော pixel များကို အချင်းဝက်၏အလယ်တွင်ရှိသော pixel များ၏ သိပ်သည်းမှု၏ တစ်ဝက်ကိုသာ အသုံးပြုပါမည်။
	     * တန်ဖိုး 1 ကိုအသုံးပြုလျှင် သိပ်သည်းမှုသည် ရှာဖွေမှုအချင်းဝက်စက်ဝိုင်းတစ်ခုလုံးတွင် ညီညီညာညာပြန့်နှံ့နေပါမည်။ ("Uniform" kernel နှင့် တူညီပါသည်)
	     * 1 ထက်ပိုကြီးသော တန်ဖိုးကိုအသုံးပြုလျှင် သိပ်သည်းမှုသည် ရှာဖွေမှုအချင်းဝက်၏အစွန်ဘက်များတွင် အလယ်ဗဟိုထက် ပိုများပါသည်။

   * - **Output value scaling** (**Output တန်ဖိုး စကေးချိန်ညှိခြင်း**)
     - ``OUTPUT_VALUE``
     - [enumeration]

       Default: *Raw*
     - Output သိပ်သည်းမှုပြမြေပုံ raster ၏တန်ဖိုးများကို ပြောင်းလဲနိုင်ပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Raw (အကြမ်း)
       * 1 --- Scaled (စကေးချိန်ညှိထားသော)

   * - **Heatmap** (**သိပ်သည်းမှုပြမြေပုံ**)
     - ``OUTPUT``
     - [raster]
       
       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Kernel သိပ်သည်းမှုတန်ဖိုးများပါဝင်သော output raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Heatmap**
     - ``OUTPUT``
     - [raster]
     - Kernel သိပ်သည်းမှုတန်ဖိုးများပါဝင်သော raster layer

ဥပမာ - သိပ်သည်းမှုပြမြေပုံတစ်ခု ဖန်တီးခြင်း
............................................

အောက်ပါ ဥပမာအတွက် QGIS နမူနာ dataset (:ref:`label_sampledata` တွင်ကြည့်ပါ) မှ ``airports`` vector point layer ကိုအသုံးပြုပါမည်။ သိပ်သည်းမှုပြမြေပုံများဖန်တီးခြင်းအတွက် အခြားအကောင်းဆုံး QGIS tutorial များကို `http://qgistutorials.com <http://www.qgistutorials.com/en/docs/creating_heatmaps.html>`_ တွင်တွေ့နိုင်ပါသည်။

:numref:`Figure_Heatmap_data_processing` ထဲတွင် Alaska ၏ လေဆိပ်များကိုပြသထားပါသည်။

.. _figure_heatmap_data_processing:

.. figure:: img/heatmap_start.png
   :align: center

   Alaska ၏ လေဆိပ်များ


#. QGIS :guilabel:`Interpolation` အုပ်စုမှ :guilabel:`Heatmap (Kernel Density Estimation)` algorithm ကိုဖွင့်ပါ။
#. :guilabel:`Point layer` |selectString| field ထဲတွင် လက်ရှိ project ထဲတွင် ထည့်သွင်းထားသော point layer များစာရင်းမှ ``airports`` ကို ရွေးချယ်ပါ။
#. :guilabel:`Radius` ကို ``1000000`` မီတာအဖြစ်ပြောင်းပါ။
#. :guilabel:`Pixel size X` ကို ``1000`` သို့ပြောင်းလဲပါ။ :guilabel:`Pixel size Y`၊ :guilabel:`Rows` နှင့် :guilabel:`Columns` များကိုအလိုအလျှောက် ပြောင်းလဲပေးပါလိမ့်မည်။
#. လေဆိပ်များ၏ သိပ်သည်းမှုပြမြေပုံကို ဖန်တီးပြီး ခေါ်ယူထည့်သွင်းရန် :guilabel:`Run` ကိုနှိပ်ပါ။ (:numref:`Figure_Heatmap_created_processing` တွင်ကြည့်ပါ)

.. _figure_heatmap_settings_processing:

.. figure:: img/heatmap_dialog.png
   :align: center

   သိပ်သည်းမှုပြမြေပုံ dialog

QGIS သည် သိပ်သည်းမှုပြမြေပုံကို ဖန်တီးပေးပြီး မြေပုံ ထဲတွင်ထည့်သွင်းပေးပါလိမ့်မည်။ သာမန်အားဖြင့် သိပ်သည်းမှုပြမြေပုံကို greyscale (မီးခိုးရောင်စကေး) ဖြင့်သာဖော်ပြနေပြီး အရောင်ဖျော့သောနေရာများသည် လေဆိပ်များ ပိုများနေသည်ကို ဆိုလိုပါသည်။ သိပ်သည်းမှုပြမြေပုံ၏အသွင်အပြင်ကို ပိုကောင်းအောင်လုပ်ဆောင်ရန် QGIS ထဲတွင် ပြင်ဆင်နိုင်ပါသည်။

.. _figure_heatmap_created_processing:

.. figure:: img/heatmap_loaded_grey.png
   :align: center

   ခေါ်ယူထည့်သွင်းပြီးနောက် သိပ်သည်းမှုပြမြေပုံသည် မီးခိုးရောင်မျက်နှာပြင်နှင့် တူနေပါသည်


#. ``heatmap_airports`` layer ၏ properties dialog ကိုဖွင့်ပါ  (``heatmap_airports`` ကိုရွေးချယ်ပါ၊ right-click နှိပ်ပြီး ပေါ်လာသော menu မှ :guilabel:`Properties` ကိုရွေးချယ်ပါ)။
#. :guilabel:`Symbology` tab ကိုရွေးချယ်ပါ။
#. :guilabel:`Render type (ပုံဖော်ပြသမှုအမျိုးအစား)` |selectString| ကို 'Singleband pseudocolor' သို့ပြောင်းပါ။
#. သင့်တော်သော :guilabel:`Color ramp (ရောင်စဉ်တန်း)` |selectString| တစ်ခုကိုရွေးချယ်ပါ၊ ဥပမာ- ``YlOrRd``။
#. :guilabel:`Classify` ခလုတ်ကိုနှိပ်ပါ။
#. Layer ကို ပုံစံအသစ်ဖြစ်စေရန် :guilabel:`OK` ကိုနှိပ်ပါ။

နောက်ဆုံးရလာဒ်ကို :numref:`Figure_Heatmap_styled_processing` ထဲတွင် ပြသပေးထားပါသည်။

.. _figure_heatmap_styled_processing:

.. figure:: img/heatmap_loaded_colour.png
   :align: center

   Alaska မှလေဆိပ်များ၏ အရောင်ခြယ်ထားသော သိပ်သည်းမှုပြမြေပုံ

.. _Wikipedia: https://en.wikipedia.org/wiki/Kernel_(statistics)#Kernel_functions_in_common_use

Python code
............

**Algorithm ID**: ``qgis:heatmapkerneldensityestimation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisidwinterpolation:

IDW Interpolation
------------------

Point vector layer တစ်ခု၏ Inverse Distance Weighted (IDW) interpolation တစ်ခုကို ထုတ်ပေးပါသည်။

ဖန်တီးလိုသော မသိ point တစ်ခုမှ အကွာအဝေးပေါ်မူတည်ပြီး တခြား point နှင့်ဆက်စပ်နေသာ point တစ်ခု၏လွှမ်းမိုးမှု ကျဆင်းသွားစေရန် interpolation လုပ်ဆောင်စဉ်တွင် နမူနာ point များကို အလေးပေးခြင်း (weight) ကို လုပ်ဆောင်ပါသည်။

IDW interpolation နည်းလမ်းသည်လည်း အားနည်းချက်အချို့ရှိပါသည် - နမူနာ point များ၏ ပြန့်နှံ့မှုမှာ မညီမညာ ဖြစ်နေလျှင် interpolation ရလာဒ်၏အရည်အသွေးသည် ကျဆင်းသွားနိုင်ပါသည်။

ထို့အပြင် interpolation ပြုလုပ်ထားသောမျက်နှာပြင်ထဲရှိ အများဆုံးနှင့် အနည်းဆုံးတန်ဖိုးများသည် နမူနာ data point များတွင်သာ တွေ့နိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer(s)** (**ထည့်သွင်းအသုံးပြုသော layer (များ)**)
     - ``INTERPOLATION_DATA``
     - [string]

     - String (စာသား) တစ်ခုထဲတွင် code လုပ်ထားသော interpolation အတွက် အသုံးပြုမည့် vector layer (များ) နှင့် field (များ) (ပိုမိုသိရှိလိုသည်များအတွက် :source:`InterpolationWidgets <python/plugins/processing/algs/qgis/ui/InterpolationWidgets.py>` ထဲရှိ ``ParameterInterpolationData`` class တွင် ကြည့်ရှုပါ)။
       အောက်ပါ GUI element များကို interpolation data စာသားများကို ရေးသားရာတွင် အသုံးပြုနိုင်ပါသည်-

       * **Vector layer** [vector: any]
       * **Interpolation attribute** [tablefield: numeric]-
         Interpolation တွင် အသုံးပြုမည့် attribute
       * **Use Z-coordinate for interpolation** [boolean]-
         Layer ၏ Z အမြင့်တန်ဖိုးများကို အသုံးပြုပါသည် (Default: False)

       ပေါင်းထည့်ထားသော layer-field ပေါင်းစပ်မှုတစ်ခုချင်းစီအတွက် အမျိုးအစားတစ်ခုကို ရွေးချယ်ပေးနိုင်ပါသည်-

       * :guilabel:`Points`
       * :guilabel:`Structured lines`
       * :guilabel:`Break lines`

       String (စာသား) ထဲတွင် layer-field element များကို ``'::|::'`` ဖြင့် ခွဲခြားထားပါသည်။ Layer-field element များ၏ element အခွဲများကို ``'::~::'`` ဖြင့် ခွဲခြားထားပါသည်။ 
   * - **Distance coefficient P** (**အကွာအဝေး ပြကိန်း P**)
     - ``DISTANCE_COEFFICIENT``
     - [number]

       Default: 2.0
     - Interpolation အတွက် အကွာအဝေး ပြကိန်း (coefficient) ကို သတ်မှတ်ပေးပါသည်။ အနည်းဆုံး- 0.0 ၊ အများဆုံး- 100.0  
   * - **Extent (xmin, xmax, ymin, ymax)**
     - ``EXTENT``
     - [extent]
     - Output raster layer ၏ နယ်ပယ်အကျယ်အဝန်း

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Output raster size** (**ရလာဒ် raster အရွယ်အစား**)
     - ``PIXEL_SIZE``
     - [number]

       Default: 0.1
     - Layer ယူနစ်များဖြင့် output raster ၏ pixel အရွယ်အစား။
   
 	     GUI ထဲတွင် row အရေအတွက် (``Number of rows``)/ column အရေအတွက် (``Number of columns``) **သို့မဟုတ်** pixel အရွယ်အစား ( ``Pixel Size X`` / ``Pixel Size Y``) တို့ဖြင့် အရွယ်အစားကို သတ်မှတ်နိုင်ပါသည်။ Row နှင့် column များအရေအတွက်ကိုပိုများအောင် လုပ်ခြင်းသည် cell အရွယ်အစားကိုလျှော့ချပြီး output raster ၏ file အရွယ်အစားကို ကြီးလာစေပါသည်။ ``Rows``၊ ``Columns``၊ ``Pixel Size X`` နှင့် ``Pixel Size Y`` ထဲရှိတန်ဖိုးများကို တပြိုင်တည်း update လုပ်ဆောင်ပေးပါသည် - row အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ခြင်းသည် column အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ပေးပြီး cell အရွယ်အစားကို တစ်ဝက်လျှော့ချပေးပါသည်။ Output raster ၏ extent (နယ်ပယ်အကျယ်အဝန်း) သည် မူရင်းအတိုင်း (ခန့်မှန်း) သာဆက်ရှိနေပါမည်။
   * - **Interpolated** (**Interpolation ပြုလုပ်ထားသော**)
     - ``OUTPUT``
     - [raster]
       
       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Interpolation ပြုလုပ်ထားသော တန်ဖိုးများ၏ raster layer ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated**
     - ``OUTPUT``
     - [raster]
     - Interpolation ပြုလုပ်ထားသော တန်ဖိုးများ၏ raster layer

Python code
............

**Algorithm ID**: ``qgis:idwinterpolation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgislinedensity:

Line Density (မျဉ်း သိပ်သည်းမှု)
---------------------------------

Raster cell တစ်ခုချင်းစီအတွက် စက်ဝိုင်းပုံစံ neighbourhood (အနီးဝန်းကျင်မှအရာများ) တစ်ခုအတွင်းရှိ မျဉ်း feature များ၏ သိပ်သည်းမှုအတိုင်းအတာကို တွက်ချက်ပေးပါသည်။ စက်ဝိုင်းပုံစံ neighbourhood နှင့်ထိဖြတ်နေသော line segment (အပိုင်း) များအားလုံးကို ပေါင်းပြီး ၎င်းပေါင်းလာဒ်ကို ထို စက်ဝိုင်းပုံစံ neighbourhood ၏ ဧရိယာဖြင့် စားခြင်းဖြင့် ဒီအတိုင်းအတာကို ရရှိပါသည်။ အလေးပေးမှုတန်ဖိုးတစ်ခုကို line အပိုင်းများတွင် အသုံးပြုနိုင်ပါသည်။

.. figure:: img/linedensity.png
  :align: center
  
  Line သိပ်သည်းမှု ဥပမာ။ ထည့်သွင်းအသုံးပြုသော layer ရင်းမြစ်- Roads Overijssel - The Netherlands (OSM)


Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input line layer** (**ထည့်သွင်းအသုံးပြုသော line layer**)
     - ``INPUT``
     - [vector: any]
     - Line feature များပါဝင်သော input vector layer
   * - **Weight field** (**အလေးပေးမှု column**)
     - ``WEIGHT``
     - [number]

     - တွက်ချက်စဉ်တွင် အသုံးပြုမည့် အလေးပေး factor ပါဝင်သော layer ၏ column
   * - **Search Radius** (**ရှာဖွေသော အချင်းဝက်**)
     - ``RADIUS``
     - [number]

       Default: 10
     - စက်ဝိုင်းပုံစံ neighbourhood ၏အချင်းဝက် ။ ယူနစ်များကို ဒီနေရာတွင် သတ်မှတ်နိုင်ပါသည်။ 
   * - **Pixel size** (**Pixel အရွယ်အစား**)
     - ``PIXEL_SIZE``
     - [number]

       Default: 10
     - Layer ယူနစ်များဖြင့် output raster layer ၏ pixel အရွယ်အစား။ Raster တွင် စတုရန်းပုံစံ pixel များရှိပါသည်။
   * - **Line density raster** (**Line သိပ်သည်းမှု raster**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Raster layer တစ်ခုအဖြစ် output ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Line density raster** (**Line သိပ်သည်းမှု raster**)
     - ``OUTPUT``
     - [raster]
     - Line သိပ်သည်းမှု output raster layer

Python code
............

**Algorithm ID**: ``native:linedensity``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgistininterpolation:

TIN Interpolation
------------------

Point vector layer တစ်ခု၏ Triangulated Irregular Network (TIN) interpolation တစ်ခုကို ထုတ်ပေးပါသည်။

TIN နည်းလမ်းကိုအသုံးပြုပြီး အနီးဆုံး point များ၏ တြိဂံများဖြင့်ဖန်တီးထားသော မျက်နှာပြင်တစ်ခုကို ဖန်တီးနိုင်ပါသည်။ ထို့သို့ပြုလုပ်ရန်အတွက် ရွေးချယ်ထားသော နမူနာ point များပတ်လည်တွင် ဝန်းထိစက်ဝိုင်းများကို ဖန်တီးပြီး ၎င်းတို့အချင်းချင်းဖြတ်သောနေရာများကို မထပ်သော ကွန်ရက်တစ်ခုအဖြစ် ဆက်သွယ်လိုက်ပြီး တတ်နိုင်သမျှ တြိဂံများကို သိပ်သည်းနေအောင် လုပ်ဆောင်ပေးပါသည်။ ရလာသော မျက်နှာပြင်များသည် ချောမွေ့နေမည်မဟုတ်ပါ။

Interpolation ပြုလုပ်ထားသောတန်ဖိုးများ၏ raster layer နှင့် triangulation နယ်နိမိတ်များပါဝင်သော vector line layer နှစ်ခုလုံးကို Algorithm မှဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer(s)** (**ထည့်သွင်းအသုံးပြုသော layer (များ)**)
     - ``INTERPOLATION_DATA``
     - [string]
     - String (စာသား) တစ်ခုထဲတွင် code လုပ်ထားသော interpolation အတွက် အသုံးပြုမည့် vector layer (များ) နှင့် field (များ) (ပိုမိုသိရှိလိုသည်များအတွက် :source:`InterpolationWidgets <python/plugins/processing/algs/qgis/ui/InterpolationWidgets.py>` ထဲရှိ ``ParameterInterpolationData`` class တွင် ကြည့်ရှုပါ)။

       အောက်ပါ GUI element များကို interpolation data စာသားများကို ရေးသားရာတွင် အသုံးပြုနိုင်ပါသည်-

       * **Vector layer** [vector: any]
       * **Interpolation attribute** [tablefield: numeric]-
         Interpolation တွင် အသုံးပြုမည့် attribute
       * **Use Z-coordinate for interpolation** [boolean]-
         Layer ၏ Z အမြင့်တန်ဖိုးများကို အသုံးပြုပါသည် (Default: False)

       ပေါင်းထည့်ထားသော layer-field ပေါင်းစပ်မှုတစ်ခုချင်းစီအတွက် အမျိုးအစားတစ်ခုကို ရွေးချယ်ပေးနိုင်ပါသည်-

       * :guilabel:`Points`
       * :guilabel:`Structured lines`
       * :guilabel:`Break lines`

       String (စာသား) ထဲတွင် layer-field element များကို ``'::|::'`` ဖြင့် ခွဲခြားထားပါသည်။ Layer-field element များ၏ element အခွဲများကို ``'::~::'`` ဖြင့် ခွဲခြားထားပါသည်။
   * - **Interpolation method** (**Interpolation နည်းလမ်း**)
     - ``METHOD``
     - [enumeration]

       Default: 0
     - အသုံးပြုမည့် interpolation နည်းလမ်းကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -
       
       * :guilabel:`Linear`
       * :guilabel:`Clough-Toucher (cubic)`
     
   * - **Extent (xmin, xmax, ymin, ymax)**
     - ``EXTENT``
     - [extent]

     - Output raster layer ၏ နယ်ပယ်အကျယ်အဝန်း

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Output raster size** (**Output raster အရွယ်အစား**)
     - ``PIXEL_SIZE``
     - [number]

       Default: 0.1
     - Layer ယူနစ်များဖြင့် output raster ၏ pixel အရွယ်အစား။ GUI ထဲတွင် row အရေအတွက် (``Number of rows``)/ column အရေအတွက် (``Number of columns``) **သို့မဟုတ်** pixel အရွယ်အစား ( ``Pixel Size X`` / ``Pixel Size Y``) တို့ဖြင့် အရွယ်အစားကို သတ်မှတ်နိုင်ပါသည်။ Row နှင့် column များအရေအတွက်ကိုပိုများအောင် လုပ်ခြင်းသည် cell အရွယ်အစားကိုလျှော့ချပြီး output raster ၏ file အရွယ်အစားကို ကြီးလာစေပါသည်။ ``Rows``၊ ``Columns``၊ ``Pixel Size X`` နှင့် ``Pixel Size Y`` ထဲရှိတန်ဖိုးများကို တပြိုင်တည်း update လုပ်ဆောင်ပေးပါသည် - row အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ခြင်းသည် column အရေအတွက်ကို နှစ်ဆတိုးမြှင့်ပေးပြီး cell အရွယ်အစားကို တစ်ဝက်လျှော့ချပေးပါသည်။ Output raster ၏ extent (နယ်ပယ်အကျယ်အဝန်း) သည် မူရင်းအတိုင်း (ခန့်မှန်း) သာဆက်ရှိနေပါမည်။   
   * - **Interpolated** (**Interpolation ပြုလုပ်ထားသော**)
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file] ([ယာယီ file ထဲတွင်သိမ်းဆည်းပါ])``
     - Raster layer တစ်ခုအဖြစ် TIN interpolation output ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**
   * - **Triangulation** (**တြိဂံဖွဲ့တွက်ထုတ်ခြင်း**)
     - ``TRIANGULATION``
     - [vector: line]

       Default: ``[Skip output]``
     - Vector layer တစ်ခုအဖြစ် output TIN ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Interpolated** (**Interpolation ပြုလုပ်ထားသော**)
     - ``OUTPUT``
     - [raster]
     - Raster layer တစ်ခုအဖြစ် TIN interpolation output 
   * - **Triangulation** (**တြိဂံဖွဲ့တွက်ထုတ်ခြင်း**)
     - ``TRIANGULATION``
     - [vector: line]
     - Vector layer တစ်ခုအဖြစ် TIN output

Python code
............

**Algorithm ID**: ``qgis:tininterpolation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |selectString| image:: /static/common/selectstring.png
   :width: 2.5em
