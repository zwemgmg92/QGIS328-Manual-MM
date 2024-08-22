.. index:: Functions
.. _functions_list:

List of functions (Function များ စာရင်း)
=========================================

QGIS တွင် ရရှိနိုင်သော function များ၊ operator များနှင့် variable (ကိန်းရှင်) များကို အောက်တွင် အမျိုးအစားအလိုက် အုပ်စုခွဲထားပါသည်။

.. only:: html

   .. contents::
      :local:
      :depth: 1

.. index:: Aggregates
.. _aggregates_function:

Aggregates Functions (စုစည်းခြင်းဆိုင်ရာ Function များ)
--------------------------------------------------------

ဤအုပ်စုတွင် layer များနှင့် field များပေါ်ရှိ တန်ဖိုးများကို စုစည်းပေးသည့် function များ ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Aggregates.rst
   :start-after: :orphan:
   :end-before: .. end_relation_aggregate_section

ထပ်မံဖတ်ရှုရန်- :ref:`vector_relations`

.. include:: expression_help/Aggregates.rst
   :start-after: .. end_relation_aggregate_section


.. index:: Array, List data structure
.. _array_functions:

Array Functions (အစီအစဉ်ဆိုင်ရာ Function များ)
-----------------------------------------------

ဤအုပ်စုတွင် array (အစီအစဉ်) များကို ဖန်တီးရန်နှင့် ကိုင်တွယ်ရန် function များ ပါရှိသည် (Data တည်ဆောက်ပုံများ စာရင်းဟုလည်း ခေါ်ဆိုသည်)။ Array အတွင်းရှိတန်ဖိုးများ၏ အစဥ် (order) သည် အရေးကြီးသော :ref:`'map' data structure ('မြေပုံ' Data တည်ဆောက်ပုံ) <maps_functions>` နှင့်မတူပဲ  key-value pairs (key-တန်ဖိုး အတွဲများ) ၏ order သည် မဆက်စပ်ပဲ တန်ဖိုးများကို ၄င်းတို့၏ key များဖြင့် သတ်မှတ်ထားပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Arrays.rst
   :start-after: :orphan:
   :end-before: .. end_array_get_section

.. hint:: Array တစ်ခုမှ တန်ဖိုးတစ်ခုရရှိရန် :ref:`index operator ([])<expression_function_Operators_index>` ကိုလည်း အသုံးပြုနိုင်ပါသည်။

.. include:: expression_help/Arrays.rst
   :start-after: end_array_get_section


Color Functions (အရောင် Function များ)
---------------------------------------

ဤအုပ်စုတွင် အရောင်များကို ကိုင်တွယ်နိုင်ရန်အတွက် function များ ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Color.rst
   :start-after: :orphan:
   :end-before: .. end_darker_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Color_lighter`

.. include:: expression_help/Color.rst
   :start-after: .. end_darker_section
   :end-before: .. end_lighter_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Color_darker`

.. include:: expression_help/Color.rst
   :start-after: .. end_lighter_section
   :end-before: .. end_project_color_section

ထပ်မံဖတ်ရှုရန်- :ref:`Setting project colors (Project အရောင်များ setting လုပ်ခြင်း) <project_colors>`

.. include:: expression_help/Color.rst
   :start-after: .. end_project_color_section
   :end-before: .. end_ramp_color_section

နောက်ထပ်ဖတ်ရှုရန်: :ref:`color-ramp` (ရောင်စဉ်တန်းတစ်ခု setting လုပ်ခြင်း) ၊ :ref:`color_ramp_widget` (ရောင်စဉ်တန်း ရွေးချယ်စရာ shortcut)

.. include:: expression_help/Color.rst
   :start-after: .. end_ramp_color_section


Conditional Functions (အခြေအနေဆိုင်ရာ Function များ)
-----------------------------------------------------

ဤအုပ်စုတွင် expression (စေခိုင်းချက်) များထဲတွင် အခြေအနေအရ (conditional) စစ်ဆေးမှုများကို ကိုင်တွယ်ရန် function များ ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Conditionals.rst
   :start-after: :orphan:


.. _conversion_functions:

Conversions Functions (ပြောင်းလဲမှုများဆိုင်ရာ Function များ)
--------------------------------------------------------------

ဤအုပ်စုတွင် data အမျိုးအစားတစ်ခုမှ အခြားတစ်ခုကို ပြောင်းရန် function များ ပါဝင်ပါသည်။ (ဥပမာ- string (စာသား) မှ/သို့ integer (ကိန်းပြည့်) ၊ binary (အ‌ခြေအနေနှစ်ခုသာရှိသည့် data) မှ/သို့ string ၊ string မှ date (နေ့စွဲသို့)၊ ...)။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Conversions.rst
   :start-after: :orphan:


Custom Functions (စိတ်တိုင်းကျ Function များ)
----------------------------------------------

ဤအုပ်စုတွင် အသုံးပြုသူမှ ဖန်တီးထားသော function များ ပါဝင်ပါသည်။ နောက်ထပ်အသေးစိတ်အချက်အလက်များအတွက် :ref:`function_editor` တွင်ကြည့်ရှုပါ။


Date and Time Functions (ရက်စွဲနှင့် အချိန်ဆိုင်ရာ Function များ)
------------------------------------------------------------------

ဤအုပ်စုတွင် ရက်စွဲ နှင့် အချိန် data များကို ကိုင်တွယ်ရန်အတွက် function များ ပါဝင်ပါသည်။ ဤအုပ်စုတွင် :ref:`conversion_functions` (to_date ၊ to_time ၊ to_datetime ၊ to_interval) နှင့် :ref:`string_functions` (format_date) အုပ်စုများဖြင့် function အများအပြားကို မျှဝေထားပါသည်။

.. note:: **Field များပေါ်တွင် ရက်စွဲ၊ ရက်စွဲအချိန် နှင့် interval (ကြားကာလ) များကို သိုလှောင်ခြင်း**

   *date (ရက်စွဲ) * ၊ *time (အချိန်)* နှင့် *datetime (ရက်စွဲအချိန်)* တန်ဖိုးများကို field များပေါ်တွင် တိုက်ရိုက်သိမ်းဆည်းနိုင်မှုသည် data ရင်းမြစ် ပံ့ပိုးပေးသူအပေါ် မူတည်ပါသည်။ (ဥပမာ- Shapefile သည် *date* format ကိုလက်ခံသော်လည်း *datetime* သို့မဟုတ် *time* format များကို လက်မခံပါ)။ ဤကန့်သတ်ချက်ကို ကျော်လွှားရန် အကြံပြုချက်အချို့ကို အောက်တွင် ဖော်ပြထားပါသည်-

   * :ref:`format_date <expression_function_Date_and_Time_format_date>` function ကို အသုံးပြုပြီး *date* ၊ *datetime* နှင့် *time* တို့ကို စာသားအမျိုးအစား field များတွင် ပြောင်းလဲ၍ သိမ်းဆည်းနိုင်ပါသည်။

   * *Intervals* သည် ရက်စွဲထုတ်ယူခြင်း (data extraction) function များထဲမှ တစ်ခုကို အသုံးပြုပြီး ကိန်းပြည့် (integer) သို့မဟုတ် ဒသမကိန်းဂဏန်း (decimal) အမျိုးအစား field များတွင် သိမ်းဆည်းနိုင်ပါသည် (ဥပမာ- ရက်များဖြင့် ဖော်ပြထားသည့် interval ကို ရရှိရန် :ref:`day() <expression_function_Date_and_Time_day>`) ။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Date_and_Time.rst
   :start-after: :orphan:


**အချို့ဥပမာများ**

အဆိုပါ function များအပြင် ``-`` (အနုတ်) operator ကို အသုံးပြု၍ date များ၊ datetime များ သို့မဟုတ် time များကို နုတ်ခြင်းဖြင့် interval တစ်ခု ပြန်လည်ရရှိပါမည်။

