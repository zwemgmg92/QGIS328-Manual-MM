Vector selection (Vector ရွေးချယ်ခြင်း)
========================================

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _qgisextractbyattribute:

Extract by attribute (Attribute (အချက်အလက်)ဖြင့် ထုတ်ယူခြင်း)
--------------------------------------------------------------

Input layer တစ်ခုမှ vector layer နှစ်ခု ကိုဖန်တီးပေးပါသည် - ပထမတစ်ခုတွင် ကိုက်ညီမှုရှိသော feature များသာပါဝင်ပြီး ဒုတိယတစ်ခုတွင် ကိုက်ညီမှုမရှိသော feature များအားလုံးပါဝင်ပါသည်။

ရလာဒ်ထုတ်ပေးသည့် layer တွင် feature များထည့်သွင်းခြင်းအတွက် စံသတ်မှတ်ချက်သည် input layer မှ attribute တစ်ခု၏ တန်ဖိုးများအပေါ် အခြေခံပါသည်။

.. seealso:: :ref:`qgisselectbyattribute`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များ ထုတ်ယူရန် Layer။
   * - **Selection attribute** **(ရွေးချယ်မှု အချက်အလက်)**
     - ``FIELD``
     - [tablefield: any]
     - Layer ၏ filter (စစ်ထုတ်) သော field  
   * - **Operator** **(+ - * / စသည့်သင်္ကေတ)**
     - ``OPERATOR``
     - [enumeration]

       Default: 0
     - အမျိုးမျိုးသော operator (သင်္ချာဆိုင်ရာ သို့မဟုတ် လော့ဂျစ်ဆိုင်ရာလုပ်ဆောင်ချက်များကို ကိုယ်စားပြုသည့်အရာ) များကို အသုံးပြုနိုင်ပါသည်-

       * 0 --- = (ညီမျှသော)
       * 1 --- ≠ (မညီမျှသော)
       * 2 --- > (..ထက်ကြီးသော)
       * 3 --- >= (..ထက်ကြီးပြီး၊ ..နှင့်ညီမျှသော)
       * 4 --- < (..ထက်ငယ်သော)
       * 5 --- <= (..ထက်ငယ်ပြီး၊ ..နှင့်ညီမျှသော)
       * 6 --- begins with (..ဖြင့်စတင်သော)
       * 7 --- contains (..ပါဝင်သော)
       * 8 --- is null (Null တန်ဖိုးဖြစ်သော)
       * 9 --- is not null (Null တန်ဖိုးမဟုတ်သော)
       * 10 --- does not contain (..မပါဝင်သော)

   * - **Value** **(တန်ဖိုး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``VALUE``
     - [string]
     - အကဲဖြတ်ရန် တန်ဖိုး 
   * - **Extracted (attribute)** **(ထုတ်ယူထားသော (အချက်အလက်))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create Temporary Layer]``
     - ကိုက်ညီမှုရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

   * - **Extracted (non-matching)** **(ထုတ်ယူထားသော (ကိုက်ညီမှုမရှိသော))**
     - ``FAIL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ကိုက်ညီမှုမရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Extracted (attribute)** **(ထုတ်ယူထားသော (အချက်အလက်))** 
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကိုက်ညီမှုရှိသော feature များပါဝင်သည့် vector layer 
   * - **Extracted (non-matching)** **(ထုတ်ယူထားသော (ကိုက်ညီမှုမရှိသော))**
     - ``FAIL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကိုက်ညီမှုမရှိသော feature များပါဝင်သည့် vector layer

Python code
............

**Algorithm ID**: ``qgis:extractbyattribute``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractbyexpression:

Extract by expression (Expression ဖြင့် ထုတ်ယူခြင်း)
-----------------------------------------------------

Input layer တစ်ခုမှ vector layer နှစ်ခု ကိုဖန်တီးပေးပါသည် - ပထမတစ်ခုတွင် ကိုက်ညီမှုရှိသော feature များသာပါဝင်ပြီး ဒုတိယတစ်ခုတွင် ကိုက်ညီမှုမရှိသော feature များအားလုံးပါဝင်ပါသည်။

