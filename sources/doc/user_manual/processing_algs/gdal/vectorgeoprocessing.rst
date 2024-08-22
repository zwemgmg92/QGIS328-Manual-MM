Vector geoprocessing (Vector ပထဝီဝင်ဆိုင်ရာများလုပ်ဆောင်ခြင်း)
===============================================================

.. only:: html

   .. contents::
      :local:
      :depth: 1

.. _gdalbuffervectors:

Buffer vectors (Buffer vector များ)
------------------------------------

Vector layer တစ်ခု၏ feature များပတ်လည်တွင် buffer (ကြားခံဇုံ) များဖန်တီးပေးပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)
     - ``GEOMETRY``
     - [string]

       Default: 'geometry'
     - အသုံးပြုမည့် input ဂျီဩမေတြီ column ၏ အမည်
   * - **Buffer distance** (**Buffer အကွာအဝေး**)
     - ``DISTANCE``
     - [number]

       Default: 10.0
     - အနည်းဆုံး- 0.0
   * - **Dissolve by attribute** (**Attribute အရ dissolve (ပေါင်းစပ်) ပြုလုပ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any]

       Default: None
     - Dissolve ပြုလုပ်ခြင်းအတွက်အသုံးပြုသော column
   * - **Dissolve results** (**Dissolve ပြုလုပ်ထားသော ရလာဒ်များ**)
     - ``DISSOLVE``
     - [boolean]

       Default: False
     - သတ်မှတ်ထားလျှင် ရလာဒ်သည် dissolve ပြုလုပ်ခံရပါမည်။ Dissolve ပြုလုပ်ခြင်းအတွက် column သတ်မှတ်မပေးထားလျှင် buffer များအားလုံးကို feature တစ်ခုတည်းအဖြစ် dissolve ပြုလုပ်မည်ဖြစ်ပါသည်။
   * - **Produce one feature for each geometry in any kind of
       geometry collection in the source file** (**မူရင်း file ထဲမှ မည်သည့် ဂျီဩမေတြီ စုစည်းခြင်းထဲတွင်မဆို ဂျီဩမေတြီ တစ်ခုချင်းစီအတွက် feature တစ်ခုဖန်တီးခြင်း**)
     - ``EXPLODE_COLLECTIONS``
     - [boolean]

       Default: False
     -
   * - **Buffer**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output buffer layer ကိုသတ်မှတ်ပေးပါသည်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

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
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Buffer**
     - ``OUTPUT``
     - [vector: polygon]
     - Output buffer layer

Python code
............

**Algorithm ID**: ``gdal:buffervectors``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalclipvectorbyextent:

Clip vector by extent (အကျယ်အဝန်းဖြင့် vector ကိုဖြတ်ခြင်း)
------------------------------------------------------------

OGR မှလုပ်ဆောင်ပေးနိုင်သော vector file များကို သတ်မှတ်ထားသော အကွာအဝေး (extent) ဖြင့် ပိုင်းဖြတ်ပေးပါသည်။

Algorithm ကို `GDAL ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Clip extent** (**ဖြတ်မည့်အကျယ်အဝန်း**)
     - ``EXTENT``
     - [extent]

     - Output vector file အတွက်အသုံးပြုမည့် စတုဂံပုံစံအကျယ်အဝန်းနယ် ကိုသတ်မှတ်ပေးပါသည်။ ဖြစ်စေလိုသော CRS ကိုဩဒိနိတ်ဖြင့် ၎င်းကိုသတ်မှတ်ရပါမည်။

       .. include:: ../algs_include.rst
          :start-after: **extent_options**
          :end-before: **end_extent_options**

   * - **Clipped (extent)** (**ဖြတ်ထားသော (အကျယ်အဝန်း)**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
   
       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - ဖြတ်ထားသော output layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Clipped (extent)** (**ဖြတ်ထားသော (အကျယ်အဝန်း)**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ဖြတ်ထားသော output layer။ Default format သည် "ESRI Shapefile" ဖြစ်ပါသည်။

Python code
............

**Algorithm ID**: ``gdal:clipvectorbyextent``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalclipvectorbypolygon:

Clip vector by mask layer (ဖုံးအုပ် layer ဖြင့် vector ကိုဖြတ်ခြင်း)
---------------------------------------------------------------------

OGR မှလုပ်ဆောင်ပေးနိုင်သော vector layer ကို mask polygon layer တစ်ခုဖြင့် ဖြတ်ပေးပါသည်။

Algorithm ကို `GDAL ogr2ogr utility <https://gdal.org/programs/ogr2ogr.html>`_ မှ ရယူပါသည်။

