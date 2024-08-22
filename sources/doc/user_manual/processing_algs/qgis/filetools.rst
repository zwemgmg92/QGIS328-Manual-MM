File tools (File ဆိုင်ရာ ကိရိယာတန်ဆာပလာများ)
=============================================

.. only:: html

   .. contents::
      :local:
      :depth: 1

.. _qgisfiledownloader:

Download file (File ကို Download ပြုလုပ်ခြင်း)
-----------------------------------------------

URL တစ်ခုကို အသုံးပြုပြီး file တစ်ခုကို download ပြုလုပ်ပေးပါသည်။ (ဥပမာ- ``http:`` သို့မဟုတ် ``file:`` ကိုအသုံးပြုခြင်း)

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
   * - **URL**
     - ``URL``
     - [string]
     - Download ပြုလုပ်မည့် file ၏ URL
   * - **File destination** (**File တည်နေရာ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``OUTPUT``
     - [string]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - File တည်နေရာ သီးခြားသတ်မှတ်ချက်။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည်-

       .. include:: ../algs_include.rst
          :start-after: **file_output_types_skip**
          :end-before: **end_file_output_types_skip**

Advanced parameters (အဆင့်မြင့် parameter များ)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Method** (**နည်းလမ်း**)
     - ``METHOD``
     - [enumeration]

       Default: 0
     - တောင်းဆိုမှုအတွက် အသုံးပြုမည့် HTTP နည်းလမ်း။ ရွေးချယ်စရာများမှာ-
       * 0 --- GET
       * 1 --- POST
   * - **Data**

       Optional
     - ``DATA``
     - [string]
     - တောင်းဆိုမှုသည် POST တစ်ခုဖြစ်လျှင် ပေါင်းထည့်မည့် data

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **File destination**
     - ``OUTPUT``
     - [string]
     - Download ပြုလုပ်ပြီးသော file ၏တည်နေရာ

Python code
............

**Algorithm ID**: ``qgis:filedownloader``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