``+`` (အပေါင်း) နှင့် ``-`` (အနုတ်) operator များကို အသုံးပြု၍ date များ၊ datetime များ သို့မဟုတ် time များသို့ interval တစ်ခုကို ပေါင်းထည့်ခြင်း သို့မဟုတ် နုတ်ခြင်းဖြင့် datetime တစ်ခု ပြန်လည်ရရှိပါမည်။

* QGIS 3.0 ဖြန့်ချိမှုမတိုင်မီအထိ ရက်အရေအတွက်ကို အောက်ပါအတိုင်း ရရှိနိုင်ပါသည်-

  .. code-block:: sql

     to_date('2017-09-29') - to_date(now())
     -- Returns <interval: 203 days>

* အချိန်အတွက်လည်း ထို့အတူပင် ဖြစ်ပါသည်-

  .. code-block:: sql

     to_datetime('2017-09-29 12:00:00') - now()
     -- Returns <interval: 202.49 days>

* ယခုမှစ၍ ရက်ပေါင်း ၁၀၀ ၏ datatime ကို ရရှိနိုင်ပါသည်-

  .. code-block:: sql

     now() + to_interval('100 days')
     -- Returns <datetime: 2017-06-18 01:00:00>


.. _fields_values:

Fields and Values (Field များနှင့် တန်ဖိုးများ)
------------------------------------------------

Active (အသက်ဝင်လုပ်ဆောင်နိုင်သော) layer မှ field များစာရင်းတစ်ခုနှင့် အထူးတန်ဖိုးများ ပါရှိသည်။ Field များစာရင်းတွင် dataset ထဲတွင် သိမ်းဆည်းထားသော အရာများ၊ :ref:`virtual <virtual_field>` နှင့် :ref:`auxiliary (အရန်) <vector_auxiliary_storage>` အရာများပါဝင်သကဲ့သို့ :ref:`joins (ချိတ်ဆက်မှုများ) <sec_joins>` များမှ အရာများလည်း ပါဝင်ပါသည်။

Expression တွင် ထည့်သွင်းရန် field အမည်တစ်ခုကို click နှစ်ချက်နှိပ်ပါ။ Field အမည် (double quotes (" ") အတွင်း) သို့မဟုတ် :ref:`alias (အမည်ပို) <configure_field>` ကို ရိုက်သွင်းပြီးလည်း ထည့်သွင်းနိုင်ပါသည်။

Expression တစ်ခုတွင် အသုံးပြုမည့် field တန်ဖိုးများကို ပြန်လည်ရယူရန် သင့်လျော်သော field ကို ရွေးချယ်ပြီး ပြထားသည့် widget တွင် :guilabel:`10 Samples (နမူနာ ၁၀ခု)` နှင့် :guilabel:`All Unique (ထူးခြားသည်များအားလုံး)` တို့အကြား ရွေးချယ်ပါ။ တောင်းဆိုထားသောတန်ဖိုးများကို ပြသမည်ဖြစ်ပြီး ရလာဒ်ကိုစစ်ထုတ် (filter) ရန် စာရင်း၏ထိပ်ရှိ :guilabel:`Search` box ကို အသုံးပြုနိုင်ပါသည်။ Field တစ်ခုပေါ်တွင် ညာဖက် click နှိပ်ခြင်းဖြင့်လည်း နမူနာတန်ဖိုးများကို ရရှိစေနိုင်ပါသည်။

ရေးသားနေသည့် Expression တွင် တန်ဖိုးတစ်ခုထည့်သွင်းရန်၊ စာရင်းထဲတွင် ၎င်း expression ကို click နှစ်ချက်နှိပ်ပါ။ တန်ဖိုးသည် string အမျိုးအစားတစ်ခုဖြစ်ပါက၊ ၎င်းကို simple quote (' ') ဖြင့်ထားပါ သို့မဟုတ်ပါက quote မလိုအပ်ပါ။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Fields_and_Values.rst
   :start-after: :orphan:

Files and Paths Functions (ဖိုင်များနှင့် ဖိုင်သိမ်းဆည်းသည့်လမ်းကြောင်း Function များ)
---------------------------------------------------------------------------------------

ဤအုပ်စုတွင် ဖိုင်နှင့် လမ်းကြောင်းအမည်များကို ကိုင်တွယ်နိုင်သည့် function များ ပါရှိသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Files_and_Paths.rst
   :start-after: :orphan:


Form Functions (ပုံစံ Function များ)
-------------------------------------

ဤအုပ်စုတွင် attribute form (အချက်အလက်ပြဇယား ပုံစံ) အကြောင်းအရာအောက်တွင် သီးသန့် လုပ်ဆောင်သည့် function များ ပါရှိသည်။ ဥပမာ- :ref:`field's widgets <vector_attributes_menu>` setting များထဲတွင်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Form.rst
   :start-after: :orphan:


Fuzzy Matching Functions (အနည်းငယ်ကွဲလွဲသော dataset များကို ယှဥ်တွဲခြင်းဆိုင်ရာ Function များ)
-----------------------------------------------------------------------------------------------

ဤအုပ်စုတွင် တန်ဖိုးများကြား တိကျသေချာမှုမရှိသော နှိုင်းယှဥ်မှုများအတွက် function များ ပါဝင်သည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Fuzzy_Matching.rst
   :start-after: :orphan:


General Functions (အထွေထွေ Function များ)
------------------------------------------

ဤအုပ်စုတွင် အထွေထွေ function အမျိုးမျိုး ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/General.rst
   :start-after: :orphan:
   :end-before: .. end_var_section

ထပ်မံဖတ်ရှုရန်- Default :ref:`variables <expression_variables>` စာရင်း

.. include:: expression_help/General.rst
   :start-after: .. end_var_section


.. _geometry_functions:

Geometry Functions (ဂျီသြမေတြီ Function များ)
----------------------------------------------

ဤအုပ်စုတွင် ဂျီသြမေတြီ အရာများပေါ်တွင် လုပ်ဆောင်နိုင်သည့် function များ ပါဝင်ပါသည်။ (ဥပမာ- buffer (ကြားခံနယ်များ)၊ transform (ပြောင်းလဲခြင်း)၊ $area (ဧရိယာတွက်ချက်ခြင်း))။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/GeometryGroup.rst
   :start-after: :orphan:
   :end-before: .. end_boundary_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisboundary` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_boundary_section
   :end-before: .. end_bounds_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisboundingboxes` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: end_bounds_section
   :end-before: .. end_buffer_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisbuffer` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_buffer_section
   :end-before: .. end_buffer_by_m_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisbufferbym` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_buffer_by_m_section
   :end-before: .. end_centroid_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgiscentroids` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_centroid_section
   :end-before: .. end_collect_geometries_section


ထပ်မံဖတ်ရှုရန်- :ref:`qgiscollect` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_collect_geometries_section
   :end-before: .. end_concave_hull_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_convex_hull`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_concave_hull_section
   :end-before: .. end_contains_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_contains`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_contains_section
   :end-before: .. end_convex_hull_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_concave_hull` ၊ :ref:`qgisconvexhull` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_convex_hull_section
   :end-before: .. end_crosses_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_crosses`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_crosses_section
   :end-before: .. end_densify_by_count_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisdensifygeometries` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_densify_by_count_section
   :end-before: .. end_densify_by_distance_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisdensifygeometriesgivenaninterval` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_densify_by_distance_section
   :end-before: .. end_difference_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisdifference` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_difference_section
   :end-before: .. end_disjoint_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_disjoint`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_disjoint_section
   :end-before: .. end_end_point_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisextractspecificvertices` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_end_point_section
   :end-before: .. end_extend_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisextendlines` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_extend_section
   :end-before: .. end_flip_coordinates_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisswapxy` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_flip_coordinates_section
   :end-before: .. end_force_polygon_ccw_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_force_polygon_cw` ၊
:ref:`expression_function_GeometryGroup_force_rhr`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_force_polygon_ccw_section
   :end-before: .. end_force_polygon_cw_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_force_polygon_ccw` ၊
