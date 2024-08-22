Raster terrain analysis (Raster မြေမျက်နှာသွင်ပြင်ဆိုင်ရာ ဆန်းစစ်လေ့လာခြင်း)
=============================================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisaspect:

Aspect (မျက်နှာမူရာအရပ်)
-------------------------

ထည့်သွင်းထားသော Digital Terrain Model ၏ aspect (မျက်နှာမူရာအရပ်) ကို တွက်ချက်ပေးပါသည်။ ရရှိလာသည့် aspect raster layer တွင် လျှောစောက်လားရာ (slope direction) ကို မြောက်ဘက် (0°) မှစပြီး နာရီလက်တံအတိုင်း 0 မှ 360 အထိ ဖော်ပြနိုင်သည့် တန်ဖိုးများပါဝင်ပါသည်။ 


.. figure:: img/aspect.png
   :align: center
   :scale: 50%

   Aspect တန်ဖိုးများ

အောက်ဖော်ပြပါပုံသည် color ramp (ရောင်စဉ်တန်း) တစ်ခုဖြင့် အတန်းအစား သို့မဟုတ် အမျိုးအစားခွဲခြားခြင်း(reclassified) ပြုလုပ်ထားသော aspect layer တစ်ခုကို ပြသပါသည်-


.. figure:: img/aspect_2.png
   :align: center

   အတန်းအစား သို့မဟုတ် အမျိုးအစားခွဲခြားထားသည့် Aspect layer

Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Elevation layer**  **(မြေပြင်အမြင့် layer)**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Z factor**
     - ``Z_FACTOR``
     - [number]

       Default: 1.0
     - Vertical exaggeration (ဒေါင်လိုက်ချဲ့ကားခြင်း)။ Z ယူနစ်များသည် X နှင့် Y ယူနစ်များမှ ကွဲပြားခြားနားနေသည့်အခါတွင် ဤ သတ်မှတ်ချက် (parameter) သည် အသုံးဝင်ပါသည်၊ ဥပမာ- ပေ နှင့် မီတာများ။  ဤ သတ်မှတ်ချက်ကို ၎င်းအတွက် ချိန်ညှိရန် အသုံးပြုနိုင်ပါသည်။ Default အားဖြင့် 1 ဖြစ်ပါသည်။ (no exaggeration (ချဲ့ကားထားခြင်းမရှိပါ))
   * - **Aspect**
     - ``OUTPUT``
     - [raster]

       Default: ``[Save to temporary file]``
     - Output aspect raster layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှတစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Aspect**
     - ``OUTPUT``
     - [raster]
     - Output aspect raster layer

Python code
............

**Algorithm ID**: ``qgis:aspect``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdtmslopebasedfilter:

DTM filter (slope-based) (DTM စစ်ထုတ်မှု (လျှောစောက်အခြေပြု))
--------------------------------------------------------------

|334|

Digital elevation model (DEM) တစ်ခုအား ၎င်း၏ cell များကို မြေပြင် နှင့် အရာဝတ္ထုများ (မြေပြင်မဟုတ်သည့်) cell များအဖြစ်သို့ အတန်းအစားခွဲခြင်း (classify) ပြုလုပ်နိုင်ရန်အတွက် စစ်ထုတ် (filter) ရာတွင် အသုံးပြုနိုင်ပါသည်။

