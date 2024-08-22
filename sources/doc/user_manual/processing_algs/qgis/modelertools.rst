Modeler tools (Modeler ဆိုင်ရာ ကိရိယာတန်ဆာပလာများ)
===================================================

.. warning::

 Model designer ထဲတွင်သာ ယခု tool များကိုအသုံးပြုနိုင်ပါသည်။ Processing Toolbox ထဲတွင် ၎င်းတို့ကိုအသုံးပြု၍မရပါ။

.. only:: html

   .. contents::
      :local:
      :depth: 1
      :class: toc_columns


.. _qgiscondition:

Conditional branch (အခြေအနေအရ ကွဲထွက်မှု)
------------------------------------------

Model တစ်ခုထဲသို့ conditional branch (အခြေအနေအရ ကွဲထွက်မှု) တစ်ခုကိုပေါင်းထည့်ခြင်းဖြင့် expression အကဲဖြတ်ခြင်းတစ်ခု၏ရလာဒ်ပေါ်တွင် အခြေခံပြီး model ၏အစိတ်အပိုင်းများကို စေခိုင်းလုပ်ဆောင်နိုင်အောင် ဖန်တီးပေးပါသည်။ Model တစ်ခု၏လုပ်ငန်းဆောင်တာများကို ထိန်းချုပ်ရန် tool dependency (အမှီအခို) များကို များသောအားဖြင့် အသုံးပြုပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Field**
     - ``BRANCH``
     - [string]
     - အခြေအနေ၏ အမည်
   * - **Field**
     - ``CONDITION``
     - [expression]
     - အကဲဖြတ်ရန် expression

Outputs (ရလာဒ်များ)
....................

ဘာမှမရှိပါ။

Python code
............

**Algorithm ID**: ``native:condition``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgiscreatedirectory:

Create directory (လမ်းကြောင်းကိုဖန်တီးခြင်း)
---------------------------------------------

File system တစ်ခုထဲတွင် လမ်းကြောင်းအသစ်တစ်ခုဖန်တီးပေးပါသည်။ လမ်းကြောင်းများကို အဆင့်ဆင့်ဖန်တီးမည်ဖြစ်ပြီး အတိအကျလမ်းကြောင်းအပြည့်ကို တည်ဆောက်ရန်အတွက် လိုအပ်သော parent (ပင်မ) လမ်းကြောင်းများအားလုံးကို ဖန်တီးမည်ဖြစ်သည်။ လမ်းကြောင်းရှိနေပြီးသား ဖြစ်နေလျှင် အမှားနှင့်ပြဿနာ ရှိမည်မဟုတ်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Directory path** (**လမ်းကြောင်း**)
     - ``PATH``
     - [string]
     - ဖန်တီးမည့် folder လမ်းကြောင်း

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output**
     - ``OUTPUT``
     - [folder]
     - ဖန်တီးထားသော folder

Python code
............

**Algorithm ID**: ``native:createdirectory``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfilter:

Feature filter (Feature ရွေးချယ်စစ်ထုတ်ပေးသည့်အရာ)
---------------------------------------------------

Input layer မှ feature များကိုရွေးချယ်စစ်ထုတ်ပြီး ၎င်းတို့ကို တစ်ခု သို့မဟုတ် များစွာသော output များဆီသို့ပြန်လည်လမ်းညွှန်ပေးပါသည်။ ဖြစ်နိုင်သော input layer အားလုံး၏ အသုံးများသော အချက်အလက်နာမည်များကို မသိလျှင် ``$id`` နှင့် ``uuid`` ကဲ့သို့သော feature geometry နှင့် အထွေထွေ မှတ်တမ်းအစိတ်အပိုင်းများထဲတွင်သာ ရွေးချယ်စစ်ထုတ်နိုင်ပါသည်။

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
     - ထည့်သွင်းအသုံးပြုသော layer
   * - **Outputs and filters** (**Output များနှင့် ရွေးချယ်စစ်ထုတ်မှုများ**)
       (တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော)
     - ``OUTPUT_<name of the filter>``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်စစ်ထုတ်မှုများ (ရွေးချယ်စစ်ထုတ်မှုများနိုင်သမျှ များများ) ဖြင့် output layer များ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Output** (**ရလာဒ်**)
       (တစ်ခု သို့မဟုတ် တစ်ခုထက်ပိုသော)
     - ``native:filter_1:OUTPUT_<name of filter>``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ရွေးချယ်စစ်ထုတ်မှုများ (ရွေးချယ်စစ်ထုတ်မှုများနိုင်သမျှ များများ) ဖြင့် output layer များ