:ref:`expression_function_GeometryGroup_force_rhr`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_force_polygon_cw_section
   :end-before: .. end_force_rhr_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisforcerhr` algorithm ၊ :ref:`expression_function_GeometryGroup_force_polygon_ccw` ၊
:ref:`expression_function_GeometryGroup_force_polygon_cw`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_force_rhr_section
   :end-before: .. end_intersection_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisintersection` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_intersection_section
   :end-before: .. end_intersects_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_intersects`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_intersects_section
   :end-before: .. end_is_empty_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_is_empty_or_null`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_is_empty_section
   :end-before: .. end_is_empty_or_null_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_is_empty` ၊
:ref:`expression_function_Fields_and_Values_NULL`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_is_empty_or_null_section
   :end-before: .. end_is_valid_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_make_valid` ၊ :ref:`qgischeckvalidity` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_is_valid_section
   :end-before: .. end_length_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_straight_distance_2d`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_length_section
   :end-before: .. end_line_interpolate_point_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisinterpolatepoint` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_line_interpolate_point_section
   :end-before: .. end_line_substring_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgislinesubstring` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_line_substring_section
   :end-before: .. end_make_valid_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_is_valid` ၊ :ref:`qgisfixgeometries` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_make_valid_section
   :end-before: .. end_minimal_circle_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisminimumenclosingcircle` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_minimal_circle_section
   :end-before: .. end_nodes_to_points_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisextractvertices` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_nodes_to_points_section
   :end-before: .. end_offset_curve_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisoffsetline` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_offset_curve_section
   :end-before: .. end_oriented_bbox_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisorientedminimumboundingbox` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_oriented_bbox_section
   :end-before: .. end_overlay_contains_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_contains` ၊ :ref:`array manipulation <array_functions>` ၊ :ref:`qgisselectbylocation` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_contains_section
   :end-before: .. end_overlay_crosses_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_crosses` ၊ :ref:`array manipulation <array_functions>` (Array များကို ကိုင်တွယ်ခြင်း) ၊ :ref:`qgisselectbylocation` (တည်နေရာဖြင့် feature/attribute များကို ရွေးချယ်ခြင်း) algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_crosses_section
   :end-before: .. end_overlay_disjoint_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_disjoint` ၊ :ref:`array manipulation <array_functions>` ၊ :ref:`qgisselectbylocation` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_disjoint_section
   :end-before: .. end_overlay_equals_section

ထပ်မံဖတ်ရှုရန်- :ref:`array manipulation <array_functions>` (Array များကို ကိုင်တွယ်ခြင်း)၊ :ref:`qgisselectbylocation` (တည်နေရာဖြင့် feature/attribute များကို ရွေးချယ်ခြင်း) algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_equals_section
   :end-before: .. end_overlay_intersects_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_intersects` ၊ :ref:`array manipulation <array_functions>` (Array များကို ကိုင်တွယ်ခြင်း) ၊ :ref:`qgisselectbylocation` (တည်နေရာဖြင့် feature/attribute များကို ရွေးချယ်ခြင်း) algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_intersects_section
   :end-before: .. end_overlay_nearest_section

ထပ်မံဖတ်ရှုရန်- :ref:`array manipulation <array_functions>` (Array များကို ကိုင်တွယ်ခြင်း) ၊ :ref:`qgisjoinbynearest` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_nearest_section
   :end-before: .. end_overlay_touches_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_touches` ၊ :ref:`array manipulation <array_functions>` ၊ :ref:`qgisselectbylocation` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_touches_section
   :end-before: .. end_overlay_within_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_within` ၊ :ref:`array manipulation <array_functions>` ၊ :ref:`qgisselectbylocation` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_overlay_within_section
   :end-before: .. end_point_n_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisextractspecificvertices` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_point_n_section
   :end-before: .. end_point_on_surface_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgispointonsurface` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_point_on_surface_section
   :end-before: .. end_pole_of_inaccessibility_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgispoleofinaccessibility` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_pole_of_inaccessibility_section
   :end-before: .. end_project_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisprojectpointcartesian` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_project_section
   :end-before: .. end_reverse_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisreverselinedirection` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_reverse_section
   :end-before: .. end_roundness_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisroundness` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_roundness_section
   :end-before: .. end_segments_to_lines_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisexplodelines` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_segments_to_lines_section
   :end-before: .. end_simplify_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgissimplifygeometries` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_simplify_section
   :end-before: .. end_simplify_vw_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgissimplifygeometries` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_simplify_vw_section
   :end-before: .. end_single_sided_buffer_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgissinglesidedbuffer` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_single_sided_buffer_section
   :end-before: .. end_smooth_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgissmoothgeometry` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_smooth_section
   :end-before: .. end_start_point_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisextractspecificvertices` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_start_point_section
   :end-before: .. end_straight_distance_2d_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_length`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_straight_distance_2d_section
   :end-before: .. end_sym_difference_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgissymmetricaldifference` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_sym_difference_section
   :end-before: .. end_tapered_buffer_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgistaperedbuffer` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_tapered_buffer_section
   :end-before: .. end_touches_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_touches`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_touches_section
   :end-before: .. end_transform_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgisreprojectlayer` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_transform_section
   :end-before: .. end_translate_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgistranslategeometry` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_translate_section
   :end-before: .. end_wedge_buffer_section