ဤ tool သည် Vosselman (2000) မှ ဖော်ပြထားသည့် သဘောတရားများ (concepts) ကို အသုံးပြုပြီး ၎င်းသည် အနီးအနားရှိ cell နှစ်ခုအကြားရှိ ကြီးမားသည့် အမြင့်ကွာခြားချက်တစ်ခုသည် မြေမျက်နှာသွင်ပြင် (terrain) ထဲရှိ မတ်စောက်သည့် လျှောစောက်တစ်ခုကြောင့် ဖြစ်ရန်အလားအလာမရှိပါဆိုသည့် ယူဆချက်အပေါ်တွင် အခြေခံပါသည်။ Cell နှစ်ခုအကြားရှိ အကွာအဝေးသည် ကျဆင်းလာသည့်အခါတွင် မြင့်မားသော cell သည် non-ground (မြေပြင်မဟုတ်သည့်) ဖြစ်နိုင်ချေမှာ တိုးလာမည်ဖြစ်သည်။
ထို့အတွက်ကြောင့် filter (စစ်ထုတ်မှု) သည် cell နှစ်ခုအကြားရှိ အမြင့်ဆုံး အမြင့်ကွာခြားချက် (``dz_max``)  တစ်ခုကို cell များအကြား (``dz_max( d ) = d``) အကွာအဝေး (``d``) ၏ function တစ်ခုအဖြစ် သတ်မှတ်ပါသည်။
အကယ်၍ kernel radius (အချင်းဝက်) အတွင်းတွင် မည်သည့် cell မျှမရှိပါက cell တစ်ခုကို terrain(မြေမျက်နှာသွင်ပြင်) အဖြစ် ခွဲခြားသတ်မှတ်ပါသည်။ ၎င်းတွင် အမြင့်ကွာခြားချက်သည် ထို cell နှစ်ခုအကြား အကွာအဝေး၌ရှိသည့် ခွင့်ပြုထားသော အများဆုံး အမြင့်ကွာခြားချက်ထက် ကြီးမားပါသည်။

လေ့လာမည့်ဧရိယာထဲရှိ overall slope (ခြုံငုံထားသည့်လျှောစောက်) နှင့် ကိုက်ညီမှုရှိစေရေး filter(စစ်ထုတ်မှု) function ကို ပြင်ဆင်မွမ်းမံခြင်း (modify) ပြုလုပ်ရန်အတွက် approximate terrain slope (ခန့်မှန်းမြေမျက်နှာသွင်ပြင်လျှောစောက်) (``s``) parameter ကို အသုံးပြုပါသည် (``dz_max( d ) = d * s``)။

5 % confidence interval (``ci = 1.65 * sqrt( 2 * stddev )``) တစ်ခုကို စစ်ထုတ်မှုစံနှုန်း (filter criterium) အား ဖြေလျော့ခြင်း (relaxing) (``dz_max( d ) = d * s + ci``)  ဖြင့် သို့မဟုတ် တိုးချဲ့ခြင်း (amplifying) (``dz_max( d ) = d * s - ci``) ဖြင့် filter (စစ်ထုတ်မှု) function ကို နောက်ထပ် ပြင်ဆင်မွမ်းမံခြင်း (modify) ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။

*ကိုးကားချက်: Vosselman, G. (2000): laser altimetry data ၏ Slope based filtering of laser altimetry data. IAPRS, Vol. XXXIII, Part B3, Amsterdam, The Netherlands, 935-942*