Parameter များ
...............

Basic parameters(အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Mask layer**
     - ``MASK``
     - [vector: polygon]
     - Input vector layer အတွက် ဖြတ်မည့် extent အဖြစ် အသုံးပြုမည့် layer။
   * - **Clipped (mask)** (**ဖြတ်ထားသော (mask)**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - ဖြတ်ထားသော (masked) layer။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Clipped (mask)** (**ဖြတ်ထားသော (mask)**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Mask ဖြင့် ဖြတ်ထုတ်ထားသည့် output layer ။ Default format မှာ "ESRI Shapefile" ဖြစ်ပါသည်။

Python code
............

**Algorithm ID**: ``gdal:clipvectorbypolygon``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaldissolve:

Dissolve (ပေါင်းစပ်ခြင်း)
--------------------------

ရွေးချယ်ထားသော attribute/field မှ တန်ဖိုးတူညီသော ဂျီဩမေတြီ များကို dissolve (ပေါင်းစပ်) ပြုလုပ်ပေးပါသည်။ Output ဂျီဩမေတြီ များသည် multipart (အပိုင်းများစွာ) ဖြစ်နေနိုင်ပါသည်။


Parameter များ
...............

Basic parameters(အခြေခံ parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40
   :class: longtable

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - Dissolve ပြုလုပ်မည့် input layer
   * - **Dissolve field** (**Dissolve ပြုလုပ်မည့် column**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any]
     - Dissolve ပြုလုပ်ခြင်းအတွက် အသုံးပြုမည့် input layer ၏ column
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)
     - ``GEOMETRY``
     - [string]

       Default: 'geometry'
     - Dissolve ပြုလုပ်ခြင်းအတွက် အသုံးပြုမည့် input layer ဂျီဩမေတြီ column ၏ အမည်
   * - **Dissolved** (**Dissolve ပြုလုပ်ထားသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
         :start-after: **file_output_types**
         :end-before: **end_file_output_types**

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
   * - **Produce one feature for each geometry in any kind of
       geometry collection in the source file** (**မူရင်း file ထဲရှိ မည့်သည့် ဂျီဩမေတြီ စုစည်းခြင်းအမျိုးအစားထဲက ဂျီဩမေတြီ တစ်ခုချင်းစီအတွက် feature တစ်ခုကို ဖန်တီးခြင်း**)
     - ``EXPLODE_COLLECTIONS``
     - [boolean]

       Default: False
     - မူရင်း file ထဲရှိ မည်သည့် ဂျီဩမေတြီ စုစည်းခြင်းအမျိုးအစားထဲရှိ ဂျီဩမေတြီ တစ်ခုချင်းစီအတွက် feature တစ်ခုကို ဖန်တီးပေးပါသည်
   * - **Keep input attributes** (**Input attribute များကို ထိန်းထားခြင်း**)
     - ``KEEP_ATTRIBUTES``
     - [boolean]

       Default: False
     - Input layer မှ attribute များအားလုံးကို ထိန်းထားပေးပါသည်
   * - **Count dissolved features** (**Dissolve ပြုလုပ်ထားသော feature များကိုရေတွက်ခြင်း**)
     - ``COUNT_FEATURES``
     - [boolean]

       Default: False
     - Dissolve ပြုလုပ်ထားသော feature များကိုရေတွက်ပြီး output layer ထဲတွင် ၎င်းကိုထည့်သွင်းပေးပါသည်
   * - **Compute area and perimeter of dissolved features** (**Dissolve ပြုလုပ်ထားသော feature များ၏ ဧရိယာနှင့် ပတ်လည်အနားကို တွက်ချက်ခြင်း**)
     - ``COMPUTE_AREA``
     - [boolean]

       Default: False 
     - Dissolve ပြုလုပ်ထားသော feature များ၏ ဧရိယာနှင့် ပတ်လည်အနားကိုတွက်ချက်ပြီး ၎င်းတို့ကို output layer တွင်ထည့်သွင်းပေးပါသည်
   * - **Compute min/max/sum/mean for attribute** (**Attribute အတွက် အနည်းဆုံး/အများဆုံး/ပေါင်းလာဒ်/ပျမ်းမျှကိန်းတို့ကို တွက်ချက်ခြင်း**)
     - ``COMPUTE_STATISTICS``
     - [boolean]

       Default: False
     - ကိန်းဂဏန်း attribute အတွက် စာရင်းအင်းကိန်းဂဏန်း (အနည်းဆုံး/အများဆုံး/ပေါင်းလာဒ်/ပျမ်းမျှကိန်း) များကို တွက်ချက်ပြီး output layer တွင် ၎င်းတို့ကို ထည့်သွင်းပေးပါသည်
   * - **Numeric attribute to calculate statistics on** (**ကိန်းဂဏန်းများကိုတွက်ချက်ရန် ကိန်းဂဏန်း attribute**)
       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``STATISTICS_ATTRIBUTE``
     - [tablefield: numeric]
     - ကိန်းဂဏန်းများကိုတွက်ချက်ရန် ကိန်းဂဏန်း attribute
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Dissolved** (**Dissolve ပြုလုပ်ထားသော**)
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - အပိုင်းများစွာပါဝင်သော output ဂျီဩမေတြီ layer (Dissolve ပြုလုပ်ထားသော ဂျီဩမေတြီ များဖြင့်)

Python code
............

**Algorithm ID**: ``gdal:dissolve``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdaloffsetcurve:

Offset curve (အရွေ့ မျဉ်းကွေး)
-------------------------------

အတိအကျအကွာအဝေးတစ်ခုဖြင့် line များကို offset (ရွှေ့) လုပ်ပေးပါသည်။ အပေါင်းတန်ဖိုးဖြင့် အကွာအဝေးကို သတ်မှတ်လျှင် offset line သည် ဘယ်ဘက်ကိုရွေ့ပြီး အနှုတ်တန်ဖိုးဖြင့် အကွာအဝေးကို သတ်မှတ်လျှင် offset line သည် ညာဘက်ကိုရွေ့ပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line layer
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)
     - ``GEOMETRY``
     - [string]

       Default: 'geometry'
     - အသုံးပြုမည့် input layer ဂျီဩမေတြီ column ၏အမည်
   * - **Offset distance (left-sided: positive, right-sided: negative)** (**Offset အကွာအဝေး (ဘယ်ဘက် - အပေါင်း၊ ညာဘက် - အနှုတ်)**)
     - ``DISTANCE``
     - [number]

       Default: 10.0
     -
   * - **Offset curve** (**Offset မျဉ်းကွေး**)
     - ``OUTPUT``
     - [vector: line]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output line layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Offset curve**
     - ``OUTPUT``
     - [vector: line]
     - Output offset မျဉ်းကွေး layer

Python code
............

**Algorithm ID**: ``gdal:offsetcurve``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalonesidebuffer:

One side buffer (တစ်ဖက်တည်းသာ လုပ်သော buffer)
----------------------------------------------

Line vector layer တစ်ခုတွင် line များ၏တစ်ဖက်တွင် (ညာဘက် သို့မဟုတ် ဘယ်ဘက်) တွင် buffer တစ်ခုဖန်တီးပေးပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line layer
   * - **Geometry column name** (**ဂျီဩမေတြီ column အမည်**)
     - ``GEOMETRY``
     - [string]

       Default: 'geometry'
     - အသုံးပြုမည့် input layer ဂျီဩမေတြီ column ၏အမည်
   * - **Buffer distance** (**Buffer အကွာအဝေး**)
     - ``DISTANCE``
     - [number]

       Default: 10.0
     -
   * - **Buffer side** (**Buffer လုပ်ပေးသောဘက်**)
     - ``BUFFER_SIDE``
     - [enumeration]

       Default: 0
     - အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Right (ညာဘက်)
       * 1 --- Left (ဘယ်ဘက်)
   * - **Dissolve by attribute** (**Attribute ဖြင့် dissolve ပြုလုပ်ခြင်း**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``FIELD``
     - [tablefield: any]

       Default: None (ဘာမှသတ်မှတ်မထားပါ)
     - Dissolve ပြုလုပ်ခြင်းအတွက် အသုံးပြုမည့် column
   * - **Dissolve all results** (**ရလာဒ်များအားလုံးကို dissolve ပြုလုပ်ခြင်း**)
     - ``DISSOLVE``
     - [boolean]

       Default: False
     - သတ်မှတ်ထားလျှင် ရလာဒ်ကို dissolve ပြုလုပ်ပါသည်။ Dissolve ပြုလုပ်ခြင်းအတွက် column ကိုသတ်မှတ်မထားလျှင် buffer များအားလုံးကို feature တစ်ခုတည်းအဖြစ် dissolve ပြုလုပ်မည်ဖြစ်ပါသည်။
   * - **Produce one feature for each geometry in any kind of
       geometry collection in the source file** (**မူရင်း file ထဲရှိ မည်သည့် ဂျီဩမေတြီ စုစည်းခြင်းထဲတွင်မဆို ဂျီဩမေတြီ တစ်ခုချင်းစီအတွက် feature တစ်ခုဖန်တီးခြင်း**)
     - ``EXPLODE_COLLECTIONS``
     - [boolean]

       Default: False
     -
   * - **One-sided buffer**
     - ``OUTPUT``
     - [vector: polygon]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output buffer layer ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **One-sided buffer** (**တစ်ဘက်တည်းသာ လုပ်ထားသော buffer**)
     - ``OUTPUT``
     - [vector: polygon]
     - Output buffer layer

Python code
............

**Algorithm ID**: ``gdal:onesidebuffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _gdalpointsalonglines:

Points along lines (Line တစ်လျှောက်ရှိ point များ)
---------------------------------------------------

Line vector layer တစ်ခု၏ line တစ်ခုချင်းစီပေါ်တွင် အစမှတ်မှ အကွာအဝေးတစ်ခု၌ point တစ်ခုကိုဖန်တီးပေးပါသည်။ အကွာအဝေးကို line အလျား၏ အပိုင်းတစ်ခုအဖြစ် ထောက်ပံ့ပေးပါသည်။

Parameter များ
...............

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: line]
     - ထည့်သွင်းအသုံးပြုသော line layer
   * - **Geometry column name** (**ဂျီဩမေတြီ column နာမည်**)
     - ``GEOMETRY``
     - [string]

       Default: 'geometry'
     - အသုံးပြုမည့် input layer ဂျီဩမေတြီ column ၏အမည်
   * - **Distance from line start represented as a fraction of line length** (**Line အလျား၏ အပိုင်းတစ်ခုအဖြစ် ကိုယ်စားပြုသော line အစမှ အကွာအဝေး**)
     - ``DISTANCE``
     - [number]

       Default: 0.5 (Line ၏ အလယ်)
     -
   * - **Points along lines** (**Line တစ်လျှောက်ရှိ point များ**)
     - ``OUTPUT``
     - [vector: point]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Output point layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       .. include:: ../algs_include.rst
          :start-after: **file_output_types**
          :end-before: **end_file_output_types**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Additional creation options** (**ထပ်ဆောင်း ဖန်တီးခြင်း နည်းလမ်းများ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OPTIONS``
     - [string]

       Default: '' (အခြားထပ်ဆောင်းရွေးချယ်စရာ မရှိပါ)
     - ထပ်ဆောင်း GDAL ဖန်တီးခြင်း နည်းလမ်းများ


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Points along line** (**Line တစ်လျှောက်ရှိ point များ**)
     - ``OUTPUT``
     - [vector: point]
     - Output point layer

Python code
............

**Algorithm ID**: ``gdal:pointsalonglines``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