ထပ်မံဖတ်ရှုရန်- :ref:`qgiswedgebuffers` algorithm

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_wedge_buffer_section
   :end-before: .. end_within_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_overlay_within`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_within_section
   :end-before: .. end_$x_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_x`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_$x_section
   :end-before: .. end_$x_at_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_x_at`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_$x_at_section
   :end-before: .. end_$y_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_y`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_$y_section
   :end-before: .. end_$y_at_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_GeometryGroup_y_at`

.. include:: expression_help/GeometryGroup.rst
   :start-after: .. end_$y_at_section

Layout Functions (ပုံထုတ်အပြင်အဆင် Function များ)
--------------------------------------------------

ဤအုပ်စုတွင် ပုံထုတ် Layout item များ၏ဂုဏ်သတ္တိများကို ကိုင်တွယ်ရန် function များ ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Layout.rst
   :start-after: :orphan:
   :end-before: .. end_item_variables_section

ထပ်မံဖတ်ရှုရန်- Default :ref:`variables <expression_variables>` စာရင်း

.. include:: expression_help/Layout.rst
   :start-after: .. end_item_variables_section
   :end-before: .. end_map_credits_section

ဤ function တွင် layer များ၏ :ref:`Access metadata properties <metadatamenu>` ကို ဖြည့်ထားရန် လိုအပ်ပါသည်။

.. include:: expression_help/Layout.rst
   :start-after: .. end_map_credits_section


Map Layers (မြေပုံ layer များ)
-------------------------------

ဤအုပ်စုတွင် လက်ရှိ project ထဲရှိ အသုံးပြုနိုင်သော layer များ၏ စာရင်းတစ်ခုနှင့်၊ layer တစ်ခုချင်းစီအတွက် ၎င်းတို့၏ field များ (dataset ထဲတွင်သိမ်းဆည်းထားသောအရာများ၊ virtual သို့မဟုတ် auxiliary များအပြင် ချိတ်ဆက်ထားမှုများမှအရာများ) ပါဝင်ပါသည်။ Active layer နှင့် မသက်ဆိုင်သော ရည်ညွှန်း field တစ်ခုအစား click နှစ်ချက်နှိပ်၍ string (single quoted) တစ်ခုအဖြစ် expression တွင် အမည်ထည့်သွင်းခြင်းမှလွဲ၍ field များသည် :ref:`fields_values` တွင် ဖော်ပြထားသည့်အတိုင်း တူညီသည့်နည်လမ်းဖြင့် အပြန်အလှန်လုပ်ဆောင်ပါသည်။ အဆိုပါအချက်သည် :ref:`aggregates (စုစည်းခြင်းများ) <aggregates_function>` ၊ :ref:`attribute (အချက်အလက်) <record_attributes>` သို့မဟုတ် :ref:`spatial <geometry_functions>` queries များ ဆောင်ရွက်ခြင်းကဲ့သို့သော မတူညီသည့် layer များကို ရည်ညွှန်းသော expression များ ရေးသားရန် အဆင်ပြေသည့်နည်းလမ်းတစ်ခု ဖြစ်ပါသည်။

၎င်းသည် layer များကို ကိုင်တွယ်ရန် အဆင်ပြေစေသည့် function များကိုလည်း ထောက်ပံ့ပေးပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Map_Layers.rst
   :start-after: :orphan:
   :end-before: .. end_layer_property_section

ထပ်မံဖတ်ရှုရန်- :ref:`vector <vectorinformationmenu>` ၊ :ref:`raster <raster_information>` နှင့် :ref:`mesh <meshinformation>` layer ဂုဏ်သတ္တိများ

.. include:: expression_help/Map_Layers.rst
   :start-after: .. end_layer_property_section


.. index:: Map data structure, Dictionary, Key-value pairs, Associative arrays
.. _maps_functions:


Maps Functions (မြေပုံဆိုင်ရာ Function များ)
---------------------------------------------

ဤအုပ်စုတွင် မြေပုံ data တည်ဆောက်ပုံများ (dictionary object များ၊ Key-value အစုံများ၊ သို့မဟုတ် ဆက်စပ် array များ အဖြစ်လည်းသိရှိကြပါသည်) ၏ ကီး (key) နှင့် တန်ဖိုး (value) များကို ဖန်တီးရန် သို့မဟုတ် ကိုင်တွယ်ရန် function များ ပါဝင်ပါသည်။ တန်ဖိုးများ၏ order (အစဉ်) သည်အရေးကြီးသည့် :ref:`list data structure <array_functions>` နှင့်မတူညီသည့်အချက်မှာ မြေပုံ object ထဲရှိ key-value အစုံများ၏ order သည် ဆက်စပ်ပတ်သက်မှုမရှိပဲ တန်ဖိုးများကို ၎င်းတို့၏ key များဖြင့် သတ်မှတ်ထားပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Maps.rst
   :start-after: :orphan:
   :end-before: .. end_map_get_section

.. hint:: Map တစ်ခုမှ တန်ဖိုးတစ်ခုကို ရရှိနိုင်ရန် :ref:`index operator ([]) <expression_function_Operators_index>` ကိုလည်း အသုံးပြုနိုင်ပါသည်။

.. include:: expression_help/Maps.rst
   :start-after: .. end_map_get_section


Mathematical Functions (သင်္ချာဆိုင်ရာ Function များ)
------------------------------------------------------

ဤအုပ်စုတွင် သင်္ချာဆိုင်ရာ function များ ပါဝင်ပါသည်။ (ဥပမာ- square root၊ sin နှင့် cos)

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Math.rst
   :start-after: :orphan:

.. _expression_function_meshes:

Meshes Functions (Mesh ဆိုင်ရာ function များ)
----------------------------------------------

ဤအုပ်စုတွင် mesh (အချိန်ဆိုင်ရာနှင့်အခြားအစိတ်အပိုင်းများပါဝင်သည့် ဖွဲ့စည်းပုံမရှိသောအကွက်) နှင့်ဆက်စပ်သည့် တန်ဖိုးများကို တွက်ချက်ခြင်း သို့မဟုတ် ထုတ်ပေးခြင်းဆိုင်ရာ function များ ပါဝင်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Meshes.rst
   :start-after: :orphan:


Operators ((+) ၊ (-) ၊ (/) ၊ (*) operator များ)
------------------------------------------------

ဤအုပ်စုတွင် operator များ ပါဝင်ပါသည် (ဥပမာ- + ၊ - ၊ \*)။ အောက်ဖော်ပြပါ သင်္ချာဆိုင်ရာ function အများစုအတွက် မှတ်သားထားရန်မှာ Input (ထည့်သွင်းခြင်း) တစ်ခုသည် NULL ဖြစ်လျှင် ထွက်ပေါ်လာမည့် ရလာဒ်သည် NULL ဖြစ်မည် ဖြစ်ပါသည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Operators.rst
   :start-after: :orphan:
   :end-before: end_+_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_concat` ၊
:ref:`expression_function_Operators_concat`

.. include:: expression_help/Operators.rst
   :start-after: end_+_section
   :end-before: end_BETWEEN_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Operators_NOT_BETWEEN`

.. include:: expression_help/Operators.rst
   :start-after: end_BETWEEN_section
   :end-before: end_NOT_BETWEEN_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Operators_BETWEEN`

.. include:: expression_help/Operators.rst
   :start-after: end_NOT_BETWEEN_section
   :end-before: end_[]_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Arrays_array_get` ၊
:ref:`expression_function_Maps_map_get`

.. include:: expression_help/Operators.rst
   :start-after: end_[]_section
   :end-before: end_||_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_concat` ၊
:ref:`expression_function_Operators_plus`

.. include:: expression_help/Operators.rst
   :start-after: end_||_section
   :end-before: end_~_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_regexp_match`

.. include:: expression_help/Operators.rst
   :start-after: end_~_section


.. _processing_functions:

Processing Functions (လုပ်ငန်းဆောင်ရွက်မှုဆိုင်ရာ Function များ)
-----------------------------------------------------------------

ဤအုပ်စုတွင် processing algorithm များပေါ်တွင် လုပ်ဆောင်သည့် function များ ပါဝင်သည်။


.. contents:: :local:

.. include:: expression_help/Processing.rst
   :start-after: :orphan:


.. _raster_functions:

Rasters Functions (Raster များ ဆိုင်ရာ Function များ)
------------------------------------------------------

ဤအုပ်စုတွင် raster layer ပေါ်တွင် လုပ်ဆောင်သည့် function များ ပါဝင်သည်။


.. contents:: :local:

.. include:: expression_help/Rasters.rst
   :start-after: :orphan:


.. _record_attributes:

Record and Attributes Functions (မှတ်တမ်းနှင့် အချက်အလက်များဆိုင်ရာ Function များ)
-----------------------------------------------------------------------------------

ဤအုပ်စုတွင် မှတ်တမ်း သတ်မှတ်ပေးသည့်အရာ (record identifier) များပေါ်တွင် လုပ်ဆောင်သည့် function များ ပါဝင်သည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: :orphan:
   :end-before: .. end_attributes_section

ထပ်မံဖတ်ရှုရန်- :ref:`maps_functions`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_attributes_section
   :end-before: .. end_feature_id_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Record_and_Attributes_get_feature_by_id`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_feature_id_section
   :end-before: .. end_get_feature_by_id_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Record_and_Attributes_feature_id`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_get_feature_by_id_section
   :end-before: .. end_$id_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Record_and_Attributes_feature_id` ၊
:ref:`expression_function_Record_and_Attributes_get_feature_by_id`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_$id_section
   :end-before: .. end_is_attribute_valid_section

ထပ်မံဖတ်ရှုရန်- :ref:`constraints`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_is_attribute_valid_section
   :end-before: .. end_is_feature_valid_section

