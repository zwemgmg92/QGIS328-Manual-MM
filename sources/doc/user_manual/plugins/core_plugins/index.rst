.. index::
   single: Core plugins
   seealso: Core plugins; Plugins

.. _core_plugins:

-----------------------------------------------------------------
Using QGIS Core Plugins (QGIS ပင်မ Plugin များကို အသုံးပြုခြင်း)
-----------------------------------------------------------------

.. toctree::
   :maxdepth: 1

   plugins_db_manager
   plugins_geometry_checker
   plugins_metasearch
   plugins_offline_editing
   plugins_topology_checker


အောက်ဖော်ပြပါစာရင်းသည် QGIS နှင့်အတူထောက်ပံ့ပေးထားသော ပင်မ plugin များစာရင်းဖြစ်ပါသည်။ ၎င်းတို့ကို default အားဖြင့် ဖွင့်ပေးထားမည်မဟုတ်ပါ။

.. list-table::
   :header-rows: 1
   :widths: 20 40 40 40

   * - သင်္ကေတ
     - Plugin
     - ဖော်ပြချက်
     - လမ်းညွှန်အကိုးအကား
   * - |dbManager|
     - DB Manager
     - QGIS အတွင်းရှိ database များကိုစီမံခန့်ခွဲသည်
     - :ref:`dbmanager`
   * - |geometryChecker|
     - Geometry Checker
     - Vector ဂျီဩမေတြီများထဲတွင် အမှားများစစ်ဆေးပြီး ပြန်လည်ပြုပြင်ပေးသည်
     - :ref:`geometry_checker`
   * - |grassTools|
     - GRASS 7
     - GRASS လုပ်ဆောင်ချက်များ
     - :ref:`sec_grass`
   * - |grassLogo|
     - GRASS GIS provider
     - GRASS GIS Processing လုပ်ဆောင်ချက်များ
     - :ref:`sec_grass`
   * - |metasearch|
     - MetaSearch Catalog Client
     - Metadata catalog services (CSW) ဖြင့် အပြန်အလှန်ဆောင်ရွက်သည်
     - :ref:`metasearch`
   * - |offlineEditingCopy|
     - Offline Editing
     - Offline တည်းဖြတ်ပြင်ဆင်ပြီး database နှင့်တပြိုင်နက်တည်းလုပ်ဆောင်ခြင်း
     - :ref:`offlinedit`
   * - |otb|
     - OrfeoToolbox provider
     - OrfeoToolbox Processing provider
     - :ref:`otb_provider`
   * - |geoprocessing|
     - Processing
     - Spatial data processing framework
     - :ref:`label_processing`
   * - |saga|
     - SAGA GIS provider
     - SAGA GIS Processing provider
     - :ref:`saga_configure`
   * - |topologyChecker|
     - Topology Checker
     - Vector layer များထဲတွင် topology ဆိုင်ရာ အမှားများကို ရှာဖွေသည်
     - :ref:`topology`

.. note::

   ပင်မ plugin များဖြစ်သော |grassTools| GRASS 7 ၊ |grassLogo| GRASS GIS provider ၊ |otb| OrfeoToolbox provider သို့မဟုတ် |saga| SAGA GIS provider တို့ကို အသုံးပြုရာတွင် ၎င်းတို့ကို ပြင်ဆင်သတ်မှတ်ပေးရမည်ဖြစ်သည်။ အချက်အလက်များကို :ref:`ဤ <processing.results>` တွင် တွေ့နိုင်ပါသည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |dbManager| image:: /static/common/dbmanager.png
   :width: 1.5em
.. |geometryChecker| image:: /static/common/geometrychecker.png
   :width: 1.5em
.. |geoprocessing| image:: /static/common/geoprocessing.png
   :width: 1.5em
.. |grassLogo| image:: /static/common/grasslogo.png
   :width: 1.5em
.. |grassTools| image:: /static/common/grass_tools.png
   :width: 1.5em
.. |metasearch| image:: /static/common/MetaSearch.png
   :width: 1.5em
.. |offlineEditingCopy| image:: /static/common/offline_editing_copy.png
   :width: 1.5em
.. |otb| image:: /static/common/otb.png
   :width: 1.5em
.. |saga| image:: /static/common/providerSaga.png
   :width: 1.5em
.. |topologyChecker| image:: /static/common/mActionTopologyChecker.png
   :width: 1.5em