ရလာဒ်ထုတ်ပေးသည့် layer တွင် feature များထည့်သွင်းခြင်းအတွက် စံသတ်မှတ်ချက်သည် QGIS expression တစ်ခုအပေါ် အခြေခံပါသည်။ Expression အကြောင်းကို ပိုမိုသိရှိရန်အတွက် :ref:`vector_expressions` တွင်ကြည့်ပါ။

.. seealso:: :ref:`qgisselectbyexpression`

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
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Expression**
     - ``EXPRESSION``
     - [expression]
     - Vector layer ကို စစ်ထုတ် (filter) ရန် expression
   * - **Matching features** **(ကိုက်ညီမှုရှိသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create Temporary Layer]``
     - ကိုက်ညီမှုရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types**
          :end-before: **end_layer_output_types**

   * - **Non-matching** **(ကိုက်ညီမှုမရှိသော)**
     - ``FAIL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Skip output]``
     - ကိုက်ညီမှုမရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **layer_output_types_skip**
          :end-before: **end_layer_output_types_skip**

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Matching features** **(ကိုက်ညီမှုရှိသော feature များ)**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကိုက်ညီမှုရှိသော feature များပါဝင်သည့် vector layer
   * - **Non-matching** **(ကိုက်ညီမှုမရှိသော)**
     - ``FAIL_OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကိုက်ညီမှုမရှိသော feature များပါဝင်သည့် vector layer

Python code
...........

**Algorithm ID**: ``qgis:extractbyexpression``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractbylocation:

Extract by location (တည်နေရာဖြင့် ထုတ်ယူခြင်း)
-----------------------------------------------

Input layer တစ်ခုမှ ကိုက်ညီမှုရှိသော feature များသာ ပါဝင်သော vector layer အသစ်တစ်ခု ဖန်တီးပေးပါသည်။

ရလာဒ် layer တွင် feature များထည့်သွင်းခြင်းအတွက် စံသတ်မှတ်ချက်သည် feature တစ်ခုချင်းစီနှင့် ထပ်ဆောင်း layer တစ်ခုထဲရှိ feature များအကြားရှိ တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relationship) အပေါ်တွင် အခြေခံပါသည်။

.. seealso:: :ref:`qgisselectbylocation` ၊ :ref:`qgisextractwithindistance`

Exploring spatial relations (တည်နေရာဆိုင်ရာဆက်နွယ်မှုကို လေ့လာခြင်း)
.....................................................................