ထပ်မံဖတ်ရှုရန်- :ref:`constraints`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_is_feature_valid_section
   :end-before: .. end_represent_attributes_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Record_and_Attributes_represent_value`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_represent_attributes_section
   :end-before: .. end_represent_value_section

ထပ်မံဖတ်ရှုရန်- :ref:`widget types <edit_widgets>` (widget အမျိုးအစားများ)၊ :ref:`expression_function_Record_and_Attributes_represent_attributes`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_represent_value_section
   :end-before: .. end_sqlite_fetch_and_increment_section

ထပ်မံဖတ်ရှုရန်- :ref:`project_data_source_properties` ၊ :ref:`vector_relations`

.. include:: expression_help/Record_and_Attributes.rst
   :start-after: .. end_sqlite_fetch_and_increment_section

.. index:: Relations
.. _relations_list:

Relations (ဆက်နွယ်မှုများ)
---------------------------

ဤအုပ်စုတွင် လက်ရှိ Project ထဲရှိ ရရှိနိုင်သော :ref:`relations (ဆက်နွယ်မှု) <project_relations>` စာရင်းများကို ၎င်းတို့၏ဖော်ပြချက်များနှင့်အတူ ပါရှိပါသည်။ ၎င်းသည် expression တစ်ခုရေးသားရန်အတွက် သို့မဟုတ် Form တစ်ခုကို စိတ်ကြိုက်ပြင်ဆင်နိုင်ရန်အတွက် relation ID သို့ အမြန်ဝင်ရောက်နိုင်ရန် ဆောင်ရွက်ပေးသည်။ (ဥပမာ- :ref:`relation_aggregate <expression_function_Aggregates_relation_aggregate>` funcion) 

.. _sensors_functions:

Sensors Functions (အာရုံခံကိရိယာများဆိုင်ရာ Function များ)
-----------------------------------------------------------

ဤအုပ်စုတွင် sensor (အာရုံခံကိရိယာ) များနှင့် အပြန်အလှန်လုပ်ဆောင်နိုင်သော function များ ပါဝင်သည်။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/Sensors.rst
   :start-after: :orphan:


.. _string_functions:

String Functions (စာသားဆိုင်ရာ Function များ)
----------------------------------------------

ဤအုပ်စုတွင် string (စာသား) များပေါ်တွင် လုပ်ဆောင်နိုင်သည့် function များ ပါဝင်သည် (ဥပမာ- အစားထိုးခြင်း၊ စာလုံးအကြီး (upper case) ပြောင်းလဲခြင်း)။

.. only:: html

   .. contents::
      :local:
      :class: toc_columns

.. include:: expression_help/String.rst
   :start-after: :orphan:
   :end-before: .. end_concat_section

**Field များ ပေါင်းစပ်ခြင်းအကြောင်း**

``||`` သို့မဟုတ် ``+`` operator များကို အသုံးပြု၍ စာသားများ သို့မဟုတ် field တန်ဖိုးများကို ပေါင်းစပ်နိုင်သည်-

* ``+`` operator သည် ‌ပေါင်းခြင်း expression ကို ဆိုလိုသည်။ အကယ်၍ ကိန်းပြည့် (integer) (field သို့မဟုတ် ကိန်းဂဏန်းတန်ဖိုး) ပမာဏတစ်ခုရှိပါက error ဖြစ်နိုင်ပြီး အခြားအရာများကို အသုံးပြုလျှင်ပိုမိုကောင်းမွန်နိုင်မည်ဖြစ်သည်-::

   'My feature id is: ' + "gid" => gid သည် interger တစ်ခုပြန်ထုတ်ပေးသောကြောင့် error ဖြစ်စေပါမည်

* Argument တစ်ခုခုသည် Null တန်ဖိုးဖြစ်ပါက ``||`` သို့မဟုတ် ``+`` သည် Null တန်ဖိုးတစ်ခုကို ပြန်ထုတ်ပေးမည်ဖြစ်သည်။ NULL တန်ဖိုးကို ထည့်သွင်းမစဉ်းစားပဲ အခြားသော argument များ ပြန်ရရှိရန် ``concat`` function ကို အသုံးပြုနိုင်သည်-::

    'My feature id is: ' + NULL ==> NULL 
    'My feature id is: ' || NULL => NULL 
    concat('My feature id is: ', NULL) => 'My feature id is: '

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_Operators_concat` ၊
:ref:`expression_function_Operators_plus`

.. include:: expression_help/String.rst
   :start-after: .. end_concat_section
   :end-before: .. end_ltrim_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_rtrim` ၊
:ref:`expression_function_String_trim`

.. include:: expression_help/String.rst
   :start-after: .. end_ltrim_section
   :end-before: .. end_rtrim_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_ltrim` ၊
:ref:`expression_function_String_trim`

.. include:: expression_help/String.rst
   :start-after: .. end_rtrim_section
   :end-before: .. end_trim_section

ထပ်မံဖတ်ရှုရန်- :ref:`expression_function_String_ltrim` ၊
:ref:`expression_function_String_rtrim`

.. include:: expression_help/String.rst
   :start-after: .. end_trim_section


User Expressions (အသုံးပြုသူ Expression များ)
----------------------------------------------

ဤအုပ်စုတွင် :ref:`user expression များ <user_expressions_functions>` အဖြစ် သိမ်းဆည်းထားသော expression များ ပါဝင်ပါသည်။


.. _expression_variables:

Variables (ကိန်းရှင်များ)
--------------------------

ဤအုပ်စုတွင် application၊ project file နှင့် အခြား setting များနှင့် သက်ဆိုင်သည့် ပြောင်းလဲနိုင်သော variable များ ပါဝင်ပါသည်။ Variable များရရှိနိုင်မှုသည် အကြောင်းအရာများအပေါ် မူတည်သည်-

- |expressionSelect| :sup:`Select by expression` (Expression ဖြင့် ရွေးခြယ်ခြင်း) dialog မှ
- |calculateField| :sup:`Field calculator` dialog မှ
- Layer properties dialog မှ
- Print layout မှ

ဤ variable များကို expression တစ်ခုတွင် အသုံးပြုလိုလျှင်  ``@`` အက္ခရာကို ရှေ့တွင်ထားပြီး အသုံးပြုသင့်သည် (ဥပမာ- ``@row_number``)။

