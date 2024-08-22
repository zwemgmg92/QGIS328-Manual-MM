Vector overlay (Vector များ အလွှာထပ်နေခြင်း)
=============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisclip:

Clip (ဖြတ်တောက်ခြင်း)
----------------------
ထပ်မံထည့်သွင်းထားသော polygon layer တစ်ခု၏ feature များကို အသုံးပြု၍ vector layer တစ်ခုကို ဖြတ်တောက် (clip) ပေးပါသည်။

ထပ်နေသည့် layer (overlay layer) ၏ polygon များအတွင်းတွင် ကျ‌ရောက်နေသော input layer ထဲရှိ feature များ၏ အစိတ်အပိုင်းများကိုသာလျှင် ရလာဒ်ထုတ်ပေးမည့် layer ထဲသို့ ပေါင်းထည့်မည် ဖြစ်ပါသည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

အဆိုပါ algorithm သည် တည်နေရာဆိုင်ရာ အညွှန်းကိန်းများကိုအသုံးပြုပြီး၊ ဂျီဩမေတြီဆိုင်ရာများကို ပြင်ဆင်ပါသည်။ ဂျီဩမေတြီသည် အဖုံးအအုပ် (mask) ဂျီဩမေတြီထဲတွင် အပြည့်အဝမပါဝင်ပါက ဖြတ်တောက်ခြင်း (clipping) လုပ်ဆောင်ချက်ကို လုပ်ဆောင်သွားမည်ဖြစ်သည်။

.. figure:: img/clip.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' တစ်ခုနှင့် feature တစ်ခုပါဝင်သော ထပ်နေသည့် (overlay) layer 'b' အကြား ဖြတ်တောက်ခြင်း လုပ်ဆောင်ချက် (ဘယ်ဘက်ပုံ) - ပြုပြင်ထားသော 'a' feature များပါဝင်သည့် ရလာဒ် layer အသစ်တစ်ခု (ညာဘက်ပုံ)