Python code
............

**Algorithm ID**: ``native:filter``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisfilterlayersbytype:

Filter layers by type (အမျိုးအစားဖြင့် layer များကို ရွေးချယ်စစ်ထုတ်ခြင်း)
---------------------------------------------------------------------------

Layer များကို ၎င်းတို့၏အမျိုးအစားဖြင့် ရွေးချယ်စစ်ထုတ်ပေးပါသည်။ ဝင်လာသော layer များကို vector ဖြစ်သည် သို့မဟုတ် raster ဖြစ်သည် အပေါ်မူတည်ပြီး output အမျိုးမျိုးသို့ လမ်းညွှန်ပေးပါလိမ့်မည်။

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
     - [layer]
     - ယေဘုယျ မြေပုံ layer


Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Vector features** (**Vector feature များ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``VECTOR``
     - [vector]
     - ကိုက်ညီမှုရှိလျှင် input ၏ vector layer တစ်ခု
   * - **Raster layer**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``RASTER``
     - [raster]
     - ကိုက်ညီမှုရှိလျှင် input ၏ raser layer တစ်ခု

Python code
............

**Algorithm ID**: ``native:filterlayersbytype``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisloadlayer:

Load layer into project (Layer ကို project ထဲသို့ခေါ်ယူထည့်သွင်းခြင်း)
-----------------------------------------------------------------------

လက်ရှိ project ထဲသို့ layer တစ်ခုခေါ်ယူထည့်သွင်းပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer**
     - ``INPUT``
     - [layer]
     - ရည်ညွှန်းချက်ထဲတွင် ထည့်သွင်းမည့် layer
   * - **Loaded layer name** (**ထည့်သွင်းထားသော layer အမည်**)
     - ``NAME``
     - [string]
     - ထည့်သွင်းထားသော layer ၏အမည်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - ထည့်သွင်းထားသော layer (နာမည်ပြန်ပေးထားသော)

Python code
............

**Algorithm ID**: ``native:loadlayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisraiseexception:

Raise exception (ချွင်းချက်လုပ်ဆောင်ခြင်း)
-------------------------------------------

ချွင်းချက် (exception) တစ်ခုလုပ်ဆောင်ပြီး model ကိုစေခိုင်းလုပ်ဆောင်ခြင်းမှ ရပ်တန့်ပေးပါသည်။ ချွင်းချက်အတွက်ဖော်ပြမှုစာသားကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပြီး expression ကိုအခြေခံသော အခြေအနေတစ်ခုကို သတ်မှတ်နိုင်ပါသည်။ Expression အခြေအနေတစ်ခုကို အသုံးပြုထားလျှင် expression ရလာဒ်သည် မှန်မှသာ ချွင်းချက်ကို လုပ်ဆောင်ပေးမည် ဖြစ်ပါသည်။ Expression ရလာဒ်အမှားသည် ချွင်းချက်ကို လုပ်ဆောင်မည်မဟုတ်ပဲ model စေခိုင်းလုပ်ဆောင်ခြင်းကို အနှောင့်အယှက်မရှိပဲ ဆက်လက်လုပ်ဆောင်နိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Message** (**စာတို**)
     - ``MESSAGE``
     - [string]
     - ဖော်ပြမည့်စာတို
   * - **Condition** (**အခြေအနေ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CONDITION``
     - [expression]
     - အမှန်ဖြစ်လျှင် အကဲဖြတ်မည့် expression

Outputs (ရလာဒ်များ)
....................

Log (မှတ်တမ်း) panel ထဲတွင် ဖော်ပြသည့် စာသား။

Python code
............

**Algorithm ID**: ``native:raiseexception``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisraisemessage:

Raise message (စာတို ဖော်ပြခြင်း)
----------------------------------

Log ထဲတွင် သတင်းအချက်အလက်စာတိုတစ်ခုကိုဖော်ပြပေးပါသည်။ ဖော်ပြမည့်စာတိုကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပြီး expression ကိုအခြေခံသော အခြေအနေတစ်ခုကို သတ်မှတ်နိုင်ပါသည်။ Expression အခြေအနေတစ်ခုကို အသုံးပြုထားလျှင် expression ရလာဒ်သည် မှန်မှသာ စာတိုကို ဖော်ပြပေးမည် ဖြစ်ပါသည်။ Expression ရလာဒ်အမှားသည် စာတိုကိုဖော်ပြမည်မဟုတ်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Information message** (**သတင်းအချက်အလက် စာတို**)
     - ``MESSAGE``
     - [string]
     - ဖော်ပြမည့်စာတို
   * - **Condition** (**အခြေအနေ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CONDITION``
     - [expression]
     - အမှန်ဖြစ်လျှင် အကဲဖြတ်မည့် expression

Outputs (ရလာဒ်များ)
....................

Log panel ထဲရှိ စာတိုတစ်ခု။

Python code
............

**Algorithm ID**: ``native:raisemessage``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisraisewarning:

Raise warning (သတိပေးချက်ကို ဖော်ပြခြင်း)
------------------------------------------

Log ထဲတွင် သတိပေးစာသားတစ်ခုကို ဖော်ပြပေးပါသည်။ ဖော်ပြမည့်သတိပေးစာသားကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ပြီး expression ကိုအခြေခံသော အခြေအနေတစ်ခုကို သတ်မှတ်နိုင်ပါသည်။ Expression အခြေအနေတစ်ခုကို အသုံးပြုထားလျှင် expression ရလာဒ်သည် မှန်မှသာ သတိပေးချက်ကို ဖော်ပြပေးမည် ဖြစ်ပါသည်။ Expression ရလာဒ်အမှားသည် သတိပေးချက်ကိုဖော်ပြမည်မဟုတ်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Message** (**စာတို**)
     - ``MESSAGE``
     - [string]
     - ဖော်ပြမည့်စာတို
   * - **Condition** (**အခြေအနေ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``CONDITION``
     - [expression]
     - အမှန်ဖြစ်လျှင် အကဲဖြတ်မည့် expression

Outputs (ရလာဒ်များ)
....................

Log panel ထဲတွင် ဖော်ပြသည့် စာတိုတစ်ခု။

Python code
............

**Algorithm ID**: ``native:raisewarning``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisrenamelayer:

Rename layer (Layer ကိုအမည်ပြန်ပေးခြင်း)
-----------------------------------------

Layer တစ်ခုကို နာမည်ပြန်ပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer**
     - ``INPUT``
     - [layer]
     - အမည်ပြန်ပေးမည့် layer
   * - **New name** (**အမည်အသစ်**)
     - ``NAME``
     - [string]
     - Layer ၏အမည်အသစ်

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Layer**
     - ``OUTPUT``
     - [input နှင့်အတူတူဖြစ်ပါသည်]
     - Output layer (အမည်ပြန်ပေးထားသော)

Python code
............

**Algorithm ID**: ``native:renamelayer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgissavelog:

Save log to file (Log ကို file ထဲတွင်သိမ်းခြင်း)
-------------------------------------------------

Model ကိုစေခိုင်းလုပ်ဆောင်ခြင်း log ကို file တစ်ခုအဖြစ်သိမ်းဆည်းပေးပါသည်။ HTML format ဖြင့်ပြင်ဆင်ထားသော version အဖြစ်လည်း log ကိုသိမ်းဆည်းနိုင်ပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Use HTML** (**HTML ကိုအသုံးပြုခြင်း**)
     - ``USE_HTML``
     - [Boolean]

       Default: False
     - HTML format ကိုအသုံးပြုပါ

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **File**
     - ``OUTPUT``
     - [string]
     - Log ၏တည်နေရာ

Python code
............

**Algorithm ID**: ``native:savelog``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

.. _qgissetprojectvariable:

Set project variable (Project ကိန်းရှင်ကို သတ်မှတ်ခြင်း)
---------------------------------------------------------

လက်ရှိ project အတွက် expression variable (ကိန်းရှင်) တစ်ခုကို သတ်မှတ်ပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Variable name** (**Variable အမည်**)
     - ``NAME``
     - [string]
     - Variable ၏အမည်
   * - **Variable value** (**Variable တန်ဖိုး**)
     - ``VALUE``
     - [string]
     - သိမ်းဆည်းမည့် တန်ဖိုး

Outputs (ရလာဒ်များ)
....................

ဘာမှမရှိပါ။

Python code
............

**Algorithm ID**: ``native:setprojectvariable``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisstringconcatenation:

String concatenation (စာသားများချိတ်ဆက်ပေါင်းစပ်ခြင်း)
-------------------------------------------------------

Processing Modeler ထဲတွင် စာသားနှစ်ခုကို တစ်ခုတည်းအဖြစ် ချိတ်ဆက်ပေါင်းစပ်ပေးပါသည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input 1** 
     - ``INPUT_1``
     - [string]
     - ပထမစာသား
   * - **Input 2**
     - ``INPUT_2``
     - [string]
     - ဒုတိယစာသား

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Concatenation** (**ချိတ်ဆက်ပေါင်းစပ်ပေးခြင်း**)
     - ``CONCATENATION``
     - [string]
     - ချိတ်ဆက်ပေါင်းစပ်ထားသော စာသား

Python code
............

**Algorithm ID**: ``native:stringconcatenation``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisvariabledistancebuffer:

Variable distance buffer (ကိန်းရှင် အကွာအဝေး ကြားခံ)
-----------------------------------------------------

.. warning:: ယခု algorithm ကို တိုးတက်မှုတစ်စုံတရာထပ်မံလုပ်ဆောင်ခြင်းမရှိတော့၍ အချိန်မရွေးဖယ်ထုတ်ပစ်ခံရနိုင်ပါသည်။ ၎င်းအစား :ref:`qgisbuffer` algorithm ကိုဦးစားပေး အသုံးပြုပါ။

Input layer တစ်ခုထဲရှိ feature များအားလုံးအတွက် buffer ဧရိယာတစ်ခုကိုတွက်ချက်ပေးပါသည်။

အသုံးပြုထားသော feature အတွက် buffer အရွယ်အစားကို attribute တစ်ခုဖြင့် သတ်မှတ်ပြီး feature အမျိုးမျိုးကို buffer အရွယ်အစား အမျိုးမျိုး ရရှိအောင်လုပ်ဆောင်ပေးပါသည်။

.. seealso:: :ref:`qgisbuffer`

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
   * - **Distance field** (**အကွာအဝေး field**)
     - ``DISTANCE``
     - [tablefield: numeric]
     - Buffer ၏ အချင်းဝက်အကွာအဝေးအတွက် attribute
   * - **Segments** (**မျဉ်းပိုင်းများ**)
     - ``SEGMENTS``
     - [number]

       Default: *5*
     - လုံးဝန်းသော offset (အရွေ့) များကိုဖန်တီးသောအခါ စက်ဝိုင်းလေးပုံတစ်ပုံကို ခန့်မှန်းရန်အတွက်အသုံးပြုမည့် မျဉ်းပိုင်းများ၏ အရေအတွက်ကို ထိန်းချုပ်ပေးပါသည်။
   * - **Dissolve result** (**ပေါင်းထားသောရလာဒ်**)
     - ``DISSOLVE``
     - [boolean]

       Default: *False*
     - နောက်ဆုံး buffer ကို dissolve ပြုလုပ်ရန် ရွေးချယ်ခြင်းသည် input feature များအားလုံးကိုလွှမ်းခြုံသော feature တစ်ခုတည်းကို ရရှိစေပါသည်။

       .. figure:: img/buffer_dissolve.png
          :align: center

          ပုံမှန် buffer နှင့် dissolve လုပ်ထားသော buffer
   * - **End cap style** (**အဆုံးသတ်အပိတ် style**)
     - ``END_CAP_STYLE``
     - [enumeration]

       Default: Round (လုံးဝန်းသော)
     - Buffer ထဲတွင် line အဆုံးသတ်များကို မည်သို့လုပ်ဆောင်သည်ကို ထိန်းချုပ်ပေးပါသည်။

       .. figure:: img/buffer_cap_style.png
          :align: center

          လုံးဝန်းသောအဝိုက်၊ အပြားနှင့် စတုရန်းပုံ အပိတ် style များ
   * - **Join style** (**ချိတ်ဆက်သော style**)
     - ``JOIN_STYLE``
     - [enumeration]

       Default: Round (လုံးဝန်းသောအဝိုက်)
     - Line တစ်ခု၏ ထောင့်စွန်းများကို offset လုပ်သောအခါ round (စောင်းလုံး) ၊ miter (စောင်းတိ) သို့မဟုတ် bevel (စောင်းသတ်) ချိတ်ဆက်ခြင်းများကို အသုံးပြုသင့်သလား ဆိုသည်ကို သတ်မှတ်ပေးပါသည်။
   * - **Miter limit** (**Miter ကန့်သတ်ချက်**)
     - ``MITER_LIMIT``
     - [number]

       Default: 2.0
     - Miter ဖြင့်ချိတ်ဆက်သော style များအတွက်သာအသုံးပြုနိုင်ပြီး miter ဖြင့်ချိတ်ဆက်မှုတစ်ခုကို ဖန်တီးသောအခါ အသုံးပြုသည့် offset curve မှ အများဆုံးအကွာအဝေးကို ထိန်းချုပ်ပေးပါသည်။

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
     - Buffer ပြုလုပ်ထားသော polygon vector layer

Python code
............

**Algorithm ID**: ``qgis:variabledistancebuffer``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