.. csv-table::
   :header: "Variable (ကိန်းရှင်)", "ဖော်ပြချက်"
   :widths: 25, 300

   "algorithm_id", "Algorithm တစ်ခု၏ ထူးခြားသော ID"
   "animation_end_time", "Animation (လှုပ်ရှားရုပ်ပုံပြသခြင်း) ၏ အချိန်အပိုင်းအခြား အဆုံးသတ် (Datetime တန်ဖိုးတစ်ခုအဖြစ်)"
   "animation_interval", "Animation ၏ အချိန်အပိုင်းအခြား ကြာချိန် (Interval တန်ဖိုးတစ်ခုအဖြစ်)"
   "animation_start_time", "Animation ၏ အချိန်အပိုင်းအခြား အစ (Datetime တန်ဖိုးတစ်ခုအဖြစ်)"
   "atlas_feature", "လက်ရှိ atlas feature (Feature object အဖြစ်)"
   "atlas_featureid", "လက်ရှိ atlas feature ID"
   "atlas_featurenumber", "Layout ထဲရှိ လက်ရှိ atlas feature နံပါတ် "
   "atlas_filename", "လက်ရှိ atlas feature ဖိုင် အမည်"
   "atlas_geometry", "လက်ရှိ atlas feature ဂျီသြမေတြီ"
   "atlas_layerid", "လက်ရှိ atlas လွှမ်းခြုံသော layer ID"
   "atlas_layername", "လက်ရှိ atlas လွှမ်းခြုံသော layer အမည်"
   "atlas_pagename", "လက်ရှိ atlas စာမျက်နှာ (page) အမည်"
   "atlas_totalfeatures", "Atlas ရှိ စုစုပေါင်း feature များ အရေအတွက်"
   "canvas_cursor_point", "Project ၏ ပထဝီဝင်ဆိုင်ရာ ကိုသြဒိနိတ်များဖြင့် canvas ပေါ်ရှိ နောက်ဆုံး cursor တည်နေရာ"
   "cluster_color", "Cluster (အစုအဖွဲ့) တစ်ခုအတွင်းမှာရှိသည့် သင်္ကေတများ၏ အရောင် သို့မဟုတ် သင်္ကေတများသည် အရောင်ရောနှောနေလျှင် NULL"
   "cluster_size", "Cluster တစ်ခုအတွင်း ပါဝင်သည့် သင်္ကေတများအရေအတွက်"
   "current_feature", "Attribute form သို့မဟုတ် ဇယား row တွင် လက်ရှိ တည်းဖြတ်နေသည့် feature"
   "current_geometry", "Attribute form သို့မဟုတ် ဇယား row တွင် လက်ရှိ တည်းဖြတ်နေသည့် feature ၏ ဂျီသြမေတြီ"
   "current_parent_feature", "Parent attribute form တွင် လက်ရှိတည်းဖြတ်နေသည့် feature ကို ကိုယ်စားပြုသည်။ ထည့်သွင်းထားသော form အကြောင်းအရာတွင်သာ အသုံးပြုနိုင်သည်။"
   "current_parent_geometry", "Parent attribute form တွင် လက်ရှိတည်းဖြတ်နေသည့် feature ၏ ဂျီသြမေတြီကို ကိုယ်စားပြုသည်။ ထည့်သွင်းထားသော form အကြောင်းအရာတွင်သာ အသုံးပြုနိုင်သည်။"
   "form_mode", "Form ကို မည်သည့်အတွက် အသုံးပြုမည်၊ ဥပမာ- AddFeatureMode ၊ SingleEditMode ၊ MultiEditMode ၊ SearchMode ၊ AggregateSearchMode သို့မဟုတ် string အနေဖြင့် IdentifyMode"
   "feature", "လက်ရှိ အကဲဖြတ်ဆန်းစစ်ခံနေရသည့် feature ။ ဤအရာသည် လက်ရှိ feature မှ attribute တန်ဖိုးများကို အကဲဖြတ်ဆန်းစစ်ရန် 'attribute' function ဖြင့် အသုံးပြုနိုင်ပါသည်။"
   "frame_duration", "Animation ဘောင် (frame) တစ်ခုစီ၏ ကြာချိန်ကာလ (Interval တန်ဖိုးတစ်ခုအဖြစ်)"
   "frame_number", "Animation ပြသနေချိန်တွင် လက်ရှိ frame နံပါတ်"
   "frame_rate", "Animation ပြသနေချိန်တွင် တစ်စက္ကန့်ရှိ frame အရေအတွက် (Number of frames per second)"
   "fullextent_maxx", "Canvas extent အပြည့် မှ အမြင့်ဆုံး x တန်ဖိုး (Layer များအားလုံး အပါအဝင်)"
   "fullextent_maxy", "Canvas extent အပြည့် မှ အမြင့်ဆုံး y တန်ဖိုး (layer များအားလုံး အပါအဝင်)"
   "fullextent_minx", "Canvas extent အပြည့် မှ အနိမ့်ဆုံး x တန်ဖိုး (layer များအားလုံး အပါအဝင်)"
   "fullextent_miny", "Canvas extent အပြည့် မှ အနိမ့်ဆုံး y တန်ဖိုး (layer များအားလုံး အပါအဝင်)"
   "geometry", "လက်ရှိ အကဲဖြတ်ဆန်းစစ်ခြင်းခံနေရသည့် feature ၏ ဂျီသြမေတြီ"
   "geometry_part_count", "ပုံဖော်ပြသထားသော feature ၏ ဂျီသြမေတြီရှိ အစိတ်အပိုင်းများအရေအတွက်"
   "geometry_part_num", "ပုံဖော်ပြသထားသော feature အတွက် လက်ရှိဂျီသြမေတြီ အစိတ်အပိုင်း နံပါတ်"
   "geometry_point_count", "ပုံဖော်ပြသထားသော ဂျီသြမေတြီ ၏ အစိတ်အပိုင်းရှိ point များ အရေအတွက်"
   "geometry_point_num", "ပုံဖော်ပြသထားသော ဂျီသြမေတြီ ၏ အစိတ်အပိုင်းရှိ လက်ရှိ point နံပါတ်"
   "geometry_ring_num", "ပုံဖော်ပြသထားသော feature ၏ လက်ရှိ ဂျီသြမေတြီ ring (ကွင်း) နံပါတ် (polygon feature များအတွက်သာ)။ အပြင် ring သည် 0 တန်ဖိုးတစ်ခု ရှိပါသည်။"
   "grid_axis", "လက်ရှိ grid annotation ဝင်ရိုး (ဥပမာ- လောင်ဂျီကျူအတွက် 'x'၊ လတ္တီကျူအတွက် 'y')"
   "grid_number", "လက်ရှိ grid annotation တန်ဖိုး"
   "id", "လက်ရှိ အကဲဖြတ်ဆန်းစစ်ခြင်းခံနေရသည့် feature ၏ id"
   "item_id", "Layout item အသုံးပြုသူ ID (Unique ဖြစ်ရန်မလိုအပ်ပါ)"
   "item_uuid", "Layout item ထူးခြားသည့် ID"
   "layer", "လက်ရှိ layer"
   "layer_crs", "လက်ရှိ layer ၏ Coordinate Reference System Authority ID"
   "layer_id", "လက်ရှိ layer ၏ ID"
   "layer_ids", "စာရင်းတစ်ခုအနေဖြင့် လက်ရှိ project ရှိ မြေပုံ layer အားလုံး၏ ID များ"
   "layer_name", "လက်ရှိ layer ၏ အမည်"
   "layers", "စာရင်းတစ်ခုအနေဖြင့် လက်ရှိ project ရှိ မြေပုံ layer များအားလုံး"
   "layout_dpi", "ဖွဲ့စည်းမှု ပြတ်သားကြည်လင်မှု (resolution) (DPI)"
   "layout_name", "Layout အမည်"
   "layout_numpages", "Layout ရှိ စာမျက်နှာ အရေအတွက်"
   "layout_page", "Layout ထဲရှိ လက်ရှိ item ၏ စာမျက်နှာအရေအတွက်"
   "layout_pageheight", "Layout ရှိ active ဖြစ်နေသော စာမျက်နှာ၏ အမြင့် (စံနမူနာ စာရွက် အရွယ်အစားများအတွက် မီလီမီတာ ဖြင့်၊ သို့မဟုတ် စိတ်ကြိုက် စာရွက် အရွယ်အစားအတွက် မည်သည့် ယူနစ်ကိုမဆို အသုံးပြုနိုင်သည်)"
   "layout_pageoffsets", "စာမျက်နှာ တစ်ခုစီ၏ ထိပ်ရှိ Y ကိုသြဒိနိတ် Array။ စာမျက်နှာအရွယ်အစားများ ပြောင်းလဲနိုင်သည့် အခြေအနေတွင် စာမျက်နှာများပေါ်ရှိ item များကို ပြောင်းလဲနေရာချထားနိုင်သည်။"
   "layout_pagewidth", "Layout ရှိ active ဖြစ်နေသော စာမျက်နှာ၏ အနံ (စံနမူနာ စာရွက် အရွယ်အစားများအတွက် မီလီမီတာ ဖြင့်၊ သို့မဟုတ် စိတ်ကြိုက် စာရွက် အရွယ်အစားအတွက် မည်သည့် ယူနစ်ကိုမဆို အသုံးပြုနိုင်သည်"
   "legend_column_count", "Legend (မြေပုံရည်ညွှန်းချက်) ရှိ column များအရေအတွက်"
   "legend_filter_by_map", "Legend ၏ အကြောင်းအရာများကို မြေပုံဖြင့် စစ်ထုတ် (filter) လျှင် ညွှန်ပြပေးသည်။"
   "legend_filter_out_atlas", "Atlas ကို legend ထဲမှ စစ်ထုတ် (filter) သည့်အခါ ညွှန်ပြပေးသည်။"
   "legend_split_layers", "Legend ထဲတွင် layer များကို ခွဲထုတ်လိုသည့်အခါ ညွှန်ပြပေးသည်။"
   "legend_title", "Legend ၏ ခေါင်းစဥ်"
   "legend_wrap_string", "Legend စာသားများကို ခြုံငုံစေရန် အသုံးပြုသည့် စကားလုံး(များ)"
   "map_crs", "လက်ရှိ မြေပုံ၏ CRS (ရည်ညွှန်းကိုသြဒိနိတ်စနစ်)"
   "map_crs_acronym", "လက်ရှိမြေပုံ CRS ၏ အတိုကောက်" 
   "map_crs_definition", "လက်ရှိမြေပုံ CRS ၏ အပြည့်အစုံ အဓိပ္ပါယ်ဖွင့်ဆိုချက်"
   "map_crs_description", "လက်ရှိမြေပုံ CRS ၏ အမည်"
   "map_crs_ellipsoid", "လက်ရှိမြေပုံ CRS ၏ ဘဲဥပုံစက်ဝိုင်း (ellipsoid) အတိုကောက်"
   "map_crs_proj4", "လက်ရှိမြေပုံ CRS ၏ proj4 အဓိပ္ပါယ်ဖွင့်ဆိုချက်"
   "map_crs_projection", "မြေပုံ CRS မှ အသုံးပြုသည့် projection နည်းလမ်း၏ ဖော်ပြချက်အမည် (ဥပမာ- 'Albers Equal Area')"
   "map_crs_wkt", "လက်ရှိမြေပုံ CRS ၏  WKT အဓိပ္ပါယ်ဖွင့်ဆိုချက်"
   "map_end_time", "မြေပုံ အချိန်အပိုင်းအခြား အဆုံး (Datetime တန်ဖိုးတစ်ခုအဖြစ်)"
   "map_extent", "မြေပုံ၏ လက်ရှိ extent ကို ကိုယ်စားပြုသည့် ဂျီသြမေတြီ"
   "map_extent_center", "မြေပုံ၏ အလယ်ဗဟိုရှိ point feature"
   "map_extent_height", "မြေပုံ၏ လက်ရှိ အမြင့်"
   "map_extent_width", "မြေပုံ၏ လက်ရှိ အနံ"
   "map_id", "လက်ရှိ မြေပုံ ဦးတည်ရာ (destination) ၏ ID။ ဤအရာသည် canvas render များအတွက် 'canvas' ဖြစ်ပြီး layout map render များအတွက် item ID ဖြစ်ပါသည်"
   "map_interval", "မြေပုံ၏ အချိန်အပိုင်းအခြား ကြာချိန် (Interval တန်ဖိုးတစ်ခုအဖြစ်)"
   "map_layer_ids", "မြေပုံတွင် မြင်နိုင်သော မြေပုံ layer ID များစာရင်း"
   "map_layers", "မြေပုံတွင် မြင်နိုင်သော မြေပုံ layer များစာရင်း"
   "map_rotation", "မြေပုံ လက်ရှိ အလှည့် (rotation)"
   "map_scale", "မြေပုံ၏ လက်ရှိ စကေး"
   "map_start_time", "မြေပုံ၏ အချိန်အပိုင်းအခြား အစ (Datetime တန်ဖိုးတစ်ခုအဖြစ်)"
   "map_units", "မြေပုံတိုင်းတာမှုများ၏ ယူနစ်များ"
   "model_path", "လက်ရှိ model ၏ လမ်းကြောင်းအပြည့်အစုံ (file အမည် အပါအဝင်) (သို့မဟုတ် model သည် project တစ်ခုတွင် ထည့်သွင်းထားလျှင် project လမ်းကြောင်း)။"
   "model_folder", "လက်ရှိ model ပါဝင်သည့် Folder (သို့မဟုတ် model သည် project တစ်ခုတွင် ထည့်သွင်းထားလျှင် project folder)။"
   "model_name", "လက်ရှိ model ၏ အမည်"
   "model_group", "လက်ရှိ model အတွက် အုပ်စု"
   "notification_message", "ပံ့ပိုးပေးသူမှ ပေးပို့သော အကြောင်းကြားစာ၏ အကြောင်းအရာ (ပံ့ပိုးပေးသူ၏ အကြောင်းကြားချက်များမှ အစပြုသည့် လုပ်ဆောင်ချက်များအတွက်သာ ရနိုင်ပါသည်)။"
   "parent", "မူလ layer ရှိ လက်ရှိ feature ကို ကိုယ်စားပြုသည်၊ :ref:`aggregate <aggregates_function>` function တစ်ခုကို စစ်ထုတ် (filter) သည့်အခါ ၎င်း၏ attribute များနှင့် ဂျီသြမေတြီများသို့ ဝင်ရောက်ခွင့်ပေးသည်။"
   "project_abstract", "Project အကျဥ်းချုပ်ကို project metadata မှ ရယူပါသည်။"
   "project_area_units", "လက်ရှိ project အတွက် ဧရိယာယူနစ်သည် ဂျီသြမေတြီများ၏ ဧရိယာများကို တွက်ချက်ရာတွင် အသုံးပြုသည်။"
   "project_author", "Project author ကို project metadata မှ ရယူပါသည်။"
   "project_basename", "လက်ရှိ project ဖိုင်အမည်၏ အခြေခံအမည် (path နှင့် extension မပါဝင်သော)"
   "project_creation_date", "Project ဖန်တီးမှု ရက်စွဲကို project metadata မှ ရယူပါသည်။"
   "project_crs", "Project ၏ CRS"
   "project_crs_arconym", "Project ၏ CRS အတိုကောက်"
   "project_crs_definition", "Project ၏ CRS အဓိပ္ပါယ်ဖွင့်ဆိုချက်အပြည့်အစုံ"
   "project_crs_description", "Project ၏ CRS ဖော်ပြချက်"
   "project_crs_ellipsoid", "Project CRS ၏ ဘဲဥပုံစက်ဝိုင်း (ellipsoid)"
   "project_crs_proj4", "Project ၏ CRS ၏ proj4 ကိုယ်စားပြုမှု"
   "project_crs_wkt", "Project ၏ CRS ၏ WKT (လူသိများသော စာသား) ကိုယ်စားပြုမှု"
   "project_distance_units", "လက်ရှိ project အတွက် အကွာအဝေးယူနစ်သည် ဂျီသြမေတြီအလျားနှင့် အကွာအဝေးများကို တွက်ချက်ရာတွင် အသုံးပြုသည်။"
   "project_ellipsoid", "Geodetic ဧရိယာများ သို့မဟုတ် ဂျီသြမေတြီများ၏ အလျားများကို တွက်ချက်ရာတွင် အသုံးပြုသည့် လက်ရှိ project ၏ ဘဲဥပုံစက်ဝိုင်း (ellipsoid) အမည်"
   "project_filename", "လက်ရှိ project ၏ file အမည်"
   "project_folder", "လက်ရှိ project ၏ folder"
   "project_home", "လက်ရှိ project ၏ မူရင်းလမ်းကြောင်း"
   "project_identifier", "Project သတ်မှတ်သူ (identifier)ကို project metadata မှ ရယူပါသည်။"
   "project_keywords", "Project အဓိက စကားလုံး (keywords)များကို project metadata မှ ရယူပါသည်။"
   "project_last_saved", "Project ကို နောက်ဆုံးသိမ်းဆည်းသည့် ရက်စွဲ/အချိန်"
   "project_path", "လက်ရှိ project ၏ လမ်းကြောင်း အပြည့်အစုံ (file အမည် အပါအဝင်)"
   "project_title", "လက်ရှိ project ၏ ခေါင်းစဥ်"
   "project_units", "Project CRS ၏ ယူနစ်များ"
   "qgis_locale", "QGIS ၏ လက်ရှိ ဘာသာစကား"
   "qgis_os_name", "လက်ရှိ OS ၏ အမည်၊ ဥပမာ- 'windows'၊ 'linux' သို့မဟုတ် 'osx'"
   "qgis_platform", "QGIS ပလပ်ဖောင်း ၊ ဥပမာ- 'desktop' သို့မဟုတ် 'server'"
   "qgis_release_name", "လက်ရှိ QGIS version ထုတ်ထားသည့် အမည်"
   "qgis_short_version", "လက်ရှိ QGIS version အတိုကောက် စာသား"
   "qgis_version", "လက်ရှိ QGIS version စာသား"
   "qgis_version_no", "လက်ရှိ QGIS version နံပါတ်"
   "row_number", "လက်ရှိ row ၏ နံပါတ်ကို သိမ်းဆည်းသည်"
   "snapping_results", "Feature တစ်ခုကို digitize (ဂျီသြမေတြီများ ရေးဆွဲခြင်း) ပြုလုပ်နေစဥ်အတွင်း snapping ရလာဒ်များကို ဝင်ရောက်ခွင့်ပေးသည် (feature ပေါင်းထည့်ခြင်းတွင်သာ ရရှိနိုင်သည်)။"
   "scale_value", "လက်ရှိ စကေးဘား အကွာအဝေးတန်ဖိုး"
   "selected_file_path", "ပြင်ပသိုလှောင်မှုစနစ်ဖြင့် file တစ်ခုကို upload (ထည့်သွင်း) လုပ်သည့်အခါ file widget ရွေးချယ်သည့်အရာမှ ရွေးချယ်ထားသော file လမ်းကြောင်း"
   "symbol_angle", "Feature ကို ပုံဖော်ပြသရန် အသုံးပြုသည့် သင်္ကေတ၏ထောင့် (အမှတ်အသား (marker) သင်္ကေတများအတွက်သာ ကိုက်ညီသည်)။"
   "symbol_color", "Feature ကို ပုံဖော်ပြသရန် အသုံးပြုသည့် သင်္ကေတ၏ အရောင်"
   "symbol_count", "သင်္ကေတဖြင့် ကိုယ်စားပြုသည့် feature များ အရေအတွက် (Layout legend ထဲတွင်)"
   "symbol_id", "သင်္ကေတ၏ အတွင်း ID (Layout legend ထဲတွင်)"
   "symbol_label", "သင်္ကေတအတွက် အညွှန်း (label) (အသုံးပြုသူသတ်မှတ်ထားသော အညွှန်း သို့မဟုတ် default အားဖြင့် အလိုအလျောက်ထုတ်လုပ်ထားသော အညွှန်း - Layout legend ထဲတွင်)"
   "symbol_layer_count", "သင်္ကေတရှိ သင်္ကေတ layer များ စုစုပေါင်းအရေအတွက်"
   "symbol_layer_index", "လက်ရှိ သင်္ကေတ layer အညွှန်းကိန်း"
   "symbol_marker_column", "အမှတ်အသား (marker) အတွက် Column နံပါတ် (point pattern အဖြည့်များအတွက်သာ ကိုက်ညီသည်)"
   "symbol_marker_row", "အမှတ်အသား (marker) အတွက် Row နံပါတ် (point pattern အဖြည့်များအတွက်သာ ကိုက်ညီသည်)"
   "user_account_name", "လက်ရှိ အသုံးပြုသူ၏ OS account အမည်"
   "user_full_name", "လက်ရှိ အသုံးပြုသူ၏ OS အသုံးပြုသူ အမည်"
   "value", "လက်ရှိ တန်ဖိုး"
   "vector_tile_zoom", "ပုံဖော်ပြသထားသော မြေပုံ၏ vector tile zoom level အတိအကျ (လက်ရှိ မြေပုံစကေးမှ ရယူပါသည်)။ ပုံမှန်အားဖြင့် [0၊ 20] ကြားရှိသည်။ @zoom_level နှင့်မတူဘဲ၊ ဤ variable သည် interger zoom level နှစ်ခုကြားရှိ တန်ဖိုးများကို interpolate ပြုလုပ်ရန် အသုံးပြုနိုင်သည့် floating point တန်ဖိုးတစ်ခုဖြစ်သည်။"
   "with_variable", "Expression တစ်ခုအတွင်း အသုံးပြုမှုအတွက် variable တစ်ခုကို သတ်မှတ်ခွင့်ပြုပြီး တူညီသောတန်ဖိုးကို ထပ်ခါထပ်ခါ ပြန်လည်တွက်ချက်ခြင်းမှ ရှောင်ရှားနိုင်သည်။"
   "zoom_level", "ပုံဖော်ပြသထားသော မြေပုံ၏ vector tile zoom level (လက်ရှိ မြေပုံစကေးမှ ရယူပါသည်)။ ပုံမှန်အားဖြင့် [0၊ 20] ကြားရှိသည်။"