|checkbox| point ၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification <processing_inplace_edit>` ကို ခွင့်ပြုသည်။

**Default menu** - :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisintersection` ၊ :ref:`qgisdifference`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ဖြတ်တောက်ခြင်း (clip) ပြုလုပ်ခံရမည့် feature များပါဝင်သော layer
   * - **Overlay layer** **(ထပ်မည့် layer)**
     - ``OVERLAY``
     - [vector: polygon]
     - ဖြတ်တောက်မည့် feature များပါဝင်သည့် layer
   * - **Clipped** **(ဖြတ်တောက်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Overlay (clipping) layer အတွင်းကျရောက်နေသော input layer မှ feature များပါဝင်သော layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Clipped** **(ဖြတ်တောက်ထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Overlay layer ဖြင့် ပိုင်းခြားထားသော input layer မှ feature များပါဝင်သည့် Layer။

Python code
...........

**Algorithm ID**: ``qgis:clip``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisdifference:

Difference (ခြားနားချက်)
-------------------------

Overlay layer ၏ နယ်နိမိတ်များအတွင်းတွင် ကျရောက်ခြင်းမရှိသော input layer မှ feature များကို ထုတ်ယူပေးပါသည်။

Overlay layer ၏ feature များနှင့် တစ်စိတ်တစ်ပိုင်း ထပ်နေသော input layer ၏ feature များကို အဆိုပါ feature များ၏နယ်နိမိတ်တစ်လျောက်အတိုင်း ပိုင်းခြားသွားမည်ဖြစ်ပြီး overlay layer ၏ အပြင်ဘက်ရှိ အစိတ်အပိုင်းများသာလျှင် ကျန်ရှိမည်ဖြစ်ပါသည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

.. figure:: img/difference.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' တစ်ခုနှင့် feature တစ်ခုပါဝင်သော overlay layer 'b' အကြား ခြားနားမှုလုပ်ဆောင်ချက် (ဘယ်ဘက်ပုံ) - ပြုပြင်ထားသော 'a' feature များပါဝင်သည့် ရလာဒ် layer အသစ်တစ်ခု (ညာဘက်ပုံ)

|checkbox| သည် point ၊ line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်နိုင်ပါသည်။

**Default menu** - :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgismultidifference` ၊ :ref:`qgissymmetricaldifference` ၊ :ref:`qgisclip`

Parameters (Parameter များ)
............................

Basic parameters  (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် Layer
   * - **Overlay layer** **(ထပ်မည့် layer)**
     - ``OVERLAY``
     - [vector: any]
     
     - Input layer ဂျီဩမေတြီများမှ နုတ်ယူထားသော ဂျီဩမေတြီများပါဝင်သည့် Layer။ Input layer ဂျီသြမေတြီများတွင် ပါရှိသော dimension (အတိုင်းအတာ) များအတိုင်း (point - 0D ၊ line - 1D၊ polygon - 2D ၊ volume - 3D) အနည်းဆုံးပါရှိရမည် ဖြစ်ပါသည်။
   * - **Difference** **(ခြားနားချက်)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Overlay layer အတွင်းတွင် မရှိသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များ ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Grid size** **(Grid ကွက်အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GRID_SIZE``
     - [number]

       Default: Not set
     - Grid အရွယ်အစားကို ထည့်သွင်းပေးထားပါက input ဂျီဩမေတြီများကို ပေးထားသည့်အရွယ်အစားဖြင့် grid တစ်ခုသို့ snap (ဆွဲကပ်) ပေးမည်ဖြစ်ပြီး ရရှိလာသည့် vertex များကို ထိုတူညီသည့် grid ပေါ်တွင် တွက်ချက်ပေးမည်ဖြစ်သည်။ GEOS 3.9.0 သို့မဟုတ် ၎င်းနှင့်အထက်ဗားရှင်း လိုအပ်ပါသည်။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Difference** **(ခြားနားချက်)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Overlay layer ပေါ်တွင် ထပ်နေခြင်းမရှိသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များပါဝင်သည့် Layer။ 

Python code
...........

**Algorithm ID**: ``qgis:difference``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismultidifference:

Difference (multiple) (ခြားနားချက် (အများ))
--------------------------------------------

Overlay layer (များ) တစ်ခုခုမှ feature များ၏ အပြင်ဘက်တွင် အပြည့်အဝကျရောက်နေသော သို့မဟုတ်  တစ်စိတ်တစ်ပိုင်းထပ်နေသာ ထပ်နေသော input layer မှ feature များကို ထုတ်ယူပေးပါသည်။

Overlay layer တစ်ခုချင်းစီအတွက် ခြားနားချက်တွက်ချက်ရာတွင် ယခင်ခြားနားချက်လုပ်ဆောင်မှုများအားလုံး၏ ရလာဒ်နှင့် ယခု overlay layer များအကြားတွင် လုပ်ဆောင်မည်ဖြစ်သည်။ Overlay layer ထဲတွင် တစ်စိတ်တစ်ပိုင်းအားဖြင့် ထပ်နေသော input layer ၏ feature များကို အဆိုပါ feature ၏ နယ်နိမိတ်တစ်လျောက် ပိုင်းခြားမည်ဖြစ်ပြီး overlay layer ၏အပြင်ဘက်တွင်ရှိသော အပိုင်းများကိုသာလျှင်ထိန်းသိမ်းထားမည်ဖြစ်သည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

.. figure:: img/difference_multi.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' တစ်ခုနှင့် feature တစ်ခုသာပါသော ထည့်သွင်းထားသည့် layer 'b' နှင့် 'c' ကြားရှိ ခြားနားမှုလုပ်ဆောင်ချက် (ဘယ်ဘက်) - ပြုပြင်ထားသည့် 'a' feature များပါဝင်သည့် ရလာဒ် layer အသစ်တစ်ခု (ညာဘက်)

.. seealso:: :ref:`qgisdifference` ၊ :ref:`qgissymmetricaldifference` ၊ :ref:`qgisclip`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များ၏ အစိတ်အပိုင်းကို ထုတ်ယူရန် Layer။
   * - **Overlay layers** **(ထပ်မည့် layer များ)**
     - ``OVERLAYS``
     - [vector: any] [list]
     - Input layer ၏ ဂျီဩမေတြီများမှ နုတ်ယူထားသည့် ဂျီဩမေတြီများပါဝင်သည့် layer များစာရင်း။ Input layer ဂျီသြမေတြီများတွင် ပါရှိသော dimension (အတိုင်းအတာ) များအတိုင်း (point - 0D ၊ line - 1D၊ polygon - 2D ၊ volume - 3D) အနည်းဆုံးပါရှိရမည် ဖြစ်ပါသည်။
   * - **Difference** **(ခြားနားချက်)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Overlay layer များ၏ feature များနှင့် ထပ်မနေသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များ ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Difference** **(ခြားနားချက်)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Overlay layer များမှ feature များနှင့် ထပ်နေခြင်းမရှိသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များပါဝင်သည့် Layer။

Python code
...........

**Algorithm ID**: ``qgis:multidifference``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractbyextent:

Extract/clip by extent (နယ်ပယ်အကျယ်အဝန်းဖြင့် ထုတ်ယူခြင်း/ဖြတ်တောက်ခြင်း)
------------------------------------------------------------------------------

သတ်မှတ်ထားသော extent (နယ်ပယ်အကျယ်အဝန်း) အတွင်း ကျ‌‌ရောက်နေသော feature များသာလျှင်ပါဝင်သည့် vector layer အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။

Extent ကို ထိဖြတ်သွားသော မည်သည့် feature မဆို ပါဝင်မည်ဖြစ်သည်။

.. figure:: img/extractbyextent.png
  :align: center

  Feature သုံးခုပါသော input layer 'a' နှင့် dash (-) ဖြင့်ပြထားသော extent တစ်ခုကြားရှိ ထုတ်ယူခြင်းလုပ်ဆောင်ချက် (ဘယ်ဘက်) - အကိုးအကားအတွက် dash ဖြင့်ပြထားသော extent ဖြင့် ရလာဒ် feature များ (ညာဘက်)

.. seealso:: :ref:`qgisclip`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် Layer။ 
   * - **Extent (xmin, xmax, ymin, ymax)** **(နယ်ပယ်အကျယ်အဝန်း (x အနည်းဆုံး၊ x အများဆုံး၊ y အနည်းဆုံး၊ y အများဆုံး))**
     - ``EXTENT``
     - [extent]
     - ဖြတ်တောက်ခြင်း (clipping) ပြုလုပ်ရန်အတွက် extent။ 

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Clip features to extent** **(Feature များကို extent ဖြင့်ဖြတ်ခြင်း)**
     - ``CLIP``
     - [boolean]
       
       Default: False
     - အမှန်ခြစ်ခြစ်ထားလျှင် output ဂျီဩမေတြီများကို အမျိုးအစားတူညီစေရန်အတွက် ဂျီဩမေတြီများစွာ (multi geometries) သို့ အလိုအလျောက်ပြောင်းလဲပေးမည် ဖြစ်ပါသည်။ ထို့အပြင် ဂျီဩမေတြီတစ်ခုလုံးကို output အဖြစ် ထုတ်ယူမည့်အစား ဂျီဩမေတြီများကို ရွေးချယ်ထားသော extent ဖြင့် ဖြတ်တောက်သွားမည် ဖြစ်ပါသည်။
       
       .. figure:: img/extractbyextent_clip.png
          :align: center

          Feature သုံးခုပါသော input layer 'a' နှင့် dash (-) ဖြင့်ပြထားသော extent တစ်ခု အကြားရှိ ထုတ်ယူခြင်းလုပ်ဆောင်ချက် (ဘယ်ဘက်) - အကိုးအကားအတွက် dash ဖြင့်ပြထားသော extent ဖြင့် ရလာဒ် feature များ (ညာဘက်)

   * - **Extracted** **(ထုတ်ယူထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Clip extent အတွင်းကျရောက်သည့် input layer မှ feature များ ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်- 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extracted** **(ထုတ်ယူထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ဖြတ်တောက်ထားသည့် feature များပါဝင်သည့် Layer။

Python code
...........

**Algorithm ID**: ``qgis:extractbyextent``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgisintersection:

Intersection (ထိဖြတ်ခြင်း)
---------------------------

Overlay layer ထဲရှိ feature များနှင့် ထပ်နေသည့် input layer မှ feature အစိတ်အပိုင်းများကို ထုတ်ယူပေးပါသည်။

Intersection (ထိဖြတ်ခြင်း) layer ထဲရှိ feature များကို input layer နှင့် overlay layer နှစ်ခုစလုံးမှ ထပ်နေသော feature များ၏ အချက်အလက်များ (attribute) များဖြင့် သတ်မှတ်ပေးမည်ဖြစ်သည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

.. figure:: img/intersection.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' နှင့် feature တစ်ခုပါသော overlay layer 'b' အကြားရှိ ထိဖြတ်ခြင်း လုပ်ဆောင်ချက် (ဘယ်ဘက်) - ထပ်နေသော ဧရိယာများသည် layer နှစ်ခုစလုံး၏ attribute များပါဝင်သော feature နှစ်ခုပါသည့် layer အသစ်ဖြစ်လာပါသည်။

**Default menu** - :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgismultiintersection` ၊ :ref:`qgisclip` ၊ :ref:`qgisdifference`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် Layer။
   * - **Overlay layer** **(ထပ်မည့် layer)**
     - ``OVERLAY``
     - [vector: any]
     - ထပ်နေခြင်းရှိ မရှိ စစ်ဆေးရန် feature များပါဝင်သည့် Layer။ Input layer ဂျီသြမေတြီများတွင် ပါရှိသော dimension (အတိုင်းအတာ) များအတိုင်း (point - 0D ၊ line - 1D၊ polygon - 2D ၊ volume - 3D) အနည်းဆုံးပါရှိရမည် ဖြစ်ပါသည်။
   * - **Input fields to keep (leave empty to keep all fields)** **(ဆက်လက်ထားရှိမည့် input field များ (field များအားလုံးကို ဆက်လက်ထားရှိရန် empty ထားပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_FIELDS``
     - [tablefield: any] [list]

       Default: None
     - Output ထဲတွင် ဆက်လက်ထားရှိမည့် input layer ၏ Field (များ)။ Field များကို ရွေးချယ်ခြင်းမရှိလျှင် field အားလုံးကို ယူမည်ဖြစ်သည်။
   * - **Overlay fields to keep (leave empty to keep all fields)** **(ဆက်လက်ထားရှိမည့် overlay field များ (field များအားလုံးကို ဆက်လက်ထားရှိရန် empty ထားပါ))**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS``
     - [tablefield: any] [list]

       Default: None
     - Output ထဲတွင် ဆက်လက်ထားရှိမည့် input layer ၏ Field (များ)။ Field များကို ရွေးချယ်ခြင်းမရှိလျှင် field အားလုံးကို ယူမည်ဖြစ်သည်။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။
   * - **Intersection** **(ထိဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Overlay layer မှ တစ်ခု သို့မဟုတ် တစ်ခုထပ်ပိုသော feature များနှင့် ထပ်နေသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များ ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်- 

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overlay fields prefix** **(ထပ်မည့် field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS_PREFIX``
     - [string]
     - Overlay layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခု ပေါင်းထည့်ပါ။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။
   * - **Grid size** **(Gird ကွက်အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GRID_SIZE``
     - [number]

       Default: Not set
     - Grid အရွယ်အစားကို ထည့်သွင်းပေးထားပါက input ဂျီဩမေတြီများကို ပေးထားသည့်အရွယ်အစားဖြင့် grid တစ်ခုသို့ snap (ဆွဲကပ်) ပေးမည်ဖြစ်ပြီး ရရှိလာသည့် vertex များကို ထိုတူညီသည့် grid ပေါ်တွင် တွက်ချက်ပေးမည်ဖြစ်သည်။ GEOS 3.9.0 သို့မဟုတ် ၎င်းနှင့်အထက်ဗားရှင်း လိုအပ်ပါသည်။

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
   * - **Intersection** **(ထိဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Overlay layer ပေါ်တွင် ထပ်နေသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များပါဝင်သည့် Layer။

Python code
...........

**Algorithm ID**: ``qgis:intersection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgismultiintersection:

Intersection (multiple) (ထိဖြတ်ခြင်း (အများ))
----------------------------------------------

Overlay layer များအားလုံးနှင့် input layer ထဲရှိ feature များ၏ ထပ်နေသောအစိတ်အပိုင်းများကို ထုတ်ယူပေးပါသည်။

Output layer ထဲရှိ feature များကို input layer နှင့် overlay layer နှစ်ခုစလုံးမှ ထပ်နေသော feature များ၏အချက်အလက်များ (attribute) များဖြင့် သတ်မှတ်ပေးမည်ဖြစ်သည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

.. figure:: img/intersection_multi.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' နှင့် feature တစ်ခုပါသော overlay layer 'b' နှင့် 'c' အကြားရှိ ထိဖြတ်ခြင်း လုပ်ဆောင်ချက် (ဘယ်ဘက်) - ထပ်နေသော ဧရိယာများသည် layer အားလုံး၏ attribute များပါဝင်သော feature နှစ်ခုပါသည့် layer အသစ်ဖြစ်လာပါသည် (ညာဘက်)

.. seealso:: :ref:`qgisintersection` ၊ :ref:`qgisclip` ၊ :ref:`qgisdifference`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် Layer။ 
   * - **Overlay layers** **(ထပ်မည့် layer များ)**
     - ``OVERLAYS``
     - [vector: any] [list]
     - ထပ်နေခြင်းရှိ မရှိ စစ်ဆေးရန် feature များပါဝင်သည့် Layer။ Input layer ဂျီသြမေတြီများတွင် ပါရှိသော dimension (အတိုင်းအတာ) များအတိုင်း (point - 0D ၊ line - 1D၊ polygon - 2D ၊ volume - 3D) အနည်းဆုံးပါရှိရမည် ဖြစ်ပါသည်။

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overlay fields prefix** **(ထပ်မည့် field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS_PREFIX``
     - [string]
     - Overlay layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခု ပေါင်းထည့်ပါ။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။

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
   * - **Intersection** **(ထိဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Overlay layer များအားလုံးနှင့် ထပ်နေသော input layer မှ feature (များ၏ အစိတ်အပိုင်းများ) များပါဝင်သည့် Layer။

Python code
...........

**Algorithm ID**: ``qgis:multiintersection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgislineintersections:

Line intersections (မျဉ်း ထိဖြတ်ခြင်းများ)
-------------------------------------------

Layer နှစ်ခုမှ line များ ထိဖြတ်သောနေရာတွင် Point feature များ ဖန်တီးပေးပါသည်။

.. figure:: img/line_intersection.png
  :align: center

  ထိဖြတ်ခြင်း Point များ

**Default menu** - :menuselection:`Vector --> Analysis Tools`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော Line layer။
   * - **Intersect layer** **(ထိဖြတ် layer)**
     - ``INTERSECT``
     - [vector: line]
     - Line ထိဖြတ်ခြင်းများကို ရှာဖွေရန် အသုံးပြုမည့် Layer
   * - **Input fields to keep (leave empty to keep all fields)** **(ဆက်လက်ထားရှိမည့် input field များ(field များအားလုံးကို ဆက်လက်ထားရှိရန် empty ထားပါ))**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INPUT_FIELDS``
     - [tablefield: any] [list]
       
       Default: None
     - Output ထဲတွင် ဆက်လက်ထားရှိမည့် input layer ၏ field (များ)။ Field များကို ရွေးချယ်ခြင်းမရှိလျှင် field အားလုံးကို ယူမည်ဖြစ်သည်။
   * - **Intersect fields to keep (leave empty to keep all fields)** **(ဆက်လက်ထားရှိမည့် intersect field များ(field များအားလုံးကို ဆက်လက်ထားရှိရန် empty ထားပါ))**
       
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INTERSECT_FIELDS``
     - [tablefield: any] [list]
       
       Default: None
     - Output ထဲတွင် ဆက်လက်ထားရှိမည့် intersect layer ၏ field (များ)။ Field များကို ရွေးချယ်ခြင်းမရှိလျှင် field အားလုံးကို ယူမည်ဖြစ်သည်။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။
   * - **Intersection** **(ထိဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [vector: point]
       
       Default: ``[Create temporary layer]``
     - Input layer နှင့် overlay layer များမှ line များ၏ ထိဖြတ်ခြင်း point များ ပါဝင်မည့် layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Intersect fields prefix** **(Intersect field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``INTERSECT_FIELDS_PREFIX``
     - [string]
     - Intersect layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခုကို ပေါင်းထည့်ပါ။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Intersections** **(ထိဖြတ်ခြင်း)**
     - ``OUTPUT``
     - [vector: point]
     - Layer နှစ်ခုစလုံး၏ အချက်အလက် (attribute) များ ပါဝင်သည့် line များ ထိဖြတ်ရာ နေရာများ၏ Point vector layer။

Python code
...........

**Algorithm ID**: ``qgis:lineintersections``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissplitwithlines:

Split with lines (မျဉ်းများဖြင့် ပိုင်းခြားခြင်း)
--------------------------------------------------

Layer တစ်ခုထဲရှိ line များ သို့မဟုတ် polygon များကို အခြား layer ထဲရှိ line များ သို့မဟုတ် polygon အကွင်းများကို အသုံးပြုပြီး breaking point (ခွဲမှတ်) များသတ်မှတ်ရန် ပိုင်းခြားပေးပါသည်။ Layer နှစ်ခုစလုံးထဲရှိ ဂျီဩမေတြီများအကြားရှိ ထိဖြတ်ရာ နေရာများကို ပိုင်းခြားအမှတ်များ (split point) အဖြစ် စဉ်းစားမည်ဖြစ်သည်။

Output တွင် split feature များအတွက် ဂျီဩမေတြီများစွာ (multi geometry) ပါဝင်မည် ဖြစ်သည်။

.. figure:: img/split_with_lines.png
  :align: center

  ပိုင်းခြားထားသော မျဉ်းများ

|checkbox| သည် Line နှင့် polygon feature များ၏ :ref:`features in-place modification (နေရာတွင် feature များကို မွမ်းမံပြင်ဆင်ခြင်း) <processing_inplace_edit>` ကို လုပ်ဆောင်နိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: line, polygon]
     - ပိုင်းခြားရန် line များ သို့မဟုတ် polygon များ ပါဝင်သည့် Layer။
   * - **Split layer** **(ပိုင်းခြားပေးမည့် layer)**
     - ``LINES``
     - [vector: line, polygon]
     - Breaking point (ခွဲမှတ်) များကို သတ်မှတ်ရန် အသုံးပြုသည့် line များ သို့မဟုတ် ring များ ပါဝင်သည့် Layer။
   * - **Split** **(ပိုင်းခြားထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
       
       Default: ``[Create temporary layer]``
     - Input layer မှ ပိုင်းခြားထားသည့် line/polygon feature များ ပါဝင်စေရန် layer ကို သတ်မှတ်ပါ (split layer ထဲရှိ line တစ်ခုဖြင့် ထိဖြတ်ခြင်းများရှိသော ကိစ္စရပ်များတွင်)။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Split** **(ပိုင်းခြားထားပြီးသော)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ပိုင်းခြားထားသော line များ သို့မဟုတ် polygon များ ပါဝင်သည့် output  vector layer ။

Python code
...........

**Algorithm ID**: ``qgis:splitwithlines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgissymmetricaldifference:

Symmetrical difference (အချိုးညီ ခြားနားမှု)
---------------------------------------------

Input layer နှင့် overlay layer နှစ်ခုစလုံးမှ feature များ ပါဝင်သည့် layer တစ်ခု ဖန်တီးပေးပါသည်။ သို့သော် အဆိုပါ layer နှစ်ခုအကြားရှိ ထပ်နေသော ဧရိယာများကို ဖယ်ရှားသွားမည် ဖြစ်သည်။

Symmetrical difference layer ၏ အချက်အလက် (attribute) ဇယားတွင် input layer နှင့် overlay layer နှစ်ခုစလုံးမှ attribute များနှင့် field များ ပါဝင်မည် ဖြစ်ပါသည်။

.. include:: ../algs_include.rst
   :start-after: **warning_attributes**
   :end-before: **end_warning_attributes**

.. figure:: img/symmetrical_difference.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' နှင့် feature တစ်ခုသာပါဝင်သည့် overlay layer 'b' အကြားရှိ Symmetrical difference လုပ်ဆောင်ချက် (ဘယ်ဘက်) - Layer နှစ်ခုစလုံး၏ attribute များပါဝင်သည့် feature သုံးခုပါဝင်သော ရလာဒ် layer (ညာဘက်)

**Default menu** - :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgisdifference` ၊ :ref:`qgisclip` ၊ :ref:`qgisintersection`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် ပထမဆုံး layer။
   * - **Overlay layer** **(ထပ်မည့် layer)**
     - ``OVERLAY``
     - [vector: any]
     - Feature ၏ အစိတ်အပိုင်းများကို ထုတ်ယူရန် ဒုတိယ layer။ အကောင်းဆုံးမှာ ဂျီဩမေတြီ အမျိုးအစားများသည် input layer အတိုင်း တူညီသင့်ပါသည်။
   * - **Symmetrical difference** **(အချိုးညီ ခြားနားမှု)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - အခြား layer မှ feature များဖြင့် ထပ်နေခြင်းမရှိသော input layer နှင့် overlay layer များမှ feature (များ၏ အစိတ်အပိုင်းများ) များ ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overlay fields prefix** **(Overlay field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS_PREFIX``
     - [string]
     - Overlay layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခု ပေါင်းထည့်ပါ။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။
   * - **Grid size** **(Gird ကွက်အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GRID_SIZE``
     - [number]

       Default: Not set
     - Grid အရွယ်အစားကို ထည့်သွင်းပေးထားပါက input ဂျီဩမေတြီများကို ပေးထားသည့်အရွယ်အစားဖြင့် grid တစ်ခုသို့ snap (ဆွဲကပ်) ပေးမည်ဖြစ်ပြီး ရရှိလာသည့် vertex များကို ထိုတူညီသည့် grid ပေါ်တွင် တွက်ချက်ပေးမည်ဖြစ်သည်။ GEOS 3.9.0 သို့မဟုတ် ၎င်းနှင့်အထက်ဗားရှင်း လိုအပ်ပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Symmetrical difference** **(အချိုးညီ ခြားနားမှု)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Layer နှစ်ခုစလုံး၏ အချက်အလက်များပါဝင်ပြီး အခြား layer နှင့် ထပ်နေခြင်းမရှိသော layer တစ်ခုချင်းစီမှ feature (များ၏ အစိတ်အပိုင်းများ) များပါဝင်သည့် layer။

Python code
...........

**Algorithm ID**: ``qgis:symmetricaldifference``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisunion:

Union (စုပေါင်းခြင်း)
----------------------

Input layer အတွင်းရှိ feature များအကြား ထပ်နေခြင်းများကို စစ်ဆေးပေးပြီး ထပ်နေသော (overlapping) နှင့် ထပ်နေခြင်းမရှိသော (non-overlapping) အစိတ်အပိုင်းများအတွက် သီးခြား feature များကိုဖန်တီးပေးပါသည်။ ထပ်နေသည့် ဧရိယာသည် အဆိုပါ ထပ်နေသည့်အထဲရှိ feature များရှိသလောက်အတိုင်း တစ်ထပ်တည်းတူညီသည့် ထပ်နေသော (overlapping) feature များကို ဖန်တီးပေးမည် ဖြစ်ပါသည်။

.. figure:: img/union.png
  :align: center

  ထပ်နေသော feature နှစ်ခုပါဝင်သည့် input layer တစ်ခုဖြင့် Union လုပ်ဆောင်ချက် (ဘယ်ဘက်) - Feature လေးခုအဖြစ် ရလာဒ်ရရှိခြင်း (အလယ်)- ရှင်းလင်းပြတ်သားရန်အတွက် ရွှေ့ထားသော feature များ (ညာဘက်)

Overlay layer တစ်ခုကိုလည်း အသုံးပြုနိုင်ပါသည်။ အဆိုပါကိစ္စရပ်တွင် layer တစ်ခုချင်းစီမှ feature များသည် အခြား layer တစ်ခုမှ feature များဖြင့် ထပ်နေသောနေရာတွင် ပိုင်းခြားသွားမည်ဖြစ်ပြီး input layer နှင့် overlay layer မှ အစိတ်အပိုင်းအားလုံး ပါဝင်သော layer တစ်ခုကို ဖန်တီးပေးမည် ဖြစ်ပါသည်။ တူညီသည့် layer ထဲရှိ feature များသည် တစ်ခုနှင့်တစ်ခု ပိုင်းခြားမည် မဟုတ်ပါ။ စုပေါင်းထားသည့် (Union) layer ၏ အချက်အလက်ဇယားတွင် ထပ်နေခြင်းမရှိသော feature များအတွက် သက်ဆိုင်ရာ မူလ layer မှ အချက်အလက်တန်ဖိုးများနှင့် ထပ်နေသော feature များအတွက် layer နှစ်ခုစလုံးမှ အချက်အလက်တန်ဖိုးများကို ဖြည့်သွားမည် ဖြစ်ပါသည်။

.. figure:: img/union_with_overlay.png
  :align: center

  Feature နှစ်ခုပါဝင်သော input layer 'a' နှင့် feature တစ်ခုသာပါဝင်သည့် overlay layer 'b' အကြားရှိ Union လုပ်ဆောင်ချက် (ဘယ်ဘက်) - layer နှစ်ခုစလုံးမှ အချက်အလက်များပါဝင်သည့် feature ငါးခုပါဝင်သော ရလာဒ် layer (ညာဘက်)

.. note::
   Overlay layer တစ်ခုဖြင့်၊ တူညီသည့် layer ထဲရှိ feature များသည် တစ်ခုနှင့်တစ်ခု ပိုင်းခြားမည် မဟုတ်ပါ။ တူညီသည့် layer ပေါ်တွင် အခြား layer များကဲ့သို့ ပိုင်းခြားလိုပါက ပထမဆုံးအနေဖြင့် layer များစွာဖြင့် algorithm ကို လုပ်ဆောင်ပါ၊ ထို့နောက် ရရှိလာသော output ဖြင့်သာ algorithm ကို ထပ်မံ လုပ်ဆောင်ပါ။

**Default menu** - :menuselection:`Vector --> Geoprocessing Tools`

.. seealso:: :ref:`qgismultiunion` ၊ :ref:`qgisclip` ၊ :ref:`qgisdifference` ၊ :ref:`qgisintersection`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထိဖြတ်ရာ နေရာတိုင်းတွင် ပိုင်းခြားရန် input vector layer။
   * - **Overlay layer** **(ထပ်မည့် layer)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY``
     - [vector: any]
     - ပထမဆုံးတစ်ခုသို့ ပေါင်းစပ်မည့် Layer။ အကောင်းဆုံးမှာ ဂျီဩမေတြီ အမျိုးအစားများသည် input layer အတိုင်း တူညီသင့်ပါသည်။
   * - **Union** **(စုပေါင်းခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Input layer နှင့် overlay layer များမှ feature များ (ပိုင်းခြားထားသော နှင့် ပုံတူပွားထားသော) ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ ‌အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overlay fields prefix** **(Overlay field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS_PREFIX``
     - [string]
     - Overlay layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခု ပေါင်းထည့်ပါ။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။
   * - **Grid size** **(Grid ကွက်အရွယ်အစား)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``GRID_SIZE``
     - [number]

       Default: Not set
     - Grid အရွယ်အစားကို ထည့်သွင်းပေးထားပါက input ဂျီဩမေတြီများကို ပေးထားသည့်အရွယ်အစားဖြင့် grid တစ်ခုသို့ snap (ဆွဲကပ်) ပေးမည်ဖြစ်ပြီး ရရှိလာသည့် vertex များကို ထိုတူညီသည့် grid ပေါ်တွင် တွက်ချက်ပေးမည်ဖြစ်သည်။ GEOS 3.9.0 သို့မဟုတ် ၎င်းနှင့်အထက်ဗားရှင်း လိုအပ်ပါသည်။

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Union** **(စုပေါင်းခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - လုပ်ဆောင်ထားသည့် layer (များ)မှ ထပ်နေသော နှင့် ထပ်နေခြင်းမရှိသော အစိတ်အပိုင်းများအားလုံး ပါဝင်သည့် Layer ။

Python code
...........

**Algorithm ID**: ``qgis:union``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgismultiunion:


Union (multiple) (စုပေါင်းခြင်း (အများ))
-----------------------------------------

Input layer အတွင်းရှိ feature များအကြား ထပ်နေခြင်းများကို စစ်ဆေးပေးပြီး ထပ်နေသော (overlapping) နှင့် ထပ်နေခြင်းမရှိသော (non-overlapping) အစိတ်အပိုင်းများအတွက် သီးခြား feature များကို ဖန်တီးပေးပါသည်။ ထပ်နေသည့် ဧရိယာသည် အဆိုပါ ထပ်နေသည့်အထဲရှိ feature များရှိသလောက်အတိုင်း တစ်ထပ်တည်းတူညီသည့် ထပ်နေသော (overlapping) feature များကို ဖန်တီးပေးမည် ဖြစ်ပါသည်။

.. figure:: img/union.png
  :align: center

  ထပ်နေသော feature နှစ်ခုပါဝင်သည့် input layer တစ်ခုဖြင့် Union လုပ်ဆောင်ချက် (ဘယ်ဘက်) - Feature လေးခုအဖြစ် ရလာဒ်ရရှိခြင်း (အလယ်) - ရှင်းလင်းပြတ်သားရန်အတွက် ရွှေ့ထားသော feature များ (ညာဘက်)

Overlay layer အများအပြား (multiple) ကိုလည်း အသုံးပြုနိုင်ပါသည်။ အဆိုပါကိစ္စရပ်တွင် layer တစ်ခုချင်းစီမှ feature များသည် အခြား layer အားလုံးမှ feature များဖြင့် ထပ်နေသောနေရာတွင် ပိုင်းခြားသွားမည်ဖြစ်ပြီး input layer နှင့် overlay layer များမှ အစိတ်အပိုင်းအားလုံး ပါဝင်သော layer တစ်ခု ဖန်တီးပေးမည်ဖြစ်ပါသည်။ တူညီသည့် layer ထဲရှိ feature များသည် တစ်ခုနှင့်တစ်ခု ပိုင်းခြားမည် မဟုတ်ပါ။ စုပေါင်းထားသည့် (Union) layer ၏ အချက်အလက်ဇယားတွင် ထပ်နေခြင်းမရှိသော feature များအတွက် သက်ဆိုင်ရာ မူလ layer မှ အချက်အလက်တန်ဖိုးများနှင့် ထပ်နေသော feature များအတွက် layer နှစ်ခုစလုံးမှ အချက်အလက်တန်ဖိုးများကို ဖြည့်သွားမည် ဖြစ်ပါသည်။

.. figure:: img/union_multi.png
  :align: center

  Feature နှစ်ခုပါဝင်သည့် input layer 'a' နှင့် feature တစ်ခုသာပါသော overlay layer 'b' နှင့် 'c' အကြားရှိ Union လုပ်ဆောင်ချက် (ဘယ်ဘက်) - Layer အားလုံးမှ အချက်အလက်များဖြင့် feature ၁၁ ခုပါဝင်သည့် ရလာဒ် layer (ညာဘက်)

.. note::
   Overlay layer တစ်ခုဖြင့်၊ တူညီသည့် layer ထဲရှိ feature များသည် တစ်ခုနှင့်တစ်ခု ပိုင်းခြားမည် မဟုတ်ပါ။ တူညီသည့် layer ပေါ်တွင် အခြား layer များကဲ့သို့ ပိုင်းခြားလိုပါက ပထမဆုံးအနေဖြင့် layer များစွာဖြင့် algorithm ကို လုပ်ဆောင်ပါ၊ ထို့နောက် ရရှိလာသော output ဖြင့်သာ algorithm ကို ထပ်မံ လုပ်ဆောင်ပါ။

.. seealso:: :ref:`qgisunion` ၊ :ref:`qgisclip` ၊ :ref:`qgisdifference` ၊ :ref:`qgisintersection`

Parameters (Parameter များ)
............................

Basic parameters (အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - ထိဖြတ်ရာ နေရာတိုင်းတွင် ပိုင်းခြားရန် input vector layer။
   * - **Overlay layers** **(ထပ်မည့် layer များ)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAYS``
     - [vector: any] [list]
     - ပထမဆုံးတစ်ခုသို့ ပေါင်းစပ်မည့် Layer။ အကောင်းဆုံးမှာ ဂျီဩမေတြီ အမျိုးအစားများသည် input layer အတိုင်း တူညီသင့်ပါသည်။
   * - **Union** **(စုပေါင်းခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - Input layer နှင့် overlay layer များမှ feature များ (ပိုင်းခြားထားသော နှင့် ပုံတူပွားထားသော) ပါဝင်မည့် layer ကို သတ်မှတ်ပါ။ ‌အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**


Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Overlay fields prefix** **(Overlay field များ၏ရှေ့ဆက်စာလုံး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``OVERLAY_FIELDS_PREFIX``
     - [string]
     - Overlay layer ၏ field များကို ခွဲခြားသတ်မှတ်ရန် prefix (ရှေ့ဆက်စာလုံး) တစ်ခု ပေါင်းထည့်ပါ။ အမည်တူနေခြင်းများကို ရှောင်ရှားရန် ပုံတူဖြစ်နေသော (Duplicate) field အမည်များတွင် အရေအတွက်နောက်ဆက်တွဲတစ်ခု (count suffix) ဆက်တွဲပေါင်းထည့်ပေးမည်ဖြစ်သည်။


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Union** **(စုပေါင်းခြင်း)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - လုပ်ဆောင်ထားသည့် layer (များ)မှ အချက်အလက်များအားလုံးပါဝင်သည့် ထပ်နေသော နှင့် ထပ်နေခြင်းမရှိသော အစိတ်အပိုင်းများအားလုံး ပါဝင်သည့် Layer။


Python code
...........

**Algorithm ID**: ``qgis:multiunion``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**



.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
