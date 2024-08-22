Database
=========

.. only:: html

   .. contents::
      :local:
      :depth: 1

.. _qgisimportintopostgis:

Export to PostgreSQL (PostgreSQL သို့ထုတ်ယူခြင်း)
--------------------------------------------------

Vector layer တစ်ခုကို PostgreSQL database သို့ထုတ်ယူပြီး ဆက်နွယ်မှု (relation) အသစ်တစ်ခုကို ဖန်တီးပေးပါသည်။ နာမည်တူသော ဆက်နွယ်မှုတစ်ခုရှိနေလျှင် ချိတ်ဆက်မှုအသစ်ကို မဖန်တီးခင် ရှိနေပြီးသားအရာကို ဖယ်ထုတ်ပစ်နိုင်ပါသည်။ PostgreSQL သို့ထုတ်ယူခြင်း မပြုလုပ်မီတွင် QGIS နှင့် PostgreSQL database ကြားထဲက ချိတ်ဆက်မှု (connection) တစ်ခုကို ဖန်တီးရပါမည် (ဥပမာ :ref:`vector_create_stored_connection` တွင်ကြည့်ပါ)

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
   * - **Layer to import** (**ထည့်သွင်းမည့် layer**)
     - ``INPUT``
     - [vector: any]
     - Database သို့ပေါင်းထည့်မည့် vector layer
   * - **Database (connection name)** (**Database (ချိတ်ဆက်မှုနာမည်)**)
     - ``DATABASE``
     - [string]
     - Database ချိတ်ဆက်မှု၏ အမည် (database အမည် မဟုတ်ပါ)။ ရှိနေပြီးသား ချိတ်ဆက်မှုများကို combox ထဲတွင်ပြသပေးပါမည်။
   * - **Schema (schema name)** (**ပုံကြမ်း (ပုံကြမ်းအမည်)**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``SCHEMA``
     - [string]

       Default: 'public'
     - Data ကိုသိမ်းဆည်းမည့် ပုံကြမ်း၏အမည်။ ၎င်းသည် အသစ် သို့မဟုတ် ရှိနေပြီးသား ဖြစ်နိုင်ပါသည်။
   * - **Table to import to (leave blank to use layer name)** (**ထည့်သွင်းမည့် ဇယား (layer အမည်ကိုအသုံးပြုရန် ဗလာထားခဲ့ပါ**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TABLENAME``
     - [string]

       Default: ''
     - ထည့်သွင်းမည့် vector file အတွက် ဇယားအမည်တစ်ခုကို သတ်မှတ်ပေးပါသည်။ ဘာမှထည့်မထားလျှင် layer အမည်ကိုအသုံးပြုပါလိမ့်မည်။
   * - **Primary key field** (**မူလ key field**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRIMARY_KEY``
     - [tablefield: any]
     - Vector layer ထဲရှိ ရှိနေပြီးသား field တစ်ခုမှ primary key field ကိုသတ်မှတ်ပေးပါသည်။ **Unique (ထူးခြားသီးသန့်ဖြစ်သော)** တန်ဖိုးများရှိသည့် column တစ်ခုကို database အတွက် primary key အဖြစ် အသုံးပြုနိုင်ပါသည်။
   * - **Geometry column**
     - ``GEOMETRY_COLUMN``
     - [string]

       Default: 'geom'
     - PostGIS ဇယားအသစ်ထဲရှိ ဂျီဩမေတြီ column ၏အမည်ကိုသတ်မှတ်ပေးပါသည်။ Feature များအတွက် ဂျီဩမေတြီ သတင်းအချက်အလက်များကို ၎င်း column ထဲတွင်သိမ်းဆည်းပါသည်။
   * - **Encoding**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ENCODING``
     - [string]

       Default: 'UTF-8'
     - Output layer ၏ encoding ကိုသတ်မှတ်ပေးပါသည်
   * - **Overwrite** (**အစားထိုးပြင်ဆင်ခြင်း**)
     - ``OVERWRITE``
     - [boolean]

       Default: True
     - သတ်မှတ်ထားသော ဇယားတစ်ခုရှိပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် feature များမပေါင်းထည့်မီ ၎င်းဇယားကိုဖျက်ပစ်ပြီး ဇယားအသစ်တစ်ခု ဖန်တီးပါလိမ့်မည်။ ``False`` အဖြစ်ထားပြီး ဇယားရှိနေလျှင် algorithm သည် ချွင်းချက်အဖြစ် ထားလိုက်ပါမည် ("ဆက်နွယ်မှုရှိနေပြီးဖြစ်ပါသည်")။
   * - **Create spatial index** (**တည်နေရာဆိုင်ရာ အညွှန်းကိန်း ဖန်တီးခြင်း**)
     - ``CREATEINDEX``
     - [boolean]

       Default: True
     - Spatial index တစ်ခုကိုဖန်တီးမည်/မဖန်တီးမည်ကို သတ်မှတ်ပေးပါသည်
   * - **Convert field names to lowercase** (**Field အမည်များကို စာလုံးအသေးအဖြစ် ပြောင်းလဲခြင်း**)
     - ``LOWERCASE_NAMES``
     - [boolean]

       Default: True
     - Input vector layer ၏ field အမည်များကို စာလုံးအသေးများသို့ ပြောင်းလဲပေးပါသည်
   * - **Drop length constraint on character fields** (**စာလုံး field များတွင် စာလုံးအရေအတွက် ကန့်သတ်ခြင်း**)
     - ``DROP_STRING_LENGTH``
     - [boolean]

       Default: False
     - စာလုံး column များတွင် စာလုံးအရေအတွက် ကန့်သတ်ခြင်းကို လုပ်ဆောင်သင့်သည်/မလုပ်ဆောင်သင့်သည်ကို သတ်မှတ်ပေးပါသည်
   * - **Create single-part geometries instead of multi-part** (**အပိုင်းများစွာပါသော ဂျီဩမေတြီ များအစား အပိုင်းတစ်ခုတည်းသာရှိသော ဂျီဩမေတြီ များဖန်တီးခြင်း**)
     - ``FORCE_SINGLEPART``
     - [boolean]

       Default: False
     - Output layer ၏ feature များသည် အပိုင်းများစွာမဟုတ်ဘဲ အပိုင်းတစ်ခုတည်းဖြစ်သင့်ပါသည်။ သာမန်အားဖြင့် ရှိနေသော ဂျီဩမေတြီ သတင်းအချက်အလက်များကို ထိန်းသိမ်းထားပါသည်။

Outputs (ရလာဒ်များ)
....................

Algorithm တွင် output မရှိပါ။

Python code
............

**Algorithm ID**: ``qgis:importintopostgis``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisimportintospatialite:

Export to SpatiaLite (SpatiaLite သို့ ထုတ်ယူခြင်း)
---------------------------------------------------

Vector layer တစ်ခုကို SpatiaLite database တစ်ခုသို့ထုတ်ယူပေးပါသည်။ ထိုသို့မလုပ်ဆောင်မီ QGIS နှင့် PostgreSQL database ကြားရှိ ချိတ်ဆက်မှုတစ်ခုကို ဖန်တီးရပါမည် (ဥပမာ- :ref:`label_spatialite` တွင်ကြည့်ပါ)

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
   * - **Layer to import** (**ထည့်သွင်းမည့် layer**)
     - ``INPUT``
     - [vector: any]
     - Database သို့ပေါင်းထည့်မည့် vector layer
   * - **File database**
     - ``DATABASE``
     - [vector: any]
     - ချိတ်ဆက်ရန် SQLite/SpatiaLite database file
   * - **Table to import to (leave blank to use layer name)** (**ထည့်သွင်းမည့် ဇယား (layer အမည်ကိုအသုံးပြုရန် ဗလာထားခဲ့ပါ**))

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``TABLENAME``
     - [string]

       Default: ''
     - ထည့်သွင်းမည့် vector file အတွက် ဇယားအမည်ကို သတ်မှတ်ပေးပါသည်။ ဘာမှထည့်မထားလျှင် layer အမည်ကိုအသုံးပြုပါမည်။	 
   * - **Primary key field** (**မူလ key field**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``PRIMARY_KEY``
     - [tablefield: any]
     - Input vector layer ထဲရှိ field တစ်ခုကို primary key အဖြစ်အသုံးပြုပါ
   * - **Geometry column** (**ဂျီဩမေတြီ column**)
     - ``GEOMETRY_COLUMN``
     - [string]

       Default: 'geom'
     - SpatiaLite ဇယားအသစ်ထဲရှိ ဂျီဩမေတြီ column ၏အမည်ကိုသတ်မှတ်ပေးပါသည်။ Featrue များအတွက် ဂျီဩမေတြီ သတင်းအချက်အလက်များကို ၎င်း column ထဲတွင်သိမ်းဆည်းပါသည်။
   * - **Encoding**

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``ENCODING``
     - [string]

       Default: 'UTF-8'
     - Output layer ၏ encoding ကိုသတ်မှတ်ပေးပါသည်
   * - **Overwrite** (**အစားထိုးပြင်ဆင်ခြင်း**)
     - ``OVERWRITE``
     - [boolean]

       Default: True
     - သတ်မှတ်ထားသော ဇယားတစ်ခုရှိပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် feature များမပေါင်းထည့်မီ ၎င်းဇယားကိုဖျက်ပစ်ပြီး ဇယားအသစ်တစ်ခု ဖန်တီးပါလိမ့်မည်။ ``False`` အဖြစ်ထားပြီး ဇယားရှိနေလျှင် algorithm သည် ချွင်းချက်အဖြစ် ထားလိုက်ပါမည် ("ဆက်နွယ်မှုရှိနေပြီးဖြစ်ပါသည်")။
   * - **Create spatial index** (**တည်နေရာဆိုင်ရာ အညွှန်းကိန်း ဖန်တီးခြင်း**)
     - ``CREATEINDEX``
     - [boolean]

       Default: True
     - Spatial index တစ်ခုကိုဖန်တီးမည်/မဖန်တီးမည်ကို သတ်မှတ်ပေးပါသည်
   * - **Convert field names to lowercase** (**Field အမည်များကို စာလုံးအသေးအဖြစ် ပြောင်းလဲခြင်း**)
     - ``LOWERCASE_NAMES``
     - [boolean]

       Default: True
     - Input vector layer ၏ field အမည်များကို စာလုံးအသေးများသို့ ပြောင်းလဲပေးပါသည်
   * - **Drop length constraint on character fields** (**စာလုံး field များတွင် စာလုံးအရေအတွက် ကန့်သတ်ခြင်း**)
     - ``DROP_STRING_LENGTH``
     - [boolean]

       Default: False
     - စာလုံး column များတွင် စာလုံးအရေအတွက် ကန့်သတ်ခြင်းကို လုပ်ဆောင်သင့်သည်/မလုပ်ဆောင်သင့်သည်ကို သတ်မှတ်ပေးပါသည်
   * - **Create single-part geometries instead of multi-part** (**အပိုင်းများစွာပါသော ဂျီဩမေတြီ များအစား အပိုင်းတစ်ခုတည်းသာရှိသော ဂျီဩမေတြီ များဖန်တီးခြင်း**)
     - ``FORCE_SINGLEPART``
     - [boolean]

       Default: False
     - Output layer ၏ feature များသည် အပိုင်းများစွာမဟုတ်ဘဲ အပိုင်းတစ်ခုတည်းဖြစ်သင့်ပါသည်။ သာမန်အားဖြင့် ရှိနေသော ဂျီဩမေတြီ သတင်းအချက်အလက်များကို ထိန်းသိမ်းထားပါသည်။

Outputs (ရလာဒ်များ)
....................

Algorithm တွင် output မရှိပါ။

Python code
............

**Algorithm ID**: ``qgis:importintospatialite``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispackage:

Package layers (Package layer များ)
------------------------------------

Layer များကို GeoPackage တစ်ခုသို့ပေါင်းထည့်ပေးပါသည်။

GeoPackage သည် ရှိနေပြီးသားဖြစ်ကာ ``Overwrite existing GeoPackage`` ကိုအမှန်ခြစ်ထားလျှင် ၎င်းကို အစားထိုးပြင်ဆင်လိမ့်မည်ဖြစ်သည် (ဖယ်ထုတ်ပစ်ခြင်း နှင့် အသစ်ဖန်တီးခြင်း)။ GeoPackage သည် ရှိနေပြီးသားဖြစ်ကာ ``Overwrite existing GeoPackage`` ကိုအမှန်မခြစ်ထားလျှင် layer ကို ဆက်တွဲပေါင်းထည့်ပါလိမ့်မည်။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Input layers** (**ထည့်သွင်းအသုံးပြုသော layer များ**)
     - ``LAYERS``
     - [vector: any] [list]
     - GeoPackage ထဲသို့ထည့်သွင်းမည့် (vector) layer များ။ Raster layer များကိုထည့်သွင်း၍မရပါ။ Raster layer တစ်ခုကို ထည့်သွင်းမိပါက :class:`QgsProcessingException <qgis.core.QgsProcessingException>` ကို လုပ်ဆောင်ပါမည်။
   * - **Overwrite existing GeoPackage** (**ရှိနေပြီးသား GeoPackage ကို အစားထိုးပြင်ဆင်ရေးသားခြင်း**)
     - ``OVERWRITE``
     - [boolean]

       Default: False
     - သတ်မှတ်ထားသော GeoPackage တစ်ခုရှိပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် layer များမပေါင်းထည့်မီ ၎င်းကိုဖျက်ပစ်ပြီး အသစ်တစ်ခု ဖန်တီးပါလိမ့်မည်။ ``False`` အဖြစ်ထားလျှင် layer များကို ဆက်တွဲပေါင်းထည့်ပေးပါမည်။
   * - **Save layer styles into GeoPackage** (**Layer style များကို GeoPackage ထဲတွင် သိမ်းဆည်းခြင်း**)
     - ``SAVE_STYLES``
     - [boolean]

       Default: True
     - Layer style များကိုသိမ်းဆည်းခြင်း
   * - **Save only selected features** (**ရွေးချယ်ထားသော feature များကိုသာ သိမ်းဆည်းခြင်း**)
     - ``SELECTED_FEATURES_ONLY``
     - [boolean]

       Default: False
     - Layer တွင် ရွေးချယ်မှု (selection) တစ်ခုရှိနေပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် ရွေးချယ်ထားသော feature များကိုသာ သိမ်းဆည်းပါလိမ့်မည်။ ရွေးချယ်မှုလုပ်မထားသော layer များအတွက်ဆိုလျှင် feature များအားလုံးကို သိမ်းဆည်းပါလိမ့်မည်။
   * - **Export related layers following relations defined in the project** (**Project ထဲတွင် သတ်မှတ်ထားသော ဆက်နွယ်မှုများနှင့် သက်ဆိုင်သော layer များကိုထုတ်ခြင်း**)
     - ``EXPORT_RELATED_LAYERS``
     - [boolean]

       Default: False
     - Input layer တစ်ခုသည် project ထဲတွင် သတ်မှတ်ထားသော :ref:`ဆက်နွယ်မှုများ <vector_relations>` ရှိပြီး ယခု setting ကို ``True`` အဖြစ်ထားလျှင် ၎င်းနှင့်ဆက်နွယ်သော layer များကိုပါထုတ်ပေးပါလိမ့်မည်။ Layer တွင်ရွေးချယ်ထားသော feature များရှိပြီး ဆက်နွယ်သော layer သည်လည်း input layer မဟုတ်လျှင် ၎င်းတို့၏ဆက်နွယ်သော feature များကိုသာ ထုတ်ပေးပါလိမ့်မည်။
   * - **Destination GeoPackage** (**GeoPackage ရှိသောနေရာ**)
     - ``OUTPUT``
     - [file]

       Default: ``[Save to temporary file] ([ယာယီ file အဖြစ်သိမ်းဆည်းပါ])``
     - GeoPackage file ကို မည်သည့်နေရာတွင် သိမ်းဆည်းမည်ကို သတ်မှတ်ပါ။ အောက်ပါတို့ထဲမှ တစ်ခုခုဖြစ်ပါသည် - 

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
   * - **Layers within new package** (**Package အသစ်အတွင်းရှိ layer များ**)
     - ``OUTPUT_LAYERS``
     - [string] [list]
     - GeoPackage သို့ပေါင်းထည့်ထားသော layer များ၏စာရင်း။

Python code
............

**Algorithm ID**: ``native:package``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispostgisexecuteandloadsql:

PostgreSQL execute and load SQL (PostgreSQL စေခိုင်းလုပ်ဆောင်ခြင်းနှင့် SQL ကိုခေါ်ယူထည့်သွင်းခြင်း)
-----------------------------------------------------------------------------------------------------

QGIS သို့ချိတ်ဆက်ထားသော PostgreSQL database တစ်ခုတွင် SQL database query တစ်ခုကိုလုပ်ဆောင်ပေးပြီး ရလာဒ်များကိုခေါ်ယူထည့်သွင်းပေးပါသည်။ Algorithm သည် layer အသစ်တစ်ခုကို **ဖန်တီးမည်မဟုတ်ပါ** - layer ပေါ်တွင် query များကိုလုပ်ဆောင်ရန် ဖန်တီးထားပါသည်။

.. _qgis_postgis_execute_sql_example:

.. **postgisexecutesqlexample**

.. The following section is included in database algorithms such as
 qgispostgisexecutesql, qgispostgisexecuteandloadsql

**Example (ဥပမာ)**

#. ရှိနေပြီးသား field တစ်ခု၏ တန်ဖိုးများအားလုံးကို ပုံသေတန်ဖိုးတစ်ခုအဖြစ် သတ်မှတ်ပါ။ SQL query စာသားမှာ-

   .. code-block:: sql
   
    UPDATE your_table SET field_to_update=20;

   အထက်ဖော်ပြပါ ဥပမာတွင် ``your_table`` ဇယား၏ ``field_to_update`` field ၏တန်ဖိုးများအားလုံးကို ``20`` အဖြစ်သတ်မှတ်ပါလိမ့်မည်။

#. ``area`` column အသစ်တစ်ခုကို ဖန်တီးပြီး feature တစ်ခုချင်းစီ၏ ဧရိယာကို ``ST_AREA`` PostGIS function အသုံးပြုပြီး တွက်ချက်ပါ။

   .. code-block:: sql
   
    -- Create the new column "area" on the table your_table"
    ALTER TABLE your_table ADD COLUMN area double precision;
    -- Update the "area" column and calculate the area of each feature:
    UPDATE your_table SET area=ST_AREA(geom);

.. **end_postgisexecutesqlexample**

.. seealso:: :ref:`qgispostgisexecutesql` ၊ :ref:`qgisexecutesql` ၊
 :ref:`qgisspatialiteexecutesql`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Database (connection name)** (**Database (ချိတ်ဆက်မှုအမည်)**)
     - ``DATABASE``
     - [string]
     - Database ချိတ်ဆက်မှု၏ အမည် (database အမည် မဟုတ်ပါ)။ ရှိနေပြီးသား ချိတ်ဆက်မှုများကို combox ထဲတွင်ပြသပေးပါမည်။
   * - **SQL query**
     - ``SQL``
     - [string]
     - SQL query ကိုသတ်မှတ်ပေးပါသည်၊ ဥပမာ-
       ``'UPDATE my_table SET field=10'``
   * - **Unique ID field name** (**Unique ဖြစ်သော ID column အမည်**)
     - ``ID_FIELD``
     - [string]

       Default: id
     - Primary key field ကိုသတ်မှတ်ပေးပါသည် (ရလာဒ်ဇယားထဲရှိ column တစ်ခု)
   * - **Geometry field name** (**ဂျီဩမေတြီ column အမည်**)

       Optional (မဖြစ်မနေလုပ်ဆောင်ရန် မလိုအပ်ပါ)
     - ``GEOMETRY_FIELD``
     - [string]

       Default: 'geom'
     - ဂျီဩမေတြီ column ၏အမည် (ရလာဒ်ဇယားထဲရှိ column တစ်ခု)

Outputs (ရလာဒ်များ)
....................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **SQL layer**
     - ``OUTPUT``
     - [vector: any]
     - QGIS ထဲသို့ ခေါ်ယူထည့်သွင်းမည့် ရလာဒ် vector layer

Python code
............

**Algorithm ID**: ``qgis:postgisexecuteandloadsql``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgispostgisexecutesql:

PostgreSQL execute SQL (PostgreSQL သည် SQL ကိုစေခိုင်းလုပ်ဆောင်ခြင်း)
----------------------------------------------------------------------

QGIS သို့ချိတ်ဆက်ထားသော PostgreSQL database တစ်ခုတွင် SQL database query တစ်ခုကိုလုပ်ဆောင်ပေးနိုင်ပါသည်။ Algorithm သည် layer အသစ်တစ်ခုကို **ဖန်တီးမည်မဟုတ်ပါ** - layer ပေါ်တွင် query များကိုလုပ်ဆောင်ရန် ဖန်တီးထားပါသည်။

.. include:: ./database.rst
   :start-after: .. **postgisexecutesqlexample**
   :end-before: .. **end_postgisexecutesqlexample**

.. seealso:: :ref:`qgispostgisexecuteandloadsql` ၊
   :ref:`qgisexecutesql` ၊ :ref:`qgisspatialiteexecutesql`

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **Database (connection name)** (**Database (ချိတ်ဆက်မှုအမည်)**)
     - ``DATABASE``
     - [string]

     - Database ချိတ်ဆက်မှု၏ အမည် (database အမည် မဟုတ်ပါ)။ ရှိနေပြီးသား ချိတ်ဆက်မှုများကို combox ထဲတွင်ပြသပေးပါမည်။
   * - **SQL query**
     - ``SQL``
     - [string]
     - SQL query ကိုသတ်မှတ်ပေးပါသည်၊ ဥပမာ-
       ``'UPDATE my_table SET field=10'``

Outputs (ရလာဒ်များ)
....................

Output ကိုဖန်တီးမပေးပါ။ SQL query ကို ၎င်းနေရာတွင် စေခိုင်းလုပ်ဆောင်ပါသည်။

Python code
............

**Algorithm ID**: ``native:postgisexecutesql``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisspatialiteexecutesql:

SpatiaLite execute SQL (SpatiaLite သည် SQL ကိုစေခိုင်းလုပ်ဆောင်ခြင်း)
----------------------------------------------------------------------

SpatiaLite database တစ်ခုတွင် SQL database query တစ်ခုကို လုပ်ဆောင်ပေးပါသည်။ Algorithm သည် layer အသစ် **ဖန်တီးမည်မဟုတ်ပါ** - layer ပေါ်တွင် query များကိုလုပ်ဆောင်ရန် ဖန်တီးထားပါသည်။

.. seealso:: :ref:`qgispostgisexecutesql` ၊ :ref:`qgisexecutesql`
 
 အချို့သော SQL query ဥပမာများအတွက် :ref:`PostGIS SQL Query Examples
 <qgis_postgis_execute_sql_example>` ကို ကြည့်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်
   * - **File Database**
     - ``DATABASE``
     - [vector]
     - ချိတ်ဆက်ရန် SQLite/SpatiaLite database file
   * - **SQL query**
     - ``SQL``
     - [string]

       Default: ''
     - SQL query ကိုသတ်မှတ်ပေးပါသည်၊ ဥပမာ- ``'UPDATE my_table SET field=10'``

Outputs (ရလာဒ်များ)
....................

Output ကိုဖန်တီးမပေးပါ။ SQL query ကို ၎င်းနေရာတွင် စေခိုင်းလုပ်ဆောင်ပါသည်။

Python code
............

**Algorithm ID**: ``native:spatialiteexecutesql``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**


.. _qgisspatialiteexecutesqlregistered:

SpatiaLite execute SQL (registered DB) (SpatiaLite သည် SQL ကိုစေခိုင်းလုပ်ဆောင်ခြင်း (မှတ်ပုံတင်ထားသော DB))
------------------------------------------------------------------------------------------------------------

QGIS သို့ချိတ်ဆက်ထားသော SpatiaLite database တစ်ခုတွင် SQL database query တစ်ခုကို လုပ်ဆောင်ပေးပါသည်။ Algorithm သည် layer အသစ် **ဖန်တီးမည်မဟုတ်ပါ** - layer ပေါ်တွင် query များကို လုပ်ဆောင်ရန် ဖန်တီးထားပါသည်။

.. seealso:: :ref:`qgispostgisexecutesql` ၊ :ref:`qgisexecutesql`

 အချို့သော SQL query ဥပမာများအတွက် :ref:`PostGIS SQL Query Examples
 <qgis_postgis_execute_sql_example>` ကိုကြည့်ပါ။

Parameters (Parameter များ)
............................

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - အညွှန်း
     - အမည်
     - အမျိုးအစား
     - ရှင်းလင်းဖော်ပြချက်

   * - **Database**
     - ``DATABASE``
     - [enumeration]
       
       Default: not set
     - လက်ရှိ session နှင့်ချိတ်ဆက်ထားသော SQLite/SpatiaLite database တစ်ခုကို ရွေးချယ်ပါ
   * - **SQL query**
     - ``SQL``
     - [string]

       Default: ''
     - SQL query ကိုသတ်မှတ်ပေးပါသည်၊ ဥပမာ- ``'UPDATE my_table SET field=10'``

Outputs (ရလာဒ်များ)
....................

Output ကိုဖန်တီးမပေးပါ။ SQL query ကို ၎င်းနေရာတွင် စေခိုင်းလုပ်ဆောင်ပါသည်။

Python code
............

**Algorithm ID**: ``native:spatialiteexecutesqlregistered``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**
