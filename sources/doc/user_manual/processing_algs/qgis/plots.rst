Plots (အကွက်များ)
==================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisbarplot:

Bar plot (ဘား plot)
--------------------

အမျိုးအစား (category) တစ်ခု နှင့် layer field တစ်ခုမှ bar plot တစ်ခုကိုဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

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
   * - **Category field name** (**အမျိုးအစား field နာမည်**)
     - ``NAME_FIELD``
     - [tablefield: any]
     - Bar များ (X ဝင်ရိုး) ကိုအုပ်စုဖွဲ့ရန်အတွက် အသုံးပြုသော အမျိုးအစား field
   * - **Value field** (**တန်ဖိုး column**)
     - ``VALUE_FIELD``
     - [tablefield: any]
     - Plot (Y ဝင်ရိုး) အတွက်အသုံးပြုသော တန်ဖိုး
   * - **Bar plot**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Bar plot**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:barplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisboxplot:

Box plot (Data ကို ထောင့်မှန်စတုဂံပုံစံဖြင့် ပြသသော plot)
----------------------------------------------------------

အမျိုးအစား (category) field တစ်ခုနှင့် ကိန်းဂဏန်း layer field တစ်ခုမှ box plot တစ်ခုကိုဖန်တီးပေးပါသည်။

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
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Category name field** (**အမျိုးအစား အမည် field**)
     - ``NAME_FIELD``
     - [tablefield: any]
     - Box များ (X ဝင်ရိုး) ကိုအုပ်စုဖွဲ့ရန်အတွက် အသုံးပြုသော အမျိုးအစား field
   * - **Value field** (**တန်ဖိုး field**)
     - ``VALUE_FIELD``
     - [tablefield: any]
     - Plot (Y ဝင်ရိုး) အတွက်အသုံးပြုသော တန်ဖိုး
   * - **Additional statistic lines** (**ထပ်ဆောင်း စာရင်းအင်းကိန်းဂဏန်း line များ**)
     - ``MSD``
     - [enumeration]

       Default: 0
     - Plot ထဲကိုပေါင်းထည့်ရမည့် ထပ်ဆောင်း စာရင်းအင်းကိန်းဂဏန်း သတင်းအချက်အလက်များ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

       * 0 --- Show Mean (ပျမ်းမျှကိန်းကိုပြပါ)
       * 1 --- Show Standard Deviation (စံသွေဖယ်မှုကိုပြပါ)
       * 2 --- Don't show mean and standard deviation (ပျမ်းမျှကိန်းနှင့် စံသွေဖယ်မှုကို မပြပါနှင့်)

   * - **Box plot**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Box plot**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:boxplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgismeanandstandarddeviationplot:

Mean and standard deviation plot (ပျမ်းမျှကိန်းနှင့် စံသွေဖယ်မှု ပြသသော plot)
------------------------------------------------------------------------------

ပျမ်းမျှကိန်းနှင့် စံသွေဖယ်မှုတန်ဖိုးများဖြင့် box plot တစ်ခုကိုဖန်တီးပေးပါသည်။


Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input table** (**ထည့်သွင်းအသုံးပြုသော ဇယား**)
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Category name field** (**အမျိုးအစား အမည် field**)
     - ``NAME_FIELD``
     - [tablefield: any]
     - Box များ (X ဝင်ရိုး) ကိုအုပ်စုဖွဲ့ရန်အတွက် အသုံးပြုသော အမျိုးအစား field 
   * - **Value field** (**တန်ဖိုး field**)
     - ``VALUE_FIELD``
     - [tablefield: any]
     - Plot (Y ဝင်ရိုး) အတွက် အသုံးပြုမည့် တန်ဖိုး
   * - **Plot**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Plot**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:meanandstandarddeviationplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispolarplot:

Polar plot (Data ကို ဝင်ရိုးမှဖြန့်ကျက်ပြသသော plot)
----------------------------------------------------

Input vector layer တစ်ခု၏တန်ဖိုးပေါ် အခြေခံပြီး polar plot တစ်ခုကိုဖန်တီးပေးပါသည်။

Field နှစ်ခုကို parameter များအဖြစ် ထည့်သွင်းရပါမည် - Parameter တစ်ခုသည် feature တစ်ခုချင်းစီ (feature များကိုအုပ်စုဖွဲ့ရန်) ၏အမျိုးအစားကို သတ်မှတ်ပေးသောတစ်ခုဖြစ်ပြီး parameter နောက်တစ်ခုသည် plot ပြုလုပ်ရန် variable (ကိန်းရှင်) ပါဝင်သောတစ်ခု (ကိန်းဂဏန်းဖြစ်ရပါမည်) ဖြစ်ပါသည်။