.. include:: ../algs_include.rst
   :start-after: **geometric_predicates**
   :end-before: **end_geometric_predicates**

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
   * - **Extract features from** **(Feature များထုတ်ယူမည့် layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Where the features (geometric predicate)**
     - ``PREDICATE``
     - [enumeration] [list]

       Default: [0]
     - ရွေးချယ်ခြင်းပြုနိုင်စေရန်အတွက် Input feature တွင် ရှိသင့်သည့် intersect feature တစ်ခုနှင့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relation) အမျိုးအစား။ အောက်ပါတို့အနက်မှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်နိုင်ပါသည်-

       * 0 --- intersect (ထိဖြတ်သော)
       * 1 --- contain (ပါဝင်သော)
       * 2 --- disjoint (ချိတ်ဆက်မှုမရှိသော)
       * 3 --- equal (ညီမျှသော)
       * 4 --- touch (ထိစပ်နေသော)
       * 5 --- overlap (ထပ်နေသော)
       * 6 --- are within (အတွင်းတွင်ကျရောက်သော)
       * 7 --- cross (တစ်ခုနှင့်တစ်ခုဖြတ်သွားသော)

       အခြေအနေတစ်ခုထက်ပို၍ ရွေးချယ်ခဲ့ပါက ၎င်းတို့အနက်မှ အနည်းဆုံးတစ်ခု (OR operation) သည် feature တစ်ခုထုတ်ယူရန်အတွက် ကိုက်ညီနေရမည်ဖြစ်သည်။
   * - **By comparing to the features from** 
     - ``INTERSECT``
     - [vector: any]
     - ထိဖြတ်ခြင်း vector layer
   * - **Extracted (location)** **(ထုတ်ယူပြီးသော (တည်နေရာ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - နှိုင်းယှဉ်ခြင်း layer ထဲရှိ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော feature များဖြင့် ရွေးချယ်ထားသည့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relationship) ရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Extracted (location)** **(ထုတ်ယူပြီးသော (တည်နေရာ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - နှိုင်းယှဉ်ခြင်း layer ထဲရှိ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော feature များဖြင့် ရွေးချယ်ထားသည့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relationship) ရှိသော input layer မှ feature များပါဝင်သည့် vector layer။

Python code
...........

**Algorithm ID**: ``qgis:extractbylocation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisextractwithindistance:

Extract within distance (အကွာအဝေးအတွင်း ထုတ်ယူခြင်း)
-----------------------------------------------------

Input layer တစ်ခုမှ ကိုက်ညီမှုရှိသော feature များသာ ပါဝင်သော vector layer အသစ်တစ်ခု ဖန်တီးပေးပါသည်။ ထပ်ဆောင်း ရည်ညွှန်း layer တစ်ခုထဲရှိ feature များမှ တိတိကျကျသတ်မှတ်ထားသော အများဆုံးအကွာအဝေး အတွင်းတွင် ရှိနေသည့်အခါတိုင်းတွင် feature များကို မိတ္တူကူးယူပေးမည် ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisselectwithindistance` ၊ :ref:`qgisextractbylocation`

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
   * - **Extract features from** **(Feature များထုတ်ယူမည့် layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များကို မိတ္တူကူးမည့် input vector layer 
   * - **By comparing to the features from**
     - ``REFERENCE``
     - [vector: any]
     - နီးစပ်မှု (closeness) အတွက်အသုံးပြုမည့် feature များပါဝင်သော Vector layer ။ 
   * - **Where the features are within**
     - ``DISTANCE``
     - [number]

       Default: 100
     - ရည်ညွှန်း feature များ ပတ်လည်ရှိ အများဆုံး အကွာအဝေး။ ထိုအကွာအဝေးအတွင်းတွင် ရှိသော input feature များကို ရွေးချယ်မည်ဖြစ်သည်။
   * - **Modify current selection by**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - Algorithm ၏ ရွေးချယ်ခြင်းကို မည်သို့စီမံသင့်သည်ကို ရွေးချယ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- creating new selection (ရွေးချယ်ခြင်းအသစ် ဖန်တီးခြင်း)
       * 1 --- adding to current selection (လက်ရှိရွေးချယ်ခြင်းထဲသို့ ပေါင်းထည့်ခြင်း)
       * 2 --- selecting within current selection (လက်ရှိရွေးချယ်ထားခြင်းထဲတွင် ရွေးချယ်ခြင်း)
       * 3 --- removing from current selection (လက်ရှိရွေးချယ်ထားခြင်းမှ ဖယ်ရှားခြင်း)
   * - **Extracted (location)** **(ထုတ်ယူထားပြီးသော (တည်နေရာ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ရည်ညွှန်း feature များမှ သတ်မှတ်ထားသော အကွာအဝေးအတွင်းရှိသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Extracted (location)** **(ထုတ်ယူထားပြီးသော (တည်နေရာ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရည်ညွှန်း feature များမှ အကွာအဝေးအခြေအနေနှင့် ကိုက်ညီသော input layer မှ
       feature များပါဝင်သည့် vector layer။

Python code
...........

**Algorithm ID**: ``native:extractwithindistance``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfilterbygeometry:

Filter by geometry type (ဂျီဩမေတြီ အမျိုးအစားများဖြင့် စစ်ထုတ်ခြင်း)
---------------------------------------------------------------------

Feature များကို ၎င်းတို့၏ ဂျီဩမေတြီအမျိုးအစားဖြင့် စစ်ထုတ်မည်ဖြစ်ပါသည်။ ဝင်ရောက်လာသော feature များကို ၎င်းတို့တွင် point တစ်ခု ၊ line သို့မဟုတ် polygon ဂျီဩမေတြီ ရှိခြင်း မရှိခြင်း အပေါ်တွင်အခြေခံပြီး ရလာဒ်အမျိုးမျိုး ထုတ်ပေးမည် ဖြစ်ပါသည်။

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
     - အကဲဖြတ်ရန် layer

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Point features**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``POINTS``
     - [vector: point]
     - Point များပါသည့် layer
   * - **Line features**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``LINES``
     - [vector: line]
     - Line များပါသည့် layer 
   * - **Polygon features**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``POLYGONS``
     - [vector: polygon]
     - Polygon များပါသည့် layer
   * - **Features with no geometry**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``NO_GEOMETRY``
     - [table]
     - ဂျီဩမေတြီများမပါဝင်သော (Geometry-less) vector layer

Python code
...........

**Algorithm ID**: ``native:filterbygeometry``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrandomextract:

Random extract (ကျပန်း ထုတ်ယူခြင်း)
-----------------------------------

Vector layer တစ်ခုကို ယူပြီး input layer ထဲရှိ feature များအစု (subset) တစ်ခုသာလျှင် ပါဝင်သည့် layer အသစ်တစ်ခုကို ထုတ်ပေးပါသည်။

အစု (subset) ကို feature ID များအပေါ်တွင် အခြေခံပြီး ကျပန်းသတ်မှတ်ပါသည်။ အစုထဲရှိ စုစုပေါင်း feature အရေအတွက်ကို သတ်မှတ်ရန် ရာခိုင်နှုန်း (percentage) သို့မဟုတ် အရေအတွက် (count) တန်ဖိုးတစ်ခုကို အသုံးပြုပါသည်။

.. seealso:: :ref:`qgisrandomselection`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များကို ရွေးချယ်ရန် ရင်းမြစ် vector layer
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - ကျပန်းရွေးချယ်ခြင်း နည်းလမ်းများ။ အောက်ပါတို့အနက်မှ တစ်ခုဖြစ်ပါသည်- 

       * 0 --- ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်
       * 1 --- ရွေးချယ်ထားသည့် feature များ၏ ရာခိုင်နှုန်း

   * - **Number/percentage of selected features** **(ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်/ရာခိုင်နှုန်း)**
     - ``NUMBER``
     - [number]

       Default: 10
     - ရွေးချယ်ရန် feature များ၏ အရေအတွက် သို့မဟုတ် ရာခိုင်နှုန်း
   * - **Extracted (random)** **(ထုတ်ယူထားပြီးသော (ကျပန်း))**
     - ``OUTPUT``
     - [vector: any]

       Default: ``[Create temporary layer]``
     - ကျပန်းရွေးချယ်ထားသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Extracted (random)** **(ထုတ်ယူထားပြီးသော (ကျပန်း))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကျပန်းရွေးချယ်ထားသည့် feature များပါဝင်သည့် vector layer 

Python code
...........

**Algorithm ID**: ``qgis:randomextract``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrandomextractwithinsubsets:

Random extract within subsets (Subset များအတွင်း ကျပန်းထုတ်ယူခြင်း)
--------------------------------------------------------------------

Vector layer တစ်ခုကို ယူပြီး input layer ထဲရှိ feature များအစု (subset) တစ်ခုသာလျှင်
ပါဝင်သည့် layer အသစ်တစ်ခုကို ထုတ်ပေးပါသည်။

အစု (subset) ကို feature ID များအပေါ်တွင် အခြေခံပြီး ကျပန်းသတ်မှတ်ပါသည်။ အစုထဲရှိ စုစုပေါင်း feature အရေအတွက်ကို သတ်မှတ်ရန် ရာခိုင်နှုန်း (percentage) သို့မဟုတ် အရေအတွက် (count) တန်ဖိုးတစ်ခုကို အသုံးပြုပါသည်။ ရာခိုင်နှုန်း/အရေအတွက် တန်ဖိုးကို layer တစ်ခုလုံးအတွက် အသုံးပြုမည်မဟုတ်ပါ၊ သို့သော် အမျိုးအစား (category) တစ်ခုချင်းစီတွင် အသုံးပြုသွားမည်ဖြစ်သည်။ အမျိုးအစား (category) များကို ပေးထားသည့် အချက်အလက် (attribute) တစ်ခုအရ သတ်မှတ်ပါသည်။

.. seealso:: :ref:`qgisrandomselectionwithinsubsets`

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
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များကို ရွေးချယ်ရန် vector layer
   * - **ID field**
     - ``FIELD``
     - [tablefield: any]
     - Feature များကို ရွေးချယ်ရန် ရင်းမြစ် vector layer ၏ အမျိုးအစား (category)  
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - ကျပန်းရွေးချယ်ခြင်း နည်းလမ်း။ အောက်ပါတို့အနက်မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်
       * 1 --- ရွေးချယ်ထားသည့် feature များ၏ ရာခိုင်နှုန်း

   * - **Number/percentage of selected features** **(ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်/ရာခိုင်နှုန်း)**
     - ``NUMBER``
     - [number]

       Default: 10
     - ရွေးချယ်ရန် feature များ၏ အရေအတွက် သို့မဟုတ် ရာခိုင်နှုန်း
   * - **Extracted (random stratified)** **(ထုတ်ယူထားပြီးသော (ကျပန်းအလွှာခွဲ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]

       Default: ``[Create temporary layer]``
     - ကျပန်းရွေးချယ်ထားသော feature များအတွက် output vector layer ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုဖြစ်ပါသည်-

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
   * - **Extracted (random stratified)** **(ထုတ်ယူထားပြီးသော (ကျပန်းအလွှာခွဲ))**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Input layer မှ ကျပန်းရွေးချယ်ထားသည့် feature များပါဝင်သည့် vector layer

Python code
...........

**Algorithm ID**: ``qgis:randomextractwithinsubsets``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrandomselection:

Random selection (ကျပန်းရွေးချယ်ခြင်း)
---------------------------------------

Vector layer တစ်ခုကို ယူပြီး ၎င်း feature များ၏ အစု (subset) တစ်ခုကို ရွေးချယ်ပေးပါသည်။ ဤ algorithm သည် layer အသစ်တစ်ခု ထုတ်ပေးမည် မဟုတ်ပါ။

အစု (subset) ကို feature ID များအပေါ်တွင် အခြေခံပြီး ကျပန်းသတ်မှတ်ပါသည်။ အစုထဲရှိ စုစုပေါင်း feature အရေအတွက်ကို သတ်မှတ်ရန် ရာခိုင်နှုန်း (percentage) သို့မဟုတ် အရေအတွက် (count) တန်ဖိုးတစ်ခုကို အသုံးပြုပါသည်။

**Default menu** - :menuselection:`Vector --> Research Tools`

.. seealso:: :ref:`qgisrandomextract`

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
     - ရွေးချယ်ခြင်းများအတွက် vector layer
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - ကျပန်းရွေးချယ်ခြင်း နည်းလမ်း။ အောက်ပါတို့အနက်မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်
       * 1 --- ရွေးချယ်ထားသည့် feature များ၏ ရာခိုင်နှုန်း

   * - **Number/percentage of selected features** **(ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်/ရာခိုင်နှုန်း)**
     - ``NUMBER``
     - [number]

       Default: 10
     - ရွေးချယ်ရန် feature များ၏ အရေအတွက် သို့မဟုတ် ရာခိုင်နှုန်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer 

Python code
...........

**Algorithm ID**: ``qgis:randomselection``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrandomselectionwithinsubsets:

Random selection within subsets (Subset များအတွင်း ကျပန်းရွေးချယ်ခြင်း)
------------------------------------------------------------------------

Vector layer တစ်ခုကို ယူပြီး ၎င်း feature များ၏ အစု (subset) တစ်ခုကို ရွေးချယ်ပေးပါသည်။ ဤ algorithm သည် layer အသစ်တစ်ခု ထုတ်ပေးမည် မဟုတ်ပါ။

အစု (subset) ကို feature ID များအပေါ်တွင် အခြေခံပြီး ကျပန်းသတ်မှတ်ပါသည်။ အစုထဲရှိ စုစုပေါင်း feature အရေအတွက်ကို သတ်မှတ်ရန် ရာခိုင်နှုန်း (percentage) သို့မဟုတ် အရေအတွက် (count) တန်ဖိုးတစ်ခုကို အသုံးပြုပါသည်။

ရာခိုင်နှုန်း/အရေအတွက် တန်ဖိုးကို layer တစ်ခုလုံးအတွက် အသုံးပြုမည်မဟုတ်ပါ၊ သို့သော် အမျိုးအစား (category) တစ်ခုချင်းစီတွင် အသုံးပြုသွားမည်ဖြစ်သည်။

ပေးထားသည့် အချက်အလက် (attribute) တစ်ခုအရ အမျိုးအစား (category) များကို သတ်မှတ်မည်ဖြစ်ပြီး ၎င်းကို algorithm အတွက် input parameter တစ်ခုအဖြစ်လည်း သတ်မှတ်မည် ဖြစ်သည်။

Output အသစ်များကို ဖန်တီးမည် မဟုတ်ပါ။

**Default menu** - :menuselection:`Vector --> Research Tools`

.. seealso:: :ref:`qgisrandomextractwithinsubsets`

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
     - Feature များ ရွေးချယ်မည့် vector layer
   * - **ID field**
     - ``FIELD``
     - [tablefield: any]
     - Feature များရွေးချယ်မည့် input layer ၏ အမျိုးအစား (category) 
   * - **Method** **(နည်းလမ်း)**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - ကျပန်းရွေးချယ်ခြင်း နည်းလမ်း။ အောက်ပါတို့အနက်မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်
       * 1 --- ရွေးချယ်ထားသည့် feature များ၏ ရာခိုင်နှုန်း

   * - **Number/percentage of selected features** **(ရွေးချယ်ထားသည့် feature များ၏ အရေအတွက်/ရာခိုင်နှုန်း)**
     - ``NUMBER``
     - [number]

       Default: 10
     - ရွေးချယ်ရန် feature များ၏ အရေအတွက် သို့မဟုတ် ရာခိုင်နှုန်း

Outputs (ရလာဒ်များ)
....................
.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer

Python code
...........

**Algorithm ID**: ``qgis:randomselectionwithinsubsets``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisselectbyattribute:

Select by attribute (အချက်အလက် (attribute)ဖြင့် ရွေးချယ်ခြင်း)
---------------------------------------------------------------

Vector layer တစ်ခုထဲတွင် ရွေးချယ်ခြင်းတစ်ခု ဖန်တီးပေးပါသည်။

Feature များ ရွေးချယ်ခြင်းအတွက် စံသတ်မှတ်ချက်သည် input layer မှ အချက်အလက်တစ်ခု၏ တန်ဖိုးများအပေါ်တွင် အခြေခံပါသည်။

.. seealso:: :ref:`qgisextractbyattribute`

Parameters (Parameter များ)
...........................

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
     - Feature များ ရွေးချယ်မည့် vector layer
   * - **Selection attribute** **(ရွေးချယ်ခြင်း အချက်အလက်)**
     - ``FIELD``
     - [tablefield: any]
     - Layer ၏ စစ်ထုတ် (filter) သော field
   * - **Operator** **(+ - * / စသည့်သင်္ကေတ)**
     - ``OPERATOR``
     - [enumeration]

       Default: 0
     - အမျိုးမျိုးသော operator (သင်္ချာဆိုင်ရာ သို့မဟုတ် လော့ဂျစ်ဆိုင်ရာလုပ်ဆောင်ချက်များကို ကိုယ်စားပြုသည့်အရာ) များကို အသုံးပြုနိုင်ပါသည်-

       * 0 --- = (ညီမျှသော)
       * 1 --- ≠ (မညီမျှသော)
       * 2 --- > (..ထက်ကြီးသော)
       * 3 --- >= (..ထက်ကြီးပြီး၊ ..နှင့်ညီမျှသော)
       * 4 --- < (..ထက်ငယ်သော)
       * 5 --- <= (..ထက်ငယ်ပြီး၊ ..နှင့်ညီမျှသော)
       * 6 --- begins with (..ဖြင့်စတင်သော)
       * 7 --- contains (..ပါဝင်သော)
       * 8 --- is null (Null တန်ဖိုးဖြစ်သော)
       * 9 --- is not null (Null တန်ဖိုးမဟုတ်သော)
       * 10 --- does not contain (..မပါဝင်သော)

   * - **Value** **(တန်ဖိုး)**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန်မလိုပါ)
     - ``VALUE``
     - [string]
     - အကဲဖြတ်ရန် တန်ဖိုး
   * - **Modify current selection by**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - Algorithm ၏ ရွေးချယ်ခြင်းကို မည်သို့စီမံသင့်သည်ကို ရွေးချယ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- creating new selection (ရွေးချယ်ခြင်းအသစ် ဖန်တီးခြင်း)
       * 1 --- adding to current selection (လက်ရှိရွေးချယ်ခြင်းထဲသို့ ပေါင်းထည့်ခြင်း)
       * 2 --- removing from current selection (လက်ရှိရွေးချယ်ထားခြင်းမှ ဖယ်ရှားခြင်း)
       * 3 --- selecting within current selection (လက်ရှိရွေးချယ်ထားခြင်းထဲတွင် ရွေးချယ်ခြင်း)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer 

Python code
...........

**Algorithm ID**: ``qgis:selectbyattribute``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisselectbyexpression:

Select by expression (Expression ဖြင့် ရွေးချယ်ခြင်း)
------------------------------------------------------

Vector layer တစ်ခုထဲတွင် ရွေးချယ်မှုတစ်ခုကို ဖန်တီးပေးပါသည်။

Feature များရွေးချယ်ခြင်းအတွက် စံသတ်မှတ်ချက်သည် QGIS expression တစ်ခုပေါ်တွင် အခြေခံပါသည်။ Expression နှင့်ပတ်သက်၍ ပိုမိုသိရှိလိုပါက :ref:`vector_expressions` တွင် လေ့လာနိုင်ပါသည်။

.. seealso:: :ref:`qgisextractbyexpression`

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
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Expression**
     - ``EXPRESSION``
     - [expression]
     - Input layer ကို စစ်ထုတ် (filter) ရန် Expression
   * - **Modify current selection by**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - Algorithm ၏ ရွေးချယ်ခြင်းကို မည်သို့စီမံသင့်သည်ကို ရွေးချယ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- creating new selection (ရွေးချယ်ခြင်းအသစ် ဖန်တီးခြင်း)
       * 1 --- adding to current selection (လက်ရှိရွေးချယ်ခြင်းထဲသို့ ပေါင်းထည့်ခြင်း)
       * 2 --- removing from current selection (လက်ရှိရွေးချယ်ထားခြင်းမှ ဖယ်ရှားခြင်း)
       * 3 --- selecting within current selection (လက်ရှိရွေးချယ်ထားခြင်းထဲတွင် ရွေးချယ်ခြင်း)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer

Python code
...........

**Algorithm ID**: ``qgis:selectbyexpression``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisselectbylocation:

Select by location (တည်နေရာဖြင့် ရွေးချယ်ခြင်း)
------------------------------------------------

Vector layer တစ်ခုထဲတွင် ရွေးချယ်မှုတစ်ခုကို ဖန်တီးပေးပါသည်။

Feature များရွေးချယ်ခြင်းအတွက် စံသတ်မှတ်ချက်သည် feature တစ်ခုချင်းစီနှင့် ထပ်ဆောင်း layer တစ်ခုထဲရှိ feature များအကြားရှိ တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relationship) အပေါ် အခြေခံပါသည်။

**Default menu** - :menuselection:`Vector --> Research Tools`

.. seealso:: :ref:`qgisextractbylocation` ၊ :ref:`qgisselectwithindistance`

Exploring spatial relations (တည်နေရာဆိုင်ရာဆက်နွယ်မှုကို လေ့လာခြင်း)
.....................................................................

.. include:: ../algs_include.rst
   :start-after: **geometric_predicates**
   :end-before: **end_geometric_predicates**

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
   * - **Select features from** **(Feature များရွေးချယ်မည့် layer)**
     - ``INPUT``
     - [vector: any]
     - ထည့်သွင်းအသုံးပြုသော vector layer
   * - **Where the features (geometric predicate)**
     - ``PREDICATE``
     - [enumeration] [list]

       Default: [0]
     - ရွေးချယ်ခြင်းပြုနိုင်စေရန်အတွက် Input feature တွင် ရှိသင့်သည့် intersect feature တစ်ခုနှင့် တည်နေရာဆိုင်ရာဆက်နွယ်မှု (spatial relation) အမျိုးအစား။ အောက်ပါတို့အနက်မှ တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ရွေးချယ်နိုင်ပါသည်-

       * 0 --- intersect (ထိဖြတ်သော)
       * 1 --- contain (ပါဝင်သော)
       * 2 --- disjoint (ချိတ်ဆက်မှုမရှိသော)
       * 3 --- equal (ညီမျှသော)
       * 4 --- touch (ထိစပ်နေသော)
       * 5 --- overlap (ထပ်နေသော)
       * 6 --- are within (အတွင်းတွင်ကျရောက်သော)
       * 7 --- cross (တစ်ခုနှင့်တစ်ခုဖြတ်သွားသော)

       အခြေအနေတစ်ခုထက်ပို၍ ရွေးချယ်ခဲ့ပါက ၎င်းတို့အနက်မှ အနည်းဆုံးတစ်ခု (OR operation) သည် feature တစ်ခုထုတ်ယူရန်အတွက် ကိုက်ညီနေရမည်ဖြစ်သည်။
   * - **By comparing to the features from** 
     - ``INTERSECT``
     - [vector: any]
     - ထိဖြတ်ခြင်း vector layer
   * - **Modify current selection by**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - Algorithm ၏ ရွေးချယ်ခြင်းကို မည်သို့စီမံသင့်သည်ကို ရွေးချယ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- creating new selection (ရွေးချယ်ခြင်းအသစ် ဖန်တီးခြင်း)
       * 1 --- adding to current selection (လက်ရှိရွေးချယ်ခြင်းထဲသို့ ပေါင်းထည့်ခြင်း)
       * 2 --- selecting within current selection (လက်ရှိရွေးချယ်ထားခြင်းထဲတွင် ရွေးချယ်ခြင်း)
       * 3 --- removing from current selection (လက်ရှိရွေးချယ်ထားခြင်းမှ ဖယ်ရှားခြင်း)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer 

Python code
...........

**Algorithm ID**: ``qgis:selectbylocation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisselectwithindistance:

Select within distance (အကွာအဝေးအတွင်း ရွေးချယ်ခြင်း)
------------------------------------------------------

Vector layer တစ်ခုထဲတွင် ရွေးချယ်မှုတစ်ခုကို ဖန်တီးပေးပါသည်။ ထပ်ဆောင်း ရည်ညွှန်း layer တစ်ခုအတွင်းရှိ feature များမှ သတ်မှတ်ထားသည့် အများဆုံးအကွာအဝေးအတွင်း
ရှိနေသည့် အခါတိုင်းတွင် feature များကို ရွေးချယ်မည်ဖြစ်ပါသည်။

.. seealso:: :ref:`qgisextractwithindistance` ၊ :ref:`qgisselectbylocation`

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
   * - **Select features from** **(Feature များရွေးချယ်မည့် layer)**
     - ``INPUT``
     - [vector: any]
     - Feature များကို ရွေးချယ်မည့် input vector layer 
   * - **By comparing to the features from**
     - ``REFERENCE``
     - [vector: any]
     - နီးစပ်မှု (closeness) အတွက်အသုံးပြုမည့် feature များပါဝင်သော Vector layer ။ 
   * - **Where the features are within**
     - ``DISTANCE``
     - [number]

       Default: 100
     - ရည်ညွှန်း feature များ ပတ်လည်ရှိ အများဆုံး အကွာအဝေး။ ထိုအကွာအဝေးအတွင်းတွင် ရှိသော input feature များကို ရွေးချယ်မည်ဖြစ်သည်။
   * - **Modify current selection by**
     - ``METHOD``
     - [enumeration]

       Default: 0
     - Algorithm ၏ ရွေးချယ်ခြင်းကို မည်သို့စီမံသင့်သည်ကို ရွေးချယ်ပါ။ အောက်ပါတို့မှ တစ်ခုဖြစ်ပါသည်-

       * 0 --- creating new selection (ရွေးချယ်ခြင်းအသစ် ဖန်တီးခြင်း)
       * 1 --- adding to current selection (လက်ရှိရွေးချယ်ခြင်းထဲသို့ ပေါင်းထည့်ခြင်း)
       * 2 --- selecting within current selection (လက်ရှိရွေးချယ်ထားခြင်းထဲတွင် ရွေးချယ်ခြင်း)
       * 3 --- removing from current selection (လက်ရှိရွေးချယ်ထားခြင်းမှ ဖယ်ရှားခြင်း)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layer** **(ထည့်သွင်းအသုံးပြုသော layer)**
     - ``INPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်ထားသည့် feature များပါဝင်သော input layer

Python code
...........

**Algorithm ID**: ``native:selectwithindistance``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