.. seealso:: ဤ tool သည် SAGA `DTM Filter (slope-based) <https://saga-gis.sourceforge.io/saga_tool_doc/9.1.1/grid_filter_7.html>`_ ၏ port တစ်ခုဖြစ်ပါသည် _


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသည့် layer)**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Band number** **(Band နံပါတ်)**
     - ``BAND``
     - [number] [list]
     - ထည့်သွင်းစဉ်းစားမည့် DEM ၏ band
   * - **Kernel radius (အချင်းဝက်) (pixels)**
     - ``RADIUS``
     - [number]

       Default: 5
     - Filter kernel ၏ အချင်းဝက် (pixels များဖြင့်)။ မြေပြင်မဟုတ်သည့် အရာဝတ္ထုများ (non-ground objects) ဘေးသို့ ground cells များရောက်ရှိနိုင်ရန်အတွက် လုံလောက်အောင်ကြီးမားရမည်ဖြစ်သည်။
   * - **Terrain slope (% ၊ pixel အရွယ်အစား/vertical ယူနစ်များ)**
     - ``TERRAIN_SLOPE``
     - [number]

       Default: 30
     - ``%`` ဖြင့် approximate terrain slope (ခန့်မှန်းမြေပြင်လျှောစောက်)။ အမြင့်ယူနစ်များနှင့် raster pixel dimension များ၏ အချိုးအတွက် မြေမျက်နှာသွင်ပြင်လျှောစောက်ကို ချိန်ညှိခြင်းပြုလုပ်ရမည်ဖြစ်ပါသည်။ မတ်စောက်သောမြေမျက်နှာသွင်ပြင်တွင် စစ်ထုတ်မှုဆိုင်ရာသတ်မှတ်ချက် (filter criterium) ကို (relax) ဖြေလျှော့လေ့ရှိပါသည်။ 
   * - **Filter modification** **(စစ်ထုတ်မှုဆိုင်ရာပြင်ဆင်မွမ်းမံခြင်း)**
     - ``FILTER_MODIFICATION``
     - [list]

       Default: 0
     - ပြင်ဆင်မွမ်းမံခြင်းများမပါဝင်ဘဲ filter kernel ကို အသုံးချမည်လား သို့မဟုတ် အမြင့်ဆိုင်ရာသတ်မှတ်ချက် (height criterium) ကို ဖြေလျှော့ခြင်း (relax) သို့မဟုတ် တိုးချဲ့ခြင်း(amplify) အတွက် confidence interval တစ်ခုကို အသုံးပြုမည်လား ဆိုသည်ကို ရွေးချယ်ပါ။

       * 0 - None
       * 1 - Relax filter (စစ်ထုတ်မှုကို ဖြေလျော့သည်)
       * 2 - Amplify (တိုးချဲ့သည်)
   * - **Standard deviation** **(စံတိမ်းချက်)**
     - ``STANDARD_DEVIATION``
     - [number]

       Default: 0.1
     - Height threshold (အမြင့်သတ်မှတ်ချက်) သို့ သက်ရောက်ထားသော 5% confidence interval တစ်ခုကို တွက်ချက်ရန် Standard deviation (စံတိမ်းချက်) ကိုအသုံးပြုပါသည်။
   * - **Output layer (ground)** **(ရလာဒ် layer (မြေပြင်))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT_GROUND``
     - [raster]

       Default : ``[Save to temporary file]``
     - Ground (မြေပြင်) အဖြစ် ခွဲခြားသတ်မှတ်ထားသည့် cell များသာပါဝင်သော စစ်ထုတ်ထားသည့် မြေပြင်အမြင့်ပြဒေတာ (DEM) ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

   * - **Output layer (non-ground objects)** **(ရလာဒ် layer (မြေပြင်မဟုတ်သည့်အရာဝတ္ထုများ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT_NONGROUND``
     - [raster]

       Default: ``[Skip output]``
     - စစ်ထုတ်မှု (filter) ဖြင့် ဖယ်ရှားထားသည့် မြေပြင်မဟုတ်သော အရာဝတ္ထုများ (non-ground objects)များကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output layer (ground)**
     - ``OUTPUT_GROUND``
     - [raster]
     - Ground (မြေပြင်) အဖြစ် ခွဲခြားသတ်မှတ်ထားသည့် cell များသာပါဝင်သော စစ်ထုတ်ထားသည့် မြေပြင်အမြင့်ပြဒေတာ (DEM)
   * - **Output layer (non-ground objects)**
     - ``OUTPUT_NONGROUND``
     - [raster]
     - စစ်ထုတ်မှု (filter) ဖြင့် ဖယ်ရှားထားသည့် မြေပြင်မဟုတ်သော အရာဝတ္ထုများ (non-ground objects)

Python code
............

**Algorithm ID**: ``native:dtmslopebasedfilter``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgishillshade:

Hillshade (တောင်အရိပ်)
-----------------------

ထည့်သွင်းထားသည့် Digital Terrain Model တစ်ခုမှ hillshade raster layer ကိုတွက်ချက်ပေးပါသည်။

Layer ၏ အရိပ်ချမှု (shading) ကို နေ၏ တည်နေရာပေါ်မူတည်၍ တွက်ချက်ပါသည်- နေ၏ horizontal angle(ရေပြင်ညီထောင့်) (azimuth) နှင့် vertical angle (ဒေါင်လိုက်ထောင့်) (နေအမြင့်) နှစ်ခုလုံးကို ပြောင်းလဲမှုပြုလုပ်ရန် ရွေးချယ်စရာများရှိပါသည်။


.. figure:: img/azimuth.png
   :align: center
   :scale: 50%

   Azimuth နှင့် vertical angle

Hillshade layer တွင် တန်ဖိုးများအနေဖြင့် 0 (အရိပ်အပြည့်အဝ) မှ 255 (နေအပြည့်အဝ) ထိ ပါဝင်ပါသည်။ များသောအားဖြင့် Hillshade ကို ဧရိယာတစ်ခု၏ အနိမ့်အမြင့် (relief) ကို ပိုမိုသဘောပေါက်နားလည်စေရန် အသုံးပြုပါသည်။

.. figure:: img/hillshade.png
   :align: center

   Azimuth 300 နှင့် vertical angle 45 ရှိသည့် Hillshade layer 

စိတ်ဝင်စားဖွယ်အချက်တစ်ခုမှာ hillshade layer ကို ဖောက်ထွင်းမြင်နိုင်သည့်တန်ဖိုး (transparency value) တစ်ခုပေးပြီး ၎င်းအား elevation raster နှင့် ထပ်ပေး (Overlap) ခြင်းဖြစ်ပါသည်-

.. figure:: img/hillshade_2.png
   :align: center

   Hillshade အား elevation layer နှင့်ထပ်ခြင်း


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Elevation layer**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Z factor**
     - ``Z_FACTOR``
     - [number]
       Default: 1.0
     - Vertical exaggeration (ဒေါင်လိုက် ချဲ့ကားခြင်း)။ ဤ parameter သည် Z ယူနစ်များသည် X နှင့် Y ယူနစ်များမှ ကွာခြားနေသည့်အခါတွင် အသုံးဝင်ပါသည်၊ ဥပမာ- ပေ နှင့် မီတာများ။ ဤ parameter ကို ၎င်းအား ချိန်ညှိခြင်း ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။ ဤ parameter ၏ တန်ဖိုးကို တိုးမြှင့်ခြင်းသည် နောက်ဆုံးရရှိလာမည့်ရလာဒ်ကို ပိုမိုချဲ့ကား (exaggerate) စေမည်ဖြစ်သည် (၎င်းကို ပို၍ "hilly (တောင်ထူထပ်သော)" ပုံစံဖြစ်ပေါ်စေခြင်း)။ Default အားဖြင့် 1 ဖြစ်ပါသည် (ချဲ့ကားထားခြင်း (exaggeration) မရှိပါ)။

   * - **Azimuth (horizontal angle)** **Azimuth (ရေပြင်ညီထောင့်)**
     - ``AZIMUTH``
     - [number]

       Default: 300.0
     - နေ၏ horizontal angle ရေပြင်ညီထောင့် (ဒီဂရီများဖြင့်) (နာရီလက်တံလှည့်သည့်အတိုင်း) ကိုသတ်မှတ်ပါ။ အပိုင်းအခြားပမာဏ- 0 မှ 360 ။ 0 သည် မြောက်ဘက်ဖြစ်ပါသည်။
   * - **Vertical angle** **(ဒေါင်လိုက်ထောင့်)**
     - ``V_ANGLE``
     - [number]

       Default : 40.0
     - နေ၏ vertical angle (ဒီဂရီများဖြင့်) များဖြင့်သတ်မှတ်ပါ။ ၎င်းသည် နေ၏ အမြင့်ဖြစ်ပါသည်။ တန်ဖိုးများသည် 0 (အနည်းဆုံး အမြင့်) မှ 90 (အများဆုံး အမြင့်) ထိ ဖြစ်ပါသည်။ 
   * - **Hillshade**
     - ``OUTPUT``
     - [raster]

       Default : ``[Save to temporary file]``
     - ရရှိလာသည့် hillshade raster layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလဒ်များ)
...................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Hillshade**
     - ``OUTPUT``
     - [raster]
     - Output hillshade raster layer

Python code
............

**Algorithm ID**: ``qgis:hillshade``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgishypsometriccurves:

Hypsometric curves (Elevation နှင့် ဧရိယာဆက်နွယ်မှုကို ပြသသော မျဉ်းကွေး)
-------------------------------------------------------------------------

ထည့်သွင်းထားသည့် Digital Elevation Model တစ်ခုအတွက် Hypsometric curve (Elevation နှင့် ဧရိယာဆက်နွယ်မှုကို ပြသသော မျဉ်းကွေး) များကို တွက်ချက်ပေးပါသည်။ မျဉ်းကွေးများ (Curves) ကို အသုံးပြုသူ (user) မှ သတ်မှတ်ထားခဲ့သော output folder တစ်ခုထဲတွင် CSV file များအဖြစ် ထုတ်ပေးပါသည်။

Hypsometric curve တစ်ခုသည် ပထဝီဝင်ဧရိယာတစ်ခုထဲရှိ အမြင့်တန်ဖိုးများ၏ cumulative histogram (စုပုံတိုးပွားလာသော ဟစ်စတိုဂရမ်) တစ်ခုဖြစ်ပါသည်။

Hypsometric curve များကို နယ်မြေဒေသ (territory) ၏ geomorphology (landforms နှင့် landform evolution ကို လေ့လာသည့်ပညာရပ်) ကြောင့် landscape တွင် မတူကွဲပြားသည်များကို ရှာဖွေတွေ့ရှိရန် အသုံးပြုနိုင်ပါသည်။


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **DEM to analyze** **(ခွဲခြမ်းစိတ်ဖြာမှုပြုလုပ်မည့် DEM)**
     - ``INPUT_DEM``
     - [raster]
     - Altitudes (အမြင့်) များကို တွက်ချက်ခြင်းအတွက် အသုံးပြုမည့် Digital Terrain Model raster layer
   * - **Boundary layer** **(နယ်နိမိတ် layer)**
     - ``BOUNDARY_LAYER``
     - [vector: polygon]
     - Hypsometric curve များကို တွက်ချက်ရန်အသုံးပြုမည့် ဧရိယာများ၏ နယ်နိမိတ်များပါရှိသည့် Polygon vector layer

   * - **Step**
     - ``STEP``
     - [number] [နံပါတ်]

       Default: 100.0
     - Curve (မျဉ်းကွေး) များအကြားရှိ ဒေါင်လိုက်အကွာအဝေး
   * - **Use % of area instead of absolute value** **(ပကတိတန်ဖိုးအစား ဧရိယာ၏ % ကို သုံးပါ)**
     - ``USE_PERCENTAGE``
     - [boolean]

       Default : False
     - CSV file ၏ “Area (ဧရိယာ)” field တွင် absolute (ပကတိ) ဧရိယာအစား ဧရိယာရာခိုင်နှုန်း (area percentage) ကိုရေးသွင်းပါ။
   * - **Hypsometric curves**
     - ``OUTPUT_DIRECTORY``
     - [folder]
     - Hypsometric curve များအတွက် output folder ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှတစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **directory_output_types**
          :end-before: **end_directory_output_types**
    
Outputs (ရလဒ်များ)
...................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Hypsometric curves**
     - ``OUTPUT_DIRECTORY``
     - [folder]
     - Hypsometric curve များရှိသော ဖိုင်များပါဝင်သည့် Directory(လမ်းကြောင်း)။ ထည့်သွင်းထားသော vector layer မှ feature တစ်ခုချင်းစီအတွက် ဧရိယာနှင့် altitude (အမြင့်) တန်ဖိုးများပါရှိသည့် CSV file တစ်ခုကို ဖန်တီးပေးမည်ဖြစ်ပါသည်။ 

       ဖိုင်အမည်များသည် ``histogram_`` ဖြင့်စပြီး နောက်တွင် layer name နှင့် feature ID များပါရှိပါသည်။

.. figure:: img/hypsometric.png
   :align: center
   :scale: 50%

Python code
............

**Algorithm ID**: ``qgis:hypsometriccurves``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrelief:

Relief (အနိမ့်အမြင့်ထင်ရှားမှု)
--------------------------------

Digital elevation data (အမြင့်ပြဒေတာ) မှ အနိမ့်အမြင့်ထင်ရှားစေရန်အရိပ်ချထားသည့် layer (shaded relief layer) တစ်ခုကို ဖန်တီးပေးပါသည်။ Relief color (အနိမ့်အမြင့်ထင်ရှားမှုပြအရောင်) ကို ကိုယ်တိုင် သတ်မှတ်နိုင်ပါသည် သို့မဟုတ် relief classes (အနိမ့်အမြင့်ထင်ရှားမှုဆိုင်ရာအတန်းအစားများ) အားလုံးကို အလိုအလျောက် ရွေးချယ်စေရန် algorithm ကို ခွင့်ပြုပေးနိုင်ပါသည်။

.. figure:: img/relief.png
   :align: center

   အနိမ့်အမြင့်ပြ (Relief) layer


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Elevation layer**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Z factor**
     - ``Z_FACTORZ factor``
     - [number]

       Default: 1.0
     - Vertical exaggeration (ဒေါင်လိုက်ချဲ့ကားခြင်း)။ ဤ parameter သည် Z ယူနစ်များသည် X နှင့် Y ယူနစ်များမှ ကွာခြားနေပါက အသုံးဝင်ပါသည်။ ဥပမာ- ပေ နှင့် မီတာများ။ ဤ parameter ကို ၎င်းအား ချိန်ညှိခြင်း ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။ ဤ parameter ၏ တန်ဖိုးကို တိုးမြှင့်ခြင်းသည် နောက်ဆုံးရရှိလာမည့်ရလာဒ်ကို ပိုမိုချဲ့ကား (exaggerate) စေမည်ဖြစ်သည် (၎င်းကို ပို၍ "hilly (တောင်ထူထပ်သော)" ပုံစံဖြစ်ပေါ်စေခြင်း)။ Default အားဖြင့် 1 ဖြစ်ပါသည် (ချဲ့ကားထားခြင်း (exaggeration) မရှိပါ)။
   * - **Generate relief classes automatically** **(အနိမ့်အမြင့်အဆင့်အတန်းများကို အလိုအလျောက် ထုတ်လုပ်ပေးခြင်း)** 
     - ``AUTO_COLORS``
     - [boolean]

       Default: False
     - အကယ်၍ ဤ option ကို အမှန်ခြစ် ပြုလုပ်ထားပါက algorithm သည် relief classes (အနိမ့်အမြင့်ထင်ရှားမှုဆိုင်ရာအဆင့်အတန်းများ) အားလုံးကို အလိုအလျောက် ထုတ်လုပ်ပေးမည်ဖြစ်ပါသည်။
   * - **Relief colors** **(အနိမ့်အမြင်ထင်ရှားမှုပြ အရောင်များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``COLORS``
     - [table widget]
     - အကယ်၍ Relief colors (အနိမ့်အမြင်ထင်ရှားမှုပြ အရောင်များ) များကို ကိုယ်တိုင် ရွေးချယ်လိုပါက table widget ကို အသုံးပြုပါ။ အလိုရှိသလောက် အရောင်အတန်းအစားများ (color classes) ကို ကိုယ်တိုင် ထည့်သွင်းနိုင်ပါသည်။ အတန်းအစားတစ်ခုချင်းစီအတွက် lower (အနိမ့်) နှင့် upper (အမြင့်) bound (အကန့်အသတ်) ကို ရွေးချယ်နိုင်ပြီး နောက်ဆုံး၌ color widget ဖြင့် အရောင်ဇယားတန်းပေါ်တွင် click ပြုလုပ်ခြင်းဖြင့် အရောင်ကို ရွေးချယ်နိုင်ပါသည်။

       .. figure:: img/relief_table.png
          :align: center

          အနိမ့်အမြင်ထင်ရှားမှုပြ အရောင်အတန်းအစားများကို ကိုယ်တိုင်သတ်မှတ်ခြင်း

       ညာဘက် side panel ထဲရှိ ခလုတ်များသည် အရောင်အတန်းအစားများ (color classes) ထပ်မံထည့်သွင်းခြင်း သို့မဟုတ် ဖယ်ရှားခြင်း၊ သတ်မှတ်ထားပြီးဖြစ်သော အရောင်အတန်းအစားများ၏ အစဉ် (order) ကိုပြောင်းလဲခြင်း၊ အရောင်အတန်းအစားများပါရှိသည့် ရှိပြီးသားဖိုင်တစ်ခုကို ဖွင့်ခြင်းနှင့် လက်ရှိ အတန်းအစားများကို ဖိုင်အဖြစ် သိမ်းဆည်းခြင်း တို့ကိုဆောင်ရွက်ခွင့်ပေးပါသည်။

   * - **Relief**
     - ``OUTPUT``
     - [raster]
       
       Default : ``[Save to temporary file]``
     - Output relief raster layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

   * - **Frequency distribution** **(ကြိမ်နှုန်းဖြန့်ကျက်မှု)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FREQUENCY_DISTRIBUTION``
     - [table]
       
       Default: ``[Skip output]``
     - Output frequency distribution အတွက် CSV ဇယားတစ်ခုကို သတ်မှတ်ပါ။ အောက်ပါထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**


Outputs (ရလဒ်များ)
...................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Relief**
     - ``OUTPUT``
     - [raster]
     - Output relief raster layer
   * - **Frequency distribution** **(ကြိမ်နှုန်းဖြန့်ကျက်မှု)**
     - ``OUTPUT``
     - [table]
     - Output frequency distribution (ကြိမ်နှုန်းဖြန့်ကျက်မှု)

Python code
............

**Algorithm ID**: ``qgis:relief``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisruggednessindex:


Ruggedness index (မြေမျက်နှာပြင်မညီညာမှုပြ အညွှန်းကိန်း)
---------------------------------------------------------

Riley et al. (1999) မှ ဖော်ပြထားသော terrain heterogeneity (မြေမျက်နှာသွင်ပြင် အနေအထားကွဲပြားမှု) ၏ အရေအတွက်ပြအတိုင်းအတာ (quantitative measurement) များကို တွက်ချက်ပေးပါသည်။ 3x3 pixel grid အတွင်း အမြင့် ပြောင်းလဲမှုများကို အကျဉ်းချုပ်ပြီး တည်နေရာတိုင်းအတွက် တွက်ချက်ပေးပါသည်။

Pixel တစ်ခုချင်းစီသည် ဗဟိုဆဲလ် (center cell) တစ်ခု နှင့် ၎င်းကို ဝန်းရံနေသည့် ဆဲလ် 8 ခု မှ အမြင့် ကွာခြားချက် ပါဝင်ပါသည်။

.. figure:: img/ruggedness.png
   :align: center

   အနိမ့် (အနီရောင်) မှ အမြင့် (အစိမ်းရောင်) တန်ဖိုးများဖြင့် Ruggedness layer


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Elevation layer**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Z factor**
     - ``Z_FACTOR``
     - [number]

       Default: 1.0
     - Vertical exaggeration (ဒေါင်လိုက်ချဲ့ကားခြင်း)။ ဤ parameter သည် Z ယူနစ်များသည် X နှင့် Y ယူနစ်များမှ ကွာခြားနေပါက အသုံးဝင်ပါသည်။ ဥပမာ- ပေ နှင့် မီတာများ။ ဤ parameter ကို ၎င်းအား ချိန်ညှိခြင်း ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။ ဤ parameter ၏ တန်ဖိုးကို တိုးမြှင့်ခြင်းသည် နောက်ဆုံးရရှိလာမည့်ရလာဒ်ကို ပိုမိုချဲ့ကား (exaggerate) စေမည်ဖြစ်သည် (၎င်းကို ပို၍ "hilly (တောင်ထူထပ်သော)" ပုံစံဖြစ်ပေါ်စေခြင်း)။ Default အားဖြင့် 1 ဖြစ်ပါသည် (ချဲ့ကားထားခြင်း (exaggeration) မရှိပါ)။
   * - **Ruggedness** **(မညီညာမှု)**
     - ``OUTPUT``
     - [raster]
       
       Default : ``[Save to temporary file]``
     - ရရှိလာသည့် output ruggedness raster layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**


Outputs (ရလဒ်များ)
...................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Ruggedness** **(မညီညာမှု)**
     - ``OUTPUT``
     - [raster]
     - ရရှိလာသည့် output ruggedness raster layer

Python code
............

**Algorithm ID**: ``qgis:ruggednessindex``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisslope:

Slope (လျှောစောက်)
-------------------

ထည့်သွင်းထားသော raster layer တစ်ခုမှ လျှောစောက် (slope) ကို တွက်ချက်ပေးပါသည်။ လျှောစောက် (slope) သည် မြေမျက်နှာသွင်ပြင်၏ စောင်းထောင့် (angle of inclination) ဖြစ်ပြီး **degrees (ဒီဂရီများ)** ဖြင့် ဖော်ပြပါသည်။

.. figure:: img/slope.png
   :align: center

   အနီရောင်ဖြင့် ပြန့်ပြူးသည့် ဧရိယာများ၊ အပြာရောင်ဖြင့် မတ်စောက်သည့် ဧရိယာများ


Parameters (သတ်မှတ်ချက်များ)
.............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Elevation layer**
     - ``INPUT``
     - [raster]
     - Digital Terrain Model raster layer
   * - **Z factor**
     - ``Z_FACTOR``
     - [number]

       Default: 1.0
     - Vertical exaggeration (ဒေါင်လိုက်ချဲ့ကားခြင်း)။ ဤ parameter သည် Z ယူနစ်များသည် X နှင့် Y ယူနစ်များမှ ကွာခြားနေပါက အသုံးဝင်ပါသည်။ ဥပမာ- ပေ နှင့် မီတာများ။ ဤ parameter ကို ၎င်းအား ချိန်ညှိခြင်း ပြုလုပ်ရန်အတွက် အသုံးပြုနိုင်ပါသည်။ ဤ parameter ၏ တန်ဖိုးကို တိုးမြှင့်ခြင်းသည် နောက်ဆုံးရရှိလာမည့်ရလာဒ်ကို ပိုမိုချဲ့ကား (exaggerate) စေမည်ဖြစ်သည် (၎င်းကို ပို၍ "hilly (တောင်ထူထပ်သော)" ပုံစံဖြစ်ပေါ်စေခြင်း)။ Default အားဖြင့် 1 ဖြစ်ပါသည် (ချဲ့ကားထားခြင်း (exaggeration) မရှိပါ)။
   * - **Slope** **(လျှောစောက်)**
     - ``OUTPUT``
     - [raster]
       
       Default : ``[Save to temporary file]``
     - output slope raster layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှတစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Outputs (ရလဒ်များ)
...................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Slope** **(လျှောစောက်)**
     - ``OUTPUT``
     - [raster]
     - ရရှိလာသည့် output slope raster layer

Python code
............

**Algorithm ID**: ``qgis:slope``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |334| replace:: ``NEW in 3.34``