Parameters (Parameter များ)
............................

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
   * - **Category name field** (**အမျိုးအစား အမည် field**)
     - ``NAME_FIELD``
     - [tablefield: any]
     - Feature များ (X ဝင်ရိုး) များကိုအုပ်စုဖွဲ့ခြင်းအတွက် အသုံးပြုသော အမျိုးအစား field
   * - **Value field** (**တန်ဖိုး field**)
     - ``VALUE_FIELD``
     - [tablefield: any]
     - Plot (Y ဝင်ရိုး) အတွက် အသုံးပြုသော တန်ဖိုး
   * - **Polar plot**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Polar plot**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:polarplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrasterlayerhistogram:

Raster layer histogram (Raster layer ကြိမ်နှုန်းပြဂရပ်)
--------------------------------------------------------

Raster layer တစ်ခု၏ တန်ဖိုးများပါဝင်သော histogram တစ်ခုကို ဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** (**ထည့်သွင်းအသုံးပြုသော layer**)
     - ``INPUT``
     - [raster]
     - ထည့်သွင်းအသုံးပြုသော raster layer
   * - **Band number** (**Band နံပါတ်**)
     - ``BAND``
     - [raster band]
     - Histogram အတွက်အသုံးပြုမည့် raster band
   * - **number of bins** (**အုပ်စုအရေအတွက်**)
     - ``BINS``
     - [number]

       Default: 10
     - Histogram (X ဝင်ရိုး) ထဲတွင် အသုံးပြုမည့် အုပ်စုအရေအတွက်။ အနည်းဆုံး အရေအတွက် - 2
   * - **Histogram**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Histogram**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:rasterlayerhistogram``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisvectorlayerhistogram:

Vector layer histogram (Vector layer ကြိမ်နှုန်းပြဂရပ်)
--------------------------------------------------------

Vector layer တစ်ခု၏ attribute တန်ဖိုးများပါဝင်သော histogram တစ်ခုကိုဖန်တီးပေးပါသည်။

Histogram ကိုတွက်ချက်ခြင်းအတွက် အသုံးပြုမည့် attribute များသည် ကိန်းဂဏန်းဖြစ်ရပါမည်။

Parameters (Parameter များ)
............................

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
   * - **Attribute** (**အချက်အလက်များ**)
     - ``FIELD``
     - [tablefield: any]
     - Plot (Y ဝင်ရိုး) အတွက် အသုံးပြုမည့် တန်ဖိုး
   * - **number of bins** (**အုပ်စုအရေအတွက်**)
     - ``BINS``
     - [number]

       Default: 10
     - Histogram (X ဝင်ရိုး) ထဲတွင် အသုံးပြုမည့် အုပ်စုအရေအတွက်။ အနည်းဆုံး အရေအတွက် - 2
   * - **Histogram**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Histogram**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:vectorlayerhistogram``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisvectorlayerscatterplot:

Vector layer scatterplot (Vector layer အတွက် ကိန်းရှင်နှစ်ခုကြားဆက်နွယ်မှုပြသသော plot )
----------------------------------------------------------------------------------------

Vector layer တစ်ခုအတွက် ရိုးရှင်းသော ``X`` - ``Y`` scatter plot တစ်ခုဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

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
   * - **X attribute** (**X အချက်အလက်**)
     - ``XFIELD``
     - [tablefield: any]
     - X ဝင်ရိုးအတွက် အသုံးပြုမည့် field
   * - **Y attribute** (**Y အချက်အလက်**)
     - ``YFIELD``
     - [tablefield: any]
     - Y ဝင်ရိုးအတွက် အသုံးပြုမည့် field
   * - **Scatterplot**
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - Plot အတွက် HTML file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Scatterplot**
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:vectorlayerscatterplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisscatter3dplot:

Vector layer scatterplot 3D (သုံးဘက်မြင် vector layer scatterplot)
-------------------------------------------------------------------

Vector layer တစ်ခုအတွက် 3D scatter plot တစ်ခုဖန်တီးပေးပါသည်။

Parameters (Parameter များ)
............................

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
   * - **X attribute** (**X အချက်အလက်**)
     - ``XFIELD``
     - [tablefield: any]
     - X ဝင်ရိုးအတွက် အသုံးပြုမည့် field
   * - **Y attribute** (**Y အချက်အလက်**)
     - ``YFIELD``
     - [tablefield: any]
     - Y ဝင်ရိုးအတွက် အသုံးပြုမည့် field
   * - **Z attribute** (**Z အချက်အလက်**)
     - ``ZFIELD``
     - [tablefield: any]
     - Z ဝင်ရိုးအတွက် အသုံးပြုမည့် field
   * - **Histogram** (**ကြိမ်နှုန်းပြဂရပ်**)
     - ``OUTPUT``
     - [html]

       Default: ``[Save to temporary file]``
     - Plot အတွက် HTML file ကိုသတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် -

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
   * - **Histogram** (**ကြိမ်နှုန်းပြဂရပ်**)
     - ``OUTPUT``
     - [html]
     - Plot ပါဝင်သော HTML file ။ :menuselection:`Processing --> Result Viewer` ထဲတွင်ရှိပါသည်။

Python code
............

**Algorithm ID**: ``qgis:scatter3dplot``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