**အချို့ ဥပမာများ-**

* Layout ရှိ မြေပုံ item ဗဟိုတစ်ခု၏ X ကိုသြဒိနိတ်ကို ပြန်ထုတ်ပေးပါသည်-::

   x( map_get( item_variables( 'map1'), 'map_extent_center' ) )

* လက်ရှိ layer ရှိ feature တစ်ခုချင်းစီအတွက် ထပ်နေသည့် လေဆိပ် feature များ၏ အရေအတွက် ပြန်ထုတ်ပေးပါသည်-::

   aggregate( layer:='airport', aggregate:='count', expression:="code",
                  filter:=intersects( $geometry, geometry( @parent ) ) )

* Line တစ်ခု၏ ပထမဆုံး snap လုပ်ထားသည့် point ၏ object_id ကို ရယူပေးပါသည်-::
   
   with_variable(
     'first_snapped_point',
     array_first( @snapping_results ),
     attribute(
       get_feature_by_id(
         map_get( @first_snapped_point, 'layer' ),
         map_get( @first_snapped_point, 'feature_id' )
       ),
       'object_id'
     )
   )


Recent Functions (လတ်တလောအသုံးပြုထားသော Function များ)
-------------------------------------------------------

ဤအုပ်စုတွင် မကြာသေးမီက အသုံးပြုထားသော function များ ပါဝင်ပါသည်။ အသုံးပြုမှု၏အကြောင်းအရာပေါ်မူတည်၍ (feature ရွေးချယ်ခြင်း၊ field calculator၊ generic) မကြာသေးမီက အသုံးပြုထားသော expression များကို နောက်ဆုံးအဖြစ်ဆုံး မှ အစောဆုံး (more to less recent) သို့ စီထားပြီး သက်ဆိုင်ရာစာရင်းတွင် (expression ၁၀ ခုအထိ) ပေါင်းထည့်ထားသည်။ ၎င်းသည် ယခင်ကအသုံးပြုထားသော expression များကို လျင်မြန်စွာ ပြန်လည်ရယူပြီး ပြန်လည်အသုံးပြုနိုင်စေပါသည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |calculateField| image:: /static/common/mActionCalculateField.png
   :width: 1.5em
.. |expressionSelect| image:: /static/common/mIconExpressionSelect.png
   :width: 1.5em
