.. index:: 3D Map view
.. _`label_3dmapview`:

******************************************************************************
3D Map View (သုံးဘက်မြင်ပုံရိပ်ဖြင့်ကြည့်ရှုနိုင်သည့်မြေပုံမြင်ကွင်း)
******************************************************************************

.. only:: html

   .. contents::
      :local:


3D visualization (သုံးဘက်မြင်ပုံရိပ်ဖြင့်ကြည့်ရှုခြင်း) ကို 3D map view (သုံးဘက်မြင်ပုံရိပ်ဖြင့်ကြည့်ရှုနိုင်သည့်မြေပုံမြင်ကွင်း) မှ တဆင့်ကြည့်ရှုနိုင်အောင် ဆောင်ရွက်ပေးထားပါသည်။ 
:menuselection:`View --> 3D Map Views -->` menu မှတဆင့် 3D map view များကို ဖန်တီးခြင်း၊ စီမံခန့်ခွဲခြင်း နှင့် ဖွင့်ခြင်းများ ပြုလုပ်နိုင်ပါသည်-


#. |new3DMap| :menuselection:`New 3D Map View` ကို နှိပ်ခြင်းဖြင့် 3D map view အသစ်တစ်ခုကို ဖန်တီးနိုင်မည်ဖြစ်ပါသည်။ 
   မိမိစိတ်ကြိုက် နေရာရွှေ့ပြောင်းချထားနိုင်သည့် (floating and dockable) QGIS panel (QGIS ဘောင်) တစ်ခုသည် ပေါ်လာမည်ဖြစ်ပါသည်။ (ကြည့်ရှုရန် :ref:`figure_3dmapview`)
   ၎င်းသည် 2D မြေပုံရေးဆွဲသည့်နေရာ (2D main map canvas) ကဲ့သို့ပင် တူညီသည့် extent (နယ်ပယ်အတိုင်းအတာပမာဏ) နှင့် view (မြင်ကွင်း) ရှိပါသည်။  
   ထို့အပြင် view များကို 3D သို့ပြောင်းလဲကြည့်ရှုနိုင်ရန် navigation tools (လမ်းညွှန်ပြသခြင်းဆိုင်ရာ tools) များအား ထည့်သွင်းထားပါသည်။ 
#. :menuselection:`Manage 3D Map Views` ကိုနှိပ်ခြင်းအားဖြင့် 3D Map Views Manager (3D Map Views များကို စီမံခန့်ခွဲသည့်နေရာ) ထဲသို့ ရောက်ရှိမည်ဖြစ်ပါသည်။
   အဆိုပါနေရာတွင် 3D map views များကို ဖွင့်ခြင်း၊ နှစ်ခုပြုလုပ်ခြင်း/ပွားခြင်း၊ ဖယ်ရှားခြင်းနှင့် အမည်ပြန်လည်သတ်မှတ်ခြင်းများကို ဆောင်ရွက်နိုင်မည်ဖြစ်ပါသည်။ 
#. သုံးဘက်မြင်ပုံရိပ်ဖြင့်ကြည့်ရှုနိုင်သည့် 3D map views များကို တစ်ခု သို့မဟုတ် တစ်ခုထက်ပို၍ ဖန်တီးခဲ့ပါက ၎င်းတို့ကို :menuselection:`3D Map Views` တွင် အစဉ်လိုက်တွေ့မြင်ရမည်ဖြစ်ပါသည်။ 
   ၎င်းတို့ကို နှိပ်၍ ဖွင့်ခြင်းနှင့်ပိတ်ခြင်းများကို ဆောင်ရွက်နိုင်မည်ဖြစ်ပါသည်။ အကယ်၍ ၎င်းတို့ကို ပိတ်ထားစေကာမူ project ကို သိမ်းဆည်းခြင်းဖြင့် ၎င်းတို့ကိုပါ တပြိုင်တည်းသိမ်းဆည်းနိုင်မည်ဖြစ်ပါသည်။ 


.. _figure_3dmapview:

.. figure:: img/3dmapview.png
   :align: center

   သုံးဘက်မြင်ပုံရိပ်ဖြင့်ကြည့်ရှုနိုင်သည့်မြေပုံမြင်ကွင်း dialog

အောက်ဖော်ပြပါ tools များကို 3D map view panel ၏ အပေါ်ဘက်ထိပ်တွင် ထည့်သွင်းပေးထားပါသည်-

* |pan| :sup:`Camera Control` - ကင်မရာ၏ လမ်းကြောင်းနှင့် ရှုထောင့် ကို နဂိုအတိုင်းထား၍ view ကိုရွေ့သည်။
* |zoomFullExtent| :sup:`Zoom Full` - Layer's extent တစ်ခုလုံးအထိ view ကို အရွယ်အစားပြန်လည်ချိန်ညှိ (resize) သည်။
* |3dNavigation| :sup:`Toggle On-Screen Notification` - Navigation widget ကို ဖော်ပြခြင်း/ဖျောက်ထားခြင်းလုပ်သည်။ (Map view အား ကိုင်တွယ်ဆောင်ရွက်ရာတွင် လွယ်ကူစေရန်အတွက် ဖြစ်သည်။)
* |identify| :sup:`Identify` - မြေပြင်အနေအထား (terrain) ၏ ကလစ်နှိပ်ထားသည့်အမှတ်ပေါ်ရှိ အချက်အလက်များ သို့မဟုတ် ကလစ်နှိပ်ထားသည့် 3D feature(s) (3D များ၏သိသာထင်ရှားသည့် ဝိသေသများ) ၏ အချက်အလက်များ (information) ကိုဖော်ပြသည်။  
  :ref:`identify` တွင် အသေးစိတ်ကိုကြည့်ရှုပါ။
* |measure| :sup:`Measurement Line` - အမှတ်နှစ်ခုအကြားရှိ horizontal distance (မြေပြင်ညီအကွာအဝေး) ကို တိုင်းတာသည်။ 
* |play| :sup:`Animations` - :ref:`animation player <create_animation>` widget ကို ဖော်ခြင်း/ဖျောက်ထားခြင်း
* |saveMapAsImage| :sup:`Save as Image...` - လက်ရှိ view အား image ဖိုင်ပုံစံဖြင့် export ထုတ်သည်။ 
* |3d| :sup:`Export 3D Scene` - Blender... ကဲ့သို့ applications များတွင် post-processing (နောက်ပိုင်းလုပ်ငန်းများထပ်မံလုပ်ဆောင်ခြင်း) ဆောင်ရွက်ခြင်းကိုခွင့်ပြုပေးပြီး လက်ရှိ view အား 
  3D မြင်ကွင်း (3D scene) (:file:`.obj` ဖိုင်) အဖြစ်သို့ export ထုတ်သည်။ 
  မြေပြင်အနေအထား (terrain) နှင့် vector features များကို 3D objects (3D အရာဝတ္ထု) များအဖြစ်သို့ export ထုတ်သည်။ 
  Export setting များ၊ layers :ref:`properties <sec_3_d_view>` များကို ပြန်လည်ပြင်ဆင်ရေးသားခြင်း 
  သို့မဟုတ် map view :ref:`configuration <scene_configuration>` တွင် အောက်ပါတို့ပါဝင်ပါသည်- 

  * :guilabel:`Scene name` နှင့် :guilabel:`Folder` တည်နေရာ
  * :guilabel:`Terrain resolution` (မြေပြင်အနေအထား ကြည်လင်ပြတ်သားမှု)
  * :guilabel:`Terrain texture resolution` (မြေပြင်အနေအထား၏ texture ကြည်လင်ပြတ်သားမှု)
  * :guilabel:`Model scale`
  * |checkbox| :guilabel:`Smooth edges` (ချောမွေ့သည့်အစွန်းများ)
  * |checkbox| :guilabel:`Export normals` (normals များကို export ပြုလုပ်ခြင်း)
  * |checkbox| :guilabel:`Export textures` (textures များကို export ပြုလုပ်ခြင်း)
* |showPresets| :sup:`Set View Theme`: ကြိုတင်သတ်မှတ်ထားသည့် :ref:`map themes <map_themes>` (မြေပုံအမျိုးအစားများ) မှ map view ထဲတွင်ပြသရန် layers များကို select (ရွေးချယ်သတ်မှတ်ခြင်း) ပြုလုပ်ခြင်းအား ခွင့်ပြုသည်။ 
* |options| :sup:`Options` menu သည် အောက်ပါတို့အတွက် shortcuts (အလွယ်တကူ မြန်မြန်လုပ်ဆောင်နိုင်သည့် အရာများ) များပံ့ပိုးပေးထားပါသည်။ 

  * 3D rendering (3D ပုံဖော်ပြသခြင်း) ထဲသို့ :ref:`shadows <shadows>` (အရိပ်များ) ၊ :ref:`eye dome lighting <eye_dome_lighting>` (depth perception ရရှိစေရန် အနီးကပ်ရှိသည့် အရာဝတ္ထုများကို အုပ်စုဖွဲ့ပြီး ၎င်းတို့၏ပုံသဏ္ဍာန်များကို ပေါ်လွင်စေသည့် 
    အလင်းရောင်ပုံစံ) သို့မဟုတ် :ref:`ambient occlusion <ambient_occlusion>` (scene တစ်ခုထဲရှိ အမှတ်တစ်ခုချင်းစီသည် ambient lighting ကို မည်မျှထိတွေ့နိုင်မည်ကို တွက်ချက်သည့် rendering technique) ပြသခြင်း ကဲ့သို့သော  visual effects (မြင်ကွင်းဆိုင်ရာ အထူးပြုလုပ်ချက်) များထည့်သွင်းခြင်း  
  * မြင်ကွင်းများကို synchronize (တစ်ချိန်ထဲတွင်တစ်ပြိုင်တည်း) ဖြစ်စေသည်။ (:guilabel:`2D map view follows 3D camera` နှင့်/သို့မဟုတ် :guilabel:`3D camera follows 2D Map view`)
  * :guilabel:`Show visible camera area in 2D map view`
  * 3D map view :ref:`settings <scene_configuration>` အား |options| :sup:`Configure` ပြုလုပ်ခြင်း
* |dock| :sup:`Dock 3D Map View` - docked widget (နေရာချထားသည့် widget) မှ top level window (window manager အောက်တွင် သီးခြားရှိသည့် window) သို့ တစ်ခုမှတစ်ခုသို့ ပြောင်းလဲသည်။ 

.. _`scene_configuration`:

Scene Configuration (Scene သတ်မှတ်ဖွဲ့စည်းခြင်း)
=================================================

3D map view သည် စိတ်ကြိုက်ပြုပြင်ပြောင်းလဲမှုများပြုလုပ်နိုင်သည့် ပုံမှန်သတ်မှတ်ထားသော setting (default settings) ဖြင့် ပွင့်လာမည်ဖြစ်ပါသည်။ 
စိတ်ကြိုက်ပြုပြင်ပြောင်းလဲနိုင်ရန် 3D canvas panel (3D Canvas ဘောင်) ၏ အပေါ်ဘက်တွင် ရှိသည့် |options| :sup:`Options` menu ကို ဖြည်ချပါ။ ထို့နောက်
:guilabel:`3D configuration` window (သုံးဘက်မြင်ပုံရိပ်များအား ဖန်တီးသတ်မှတ်သည့် window) ကို ဖွင့်ရန် |options| :menuselection:`Configure` ခလုတ်ကိုနှိပ်ပါ။ 

.. _figure_3dmap_config:

.. figure:: img/3dmapconfiguration.png
   :align: center

   3D မြေပုံ ဖန်တီးသတ်မှတ်ခြင်း Dialog


3D Configuration window တွင် အကောင်းမွန်ဆုံးသော 3D scene ကို ဖန်တီးနိုင်ရန် များစွာသော options (ရွေးချယ်မှုများ) ပါရှိပါသည်။ 

Terrain (မြေပြင်အနေအထား)
-------------------------

* :guilabel:`Terrain` - အသေးစိတ်အကြောင်းအရာများကိုမလေ့လာမီတွင် 3D view ရှိ မြေပြင်အနေအထားသည်  terrain tiles (ကွန်တိုလိုင်းများနှင့် hill shade mapping များပါဝင်သည့် image tiles) များ၏ အဆင့်အတန်း (hierarchy)အပေါ်မူတည်၍ 
  ပြသမည်ဖြစ်ပြီး ကင်မရာသည် မြေပြင်အနေအထားနှင့် နီးကပ်လာသည်နှင့်အမျှ လုံလောက်သည့်အသေးစိတ်အချက်များမပါဝင်သည့် လက်ရှိရှိနေသည့် tiles များကို အသေးစိတ်အချက်များပါဝင်သည့် 
  ပို၍သေးငယ်သော tiles များဖြင့် အစားထိုးသည်ကို သတိပြုရမည်ဖြစ်ပါသည်။ 
  Tile တစ်ခုချင်းစီတွင် elevation raster layer (အညီအမျှ နေရာချထားသော grid တစ်ခုတွင် ပေးထားသောဧရိယာအတွက် အမြင့်များပါရှိသည့် layer) များနှင့် 
  2D map layers များမှ texture များထံမှ တွက်ချက်ရယူထားသည့် mesh geometry (မျက်နှာပြင်တစ်ခုသို့မဟုတ်
  အစိုင်အခဲအရာဝတ္တုတစ်ခုကို ကိုယ်စားပြုဖော်ပြနိုင်သည့် ထောင့်များနှင့် တြိဂံများပါရှိသည့်အစုအဝေး) ပါရှိပါသည်။ 

  * Elevation terrain အမျိုးအစား :guilabel:`Type` သည် 

    * :guilabel:`Flat terrain` (ပြန့်ပြူးမှုရှိသည့် မြေပြင်အနေအထား)
    * :guilabel:`DEM (Raster Layer)` (သစ်ပင်များ၊ အဆောက်အဦများနှင့် အခြားသော surface object များမပါရှိသည့် ကမ္ဘာမြေမျက်နှာပြင်)
    * :guilabel:`Online` service, Mapzen tools ဖြင့် ထုတ်လုပ်ဆောင်ရွက်ထားသည့် `elevation tiles 
      http://s3.amazonaws.com/elevation-tiles-prod/>` များကို ထည့်သွင်းခြင်း။ 
      အသေးစိတ်ကြည့်ရှုရန် https://registry.opendata.aws/terrain-tiles/
    * ထည့်သွင်းထားသည့် :guilabel:`Mesh` dataset

  * :guilabel:`Elevation` - Raster (ဓါတ်ပုံများကဲ့သို့ pixels များပါရှိသည့် layer အမျိုးအစား) သို့မဟုတ် mesh layer ကို မြေပြင်အနေအထား (terrain) များ ထုတ်လုပ်ရန်အတွက်အသုံးပြုပါသည်။ 
    raster layer သည် အမြင့်ကိုဖော်ပြသည့် band (မတူညီသောရောင်စဉ်) တစ်ခုပါဝင်ရမည်ဖြစ်ပါသည်။ 
    mesh layer အတွက်မူ vertices များ၏ Z တန်ဖိုးများကိုအသုံးပြုပါသည်။
  * :guilabel:`Vertical scale` - ဒေါင်လိုက်ဝင်ရိုး (vertical axis) အတွက်  Scale factor 
    စကေးအရွယ်အစားကို တိုးမြှင့်ခြင်းသည် မြေမျက်နှာသွင်ပြင်ပုံစံ၏ အမြင့်ကို ပိုမိုချဲ့ကားစေမည်ဖြစ်ပါသည်။ 
  * :guilabel:`Tile resolution` - Tile တစ်ခုချင်းစီအတွက် terrain raster layer မှ sample (နမူနာ) မည်မျှကိုအသုံးပြုမည်။ 
    16px တစ်ခု၏ တန်ဖိုးဆိုသည်မှာ tile တစ်ခုချင်းစီ၏ geometry (ဂျီဩမေတြီ)တွင် 16x16 elevation samples များပါဝင်သည်ကိုဆိုလိုခြင်းဖြစ်ပါသည်။ 
    မြင့်မားသည့်ကိန်းဂဏန်းတန်ဖိုးများသည် ပို၍အသေးစိတ်ကျသည့် terrain tiles များကိုဖန်တီးပြီး ပိုမိုရှုပ်ထွေးသည့် rendering (2D သို့မဟုတ် 3D model မှ ဓါတ်ပုံရိုက်ကူးထားသကဲ့သို့ဖြစ်အောင်
    ဆောင်ရွက်ခြင်းလုပ်ငန်းစဉ်) ကို ဖြစ်ပေါ်စေပါသည်။ 
  * :guilabel:`Skirt height` - တစ်ခါတစ်ရံတွင် terrain ၏ tile များအကြားတွင် သေးငယ်သည့်အက်ကြောင်းလေးများကို တွေ့မြင်ကောင်းတွေ့မြင်နိုင်မည်ဖြစ်ပါသည်။ 
    ဤတန်ဖိုးကိုမြှင့်တင်ခြင်းသည် အက်ကြောင်းများကိုဖုံးကွယ်စေနိုင်ရန်အတွက် terrain tile များ၏အနီးတစ်ဝိုက်တွင် ဒေါင်လိုက်နံရံများ (vertical walls ("skirts")) ထပ်မံထည့်သွင်းပေးမည်ဖြစ်ပါသည်။
  * :guilabel:`Offset` - မြေပြင်အနေအထားကို အပေါ် သို့မဟုတ် အောက် ရွှေ့ကြည့်ပါ။ ဥပမာ ၎င်း၏အမြင့်ပေအား မြင်ကွင်း
    (scene) ထဲရှိ အခြားသော အရာဝတ္ထုများ၏ ground level (မြေပြင်အနိမ့်အမြင့်) ကို လိုက်၍ ချိန်ညှိခြင်းကိုဆိုလိုပါသည်။
    
    Scene ထဲတွင် layers များ၏ အမြင့်နှင့် terrain အမြင့်အကြား ကွဲလွဲမှုရှိပါက ၎င်းသည် များစွာအသုံးဝင်မည်ဖြစ်ပါသည်။ (ဥပမာ- နှိုင်းရဖြစ်သော ဒေါင်လိုက်အမြင့်ကိုသာအသုံးပြုသည့် point cloud များ)
    ထိုသို့ဖြစ်ပွားပါက မြေပြင်အနေအထား၏ အမြင့် (terrain elevation) ကို scene ထဲရှိ အရာဝတ္ထုများ၏ အမြင့်နှင့်ချိန်ညှိခြင်းသည် ကို navigation
    experience (ညွှန်ပြခြင်းအတွေ့အကြုံ) ပိုမိုတိုးတက်လာစေမည်ဖြစ်ပါသည်။ 

* Mesh layer ကို terrain အဖြစ်အသုံးပြုပါက Traingle setting :guilabel:`Triangles settings` (wireframe display (အရာဝတ္ထုတစ်ခု၏ ဖွဲ့စည်းထားမှုပုံစံ)၊ smooth triangles (ချောမွေ့သောတြိဂံများ)၊
  level of detail (အသေးစိတ်မြင်နိုင်သည့်အဆင့်)) နှင့် :guilabel:`Rendering colors settings` (uniform color (တူညီသည့်အရောင်)
  သို့မဟုတ် :ref:`color ramp based (အရောင်အမျိုးမျိုး) <color_ramp_shader>` အဖြစ်) တို့ကို စီစဉ်သတ်မှတ်ဆောင်ရွက်နိုင်ပါသည်။ အသေးစိတ်ကို :ref:`Mesh layer 3D properties <mesh3dview>` section တွင်ကြည့်ရှုနိုင်ပါသည်။
* |unchecked| :guilabel:`Terrain shading` - သည် terrain ကို မည်ကဲ့သို့ ပုံဖော်ပြသမည်ကို ရွေးချယ်ဆောင်ရွက်ခွင့်ပြုပါသည်။ 

  * Shading ပိတ်ထားခြင်း - Terrain color ကို map texture ဖြင့်သာ ဆုံးဖြတ်သည်။ 
  * Shading ဖွင့်ထားခြင်း -  Map texture (မြေပုံ၏ပုံပန်းသဏ္ဍာန်အသွင်အပြင်နှင့်အသားအနား) ၊ terrain normal vector (အမှတ်တစ်ခု၌ မျက်နှာပြင်နှင့်ထောင့်မှန်ကျရှိသည့် vector တစ်ခု)၊ scene light(s) (မြင်ကွင်းအလင်း) နှင့် terrain material ၏ :guilabel:`Ambient` (အရာဝတ္ထုတစ်ခု၏အနီးပတ်ဝန်းကျင်ရှိ အလင်းရောင်)၊ 
    :guilabel:`Specular` အရောင်များ (ပြန်လင်းတန်းများ၏အရောင်များ) နှင့် :guilabel:`Shininess` (တောက်ပမှု) တို့ကိုထည့်သွင်းစဉ်းစား၍ မြေပြင်အနေအထား၏အရောင် (terrain color) ကို 
    Phong ၏ shading model အသုံးပြု၍ ဆုံးဖြတ်ပါသည်။ 

Lights (အလင်းများ)
-------------------

အောက်ပါတို့ကိုထည့်သွင်းရန် :guilabel:`Lights` tab မှ |symbologyAdd| menu ကိုနှိပ်ပါ။  

* :guilabel:`Point lights` (၈)ခုအထိ ထည့်သွင်းနိုင်ပါသည် - ဧရိယာတစ်ခုအား စက်လုံးပုံစံအလင်း (sphere of light) ဖြင့် အလင်းပေးသကဲ့သို့ အလင်းရောင်အား
  နေရာအနှံ့သို့ထုတ်လွှတ်ပါသည်။ အလင်းနှင့်နီးကပ်စွာရှိသည့်အရာဝတ္ထုသည် ပိုမိုတောက်ပမည်ဖြစ်ပြီး ဝေးကွာသည့်နေရာတွင်
  ရှိသည့် အရာဝတ္ထုသည် မှောင်နေမည်ဖြစ်ပါသည်။ Point light (အလင်းသည် အမှတ်တစ်ခုမှလာပြီး နေရာအနှံ့သို့ လင်းစေသည့်အလင်း) တစ်ခုတွင် သတ်မှတ်ထားသည့် တည်နေရာ
  (:guilabel:`X` ၊ :guilabel:`Y` နှင့် :guilabel:`Z`)၊ :guilabel:`Color`၊ 
  :guilabel:`Intensity` (ပြင်းအား) နှင့် :guilabel:`Attenuation` (အလင်းရောင်အား မှေးမှိန်စေနိုင်ခြင်း) တို့ပါရှိပါသည်။ 
* :guilabel:`Directional lights` (၄)ခုအထိထည့်သွင်းနိုင်ပါသည် - အမြဲတမ်းလင်းနေသည့် (ဥပမာ - နေ) နေရာတစ်ခုကိုသာဗဟိုပြုထားပြီး အရာဝတ္ထုများနှင့်အလွန်ဝေးသည့်အကွာအဝေးရှိ  ဖလက်ရှ်မီးကြီးမှ ရရှိသည့်အလင်းရောင်အား နမူနာယူထားပါသည်။ ၎င်းသည် ပြိုင်လင်းတန်းများကို ဦးတည်ရာတစ်ခုဖြင့်သာ ထုတ်လွှတ်သော်လည်း နေရာအနှံ့ကို အလင်းရရှိစေပါသည်။ 
  Directional light (အရပ်မျက်နှာတစ်ခုကိုဦးတည်သော အလင်း) တစ်ခုသည် :guilabel:`Azimuth` (မြောက်အရပ်မှ လက်ယာရစ် တိုင်းတာရသောထောင့်) အရ rotate (လှည့်ပတ်ခြင်း) ပြုလုပ်နိုင်ပြီး :guilabel:`Altitude` (အမြင့်)၊ 
  :guilabel:`Color` (အရောင်) နှင့် :guilabel:`Intensity` (ပြင်းအား) တို့ပါရှိပါသည်။ 

.. _figure_3dmap_configlights:

.. figure:: img/3dmapconfiguration_lights.png
   :align: center

   3D မြေပုံအလင်းများ သတ်မှတ်ခြင်း Dialog

.. _shadows:

Shadow (အရိပ်)
---------------

Scene အတွင်း အရိပ်များကို ပြသရန် |unchecked| :guilabel:`Show shadows` ကို အမှန်ခြစ်ပါ။ 

* :guilabel:`Directional light`
* :guilabel:`Shadow rendering maximum distance` - အထူးသဖြင့် ကင်မရာကို ရေပြင်ညီတစ်လျှောက်ကြည့်ရှုပါက အလွန်
  ဝေးကွာသည့် အရာဝတ္ထုများ၏ အရိပ်များကို rendering ပြုလုပ်ခြင်းကို ရှောင်ရှားရန်။
* :guilabel:`Shadow bias` - မြေပုံအရွယ်အစားအကြားကွာခြားချက်များရှိခြင်းကြောင့် ဖြစ်ပေါ်လာနိုင်သည့် အချို့သောဧရိယာများကို အခြားဧရိယာများထက် ပိုမိုမှောင်စေသည့် self-shadowing effects ကို ရှောင်ရှားရန်။ နည်းလေ ပိုကောင်းလေ ဖြစ်သည်။
* :guilabel:`Shadow map resolution` - အရိပ်များကိုပိုမိုထင်ရှားပြတ်သားအောင်ပြုလုပ်ရန်။ ၎င်းသည် 
  resolution parameter (resolution သတ်မှတ်ချက်များ) အလွန်မြင့်မားနေပါက ကောင်းမွန်ခြင်းမရှိသည့်သရုပ်ဖော်ပြမှု (performance) ကို ဖြစ်ပေါ်စေနိုင်ပါသည်။

Camera & Skybox (ကင်မရာနှင့် မြင်ကွင်းများကိုကြည့်ရှုရန် ထိပ်ဘက်တွင်သီးသန့်ရှိသည့် box) 
-----------------------------------------------------------------------------------------

ယခု tab တွင် ကင်မရာ၊ 3D axis (3D ဝင်ရိုး)၊  navigation synchronization (လမ်းညွှန်ပြသခြင်းဆိုင်ရာများ တစ်ပြိုင်နက်ဖြစ်စေခြင်း)နှင့် skybox ကဲ့သို့သော အမျိုးမျိုးသောသတ်မှတ်ချက် (parameter) များကိုကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်။ 

.. _figure_3dmap_config_camera:

.. figure:: img/3dmapconfiguration_camera.png
   :align: center

   3D မြေပုံ Camera သတ်မှတ်ခြင်း Dialog

* :guilabel:`Camera` parameter group သည် :menuselection:`Settings --> Options --> 3D` dialog တွင် 
  ရှိနေသည့် :ref:`default camera settings <3d_options>` အချို့ကို ပြန်လည်ပြင်ဆင်မွမ်းမံပါသည်။
* 3D axis tool ကို ဖွင့်ရန် |unchecked| :guilabel:`Show 3D Axis` ကို အမှန်ခြစ်ပါ။ ဤ parameter group သည်  axis အမျိုးအစားနှင့် ၎င်း၏ တည်နေရာသတ်မှတ်ဆောင်ရွက်ခြင်းများပြုလုပ်နိုင်ရန်ခွင့်ပြုထားပါသည်-

  * :guilabel:`Coordinate Reference System` type ဖြင့် orthogonal axis (တစ်ခုနှင့်တစ်ခုထောင့်မှန်ကျနေသည့်ဝင်ရိုး) တစ်ခုအား ဖော်ပြသွားမည်ဖြစ်သည်။
  * :guilabel:`Cube` type ဖြင့် 3D ကုဗတုံး (3D cube) တစ်ခုကို ကိုယ်စားပြုဖော်ပြမည်ဖြစ်သည်။ အဆိုပါကုဗတုံး၏ မျက်နှာပြင်များအား ကင်မရာမြင်ကွင်းများ ပြောင်းလဲကြည့်ရှုရာတွင် အသုံးပြုနိုင်မည်ဖြစ်သည်။ 
    ဥပမာ - မြောက်ဘက်အရပ်မှ ကြည့်ရှုရန် :guilabel:`north` ကိုနှိပ်၍ ကင်မရာကို သတ်မှတ်ပေးပါ။  

.. tip:: ၎င်း၏တည်နေရာ၊ အမျိုးအစားနှင့် ကင်မရာမြင်ကွင်းကို အမြန်သတ်မှတ်ရန် 3D ဝင်ရိုးကို ညာဖက်ကလစ်နှိပ်ပါ။

  .. _figure_3dmap_config_3daxis_menu:

  .. figure:: img/3dmapconfiguration_3daxis_menu.png
     :align: center

     3D ဝင်ရိုး အကြောင်းအရာများနှင့်သက်ဆိုင်သည့် menu

* :guilabel:`Navigation Synchronization` parameter group သည် 2D view အား 3D camera position နှင့်ဖြစ်စေ
  3D camera position အား 2D view နှင့်ဖြစ်စေ သို့မဟုတ် bi directional synchronization (ဦးတည်ရာနှစ်ခုကိုတစ်ပြိုင်နက်ဖြစ်စေခြင်း) ကို တစ်ပြိုင်နက်ပြောင်းလဲရန် (synchronize) option များကို ထည့်သွင်းထားပါသည်။
  နောက်ဆုံး option သည် 2D map view အပေါ်တွင် 3D camera မှ မြင်နိုင်သည့် extent ကိုပြသပါသည်။ 

* Scene ထဲတွင် skybox rendering ကို ဖွင့်ရန် |unchecked| :guilabel:`Show skybox` ကိုအမှန်ခြစ်ပါ။ skybox အမျိုးအစားသည် -
  
  * 360\° မြင်ကွင်းကို ထောက်ပံ့ထားသည့်ဖိုင်တစ်ခု (single file) တစ်ခုနှင့်အတူ :guilabel:`Panoramic texture`၊ 
  * Scene ပါဝင်သည့် box ၏ မျက်နှာခြောက်ဖက်လုံးအတွက် texture file နှင့်အတူ :guilabel:`Distinct faces`၊

  Skybox ၏ texture image file များသည် disk ပေါ်ရှိဖိုင်များ၊  remote URLs များ သို့မဟုတ် project အတွင်းတွင် မထင်မရှားရှိနေသည့် ဖိုင်များဖြစ်နိုင်ပါသည်။ 
  (:ref:`more details <embedded_file_selector>`)

Advanced (အဆင့်မြင့် အပိုင်းများ)
----------------------------------

* :guilabel:`Map tile resolution` - 2D map images များ၏ အကျယ်နှင့် အမြင့်ကို terrain tiles များအတွက် texture အဖြစ်အသုံးပြုပါသည်။ 
  256px သည် tile တစ်ခုချင်းစီသည် 256x256 pixels ရှိ image အဖြစ်သို့ render ပြုလုပ်မည်ကိုဆိုလိုပါသည်။
  မြင့်မားသည့်ကိန်းဂဏန်းတန်ဖိုးများသည် ပို၍အသေးစိတ်သည့် terrain tiles များကို ဖန်တီးနိုင်ပြီး rendering complexity (rendering ဖြစ်စဉ်ရှုပ်ထွေးမှု) အား ပိုမိုမြင့်မားစေပါသည်။ 
* :guilabel:`Max. screen error` - Terrain tiles များအား ပိုမိုအသေးစိတ်သည့် tiles များဖြင့် 
  အပြောင်းအလဲပြုလုပ်ရာတွင် threshold (တန်ဖိုးသတ်မှတ်ချက်) အားဆုံးဖြတ်ပေးပါသည် (အပြန်အလှန်အားဖြင့်) - ဆိုလိုသည်မှာ 3D view သည် အရည်အသွေးမြင့်မားသည့် tiles များကို မည်ကဲ့သို့အသုံးပြုမည်ကိုဆုံးဖြတ်ခြင်းဖြစ်ပါသည်။
  နည်းပါးသည့် ကိန်းဂဏန်းတန်ဖိုးသည် scene အတွင်းတွင်ပို၍အသေးစိတ်ပြီး rendering complexity အား ပိုမိုမြင့်မားစေပါသည်။
* :guilabel:`Max. ground error` - tiles များအား ပိုမိုအသေးစိတ်သည့် tiles များအဖြစ်သို့ ခွဲခြမ်းစိတ်ဖြာသည့် terrain tiles များ၏ 
  ကြည်လင်ပြတ်သားမှု  (resolution) သည် ရပ်တံ့သွားမည်ဖြစ်ပါသည်။ (၎င်းတို့အားခွဲခြားစိတ်ဖြာခြင်းသည် မည့်သည့် အသေးစိတ်ကိုမျှ ထပ်မံမရရှိနိုင်တော့ပါ)
  အဆိုပါ ကိန်းဂဏန်းတန်ဖိုးသည် tiles များ၏ ့hierarchy ၏ အနက်ကို ကန့်သတ်ထားပါသည် - နည်းပါးသည့် ကိန်းဂဏန်းတန်ဖိုးသည် hierarchy ၏ အနက် (depth) ပိုမိုဖြစ်စေပြီး
  rendering complexity အား ပိုမိုမြင့်မားစေပါသည်။
* :guilabel:`Zoom levels` - zoom levels များ၏ ကိန်းဂဏန်းများကိုဖော်ပြပါသည်။ (map tile resolution နှင့် max. ground error (အမြင့်ဆုံးမြေပြင်ကွဲလွဲမှု) အပေါ်မူတည်ပါသည်)
* |unchecked| :guilabel:`Show labels` - Map labels (မြေပုံအညွှန်းများ) ကို အဖွင့်/အပိတ် ပြုလုပ်သည်။
* |unchecked| :guilabel:`Show map tile info` - Terrain tiles များအတွက် border (နယ်နိမိတ်) နှင့် tile အရေအတွက်များပါဝင်ပါသည်။ (terrain issues များကိုဖြေရှင်းရာတွင်အသုံးဝင်ပါသည်။)
* |unchecked| :guilabel:`Show bounding boxes` - Terrain tiles များ၏ 3D bounding boxes (3D model တစ်ခုလုံးကိုဖော်ပြသည့် ထောင့်မှန်စတုဂံ) ကိုဖော်ပြပါသည်။
  (terrain issues များကိုဖြေရှင်းရာတွင်အသုံးဝင်ပါသည်။)
* |unchecked| :guilabel:`Show camera's view center`
* |unchecked| :guilabel:`Show camera's rotation center`
* |unchecked| :guilabel:`Show light sources` - အလင်းအရင်းအမြစ် စက်လုံးတစ်ခုကိုဖော်ပြပါသည်။ Scene contents (မြင်ကွင်းပါအကြောင်းအရာများ) နှင့်လိုက်လျောညီထွေရှိအောင်
  အလင်းအရင်းအမြစ်များထားရှိမှုများအား ပြန်လည်နေရာချထားခြင်းကို ပိုမိုလွယ်ကူစေပါသည်။
* |unchecked| :guilabel:`Show frames per second (FPS)` (စက္ကန့်အလိုက် frame များကိုပြသခြင်း)
* |unchecked| :guilabel:`Show debug overlay` - အချို့အသုံးဝင်သည့် debugging နှင့် profiling information (ကွန်ပျူတာ hardware နှင့် software များမှတွေ့ရှိသည့် အမှားများကို ပြင်ဆင်ခြင်းများနှင့် ရှိပြီးသားအကြောင်းအရာများကို အခြေခံ၍ သတင်းအချက်အလက်များကို လေ့လာဆန်းစစ်သိမ်းဆည်းခြင်း) ကို ပြသနိုင်သည့် 
  visual overlay။ အထူးသဖြင့် ၎င်းသည် frame graph (ရှုပ်ထွေးသည့် rendering pipelines များကို ကိုင်တွယ်ထိန်းချုပ်သည့် ဒီဇိုင်းပုံစံ) နှင့် scene graph (scene ထဲရှိ အရာဝတ္ထုများ၊ ဆက်စပ် attributes များနှင့် ၎င်းတို့အကြားရှိဆက်နွယ်မှုများကို သေချာဖော်ပြထားမှု) တို့ကို လွယ်ကူလျင်မြန်စွာတွေ့ရှိစေနိုင်ပါသည်။

.. _eye_dome_lighting:

* |unchecked| :guilabel:`Show Eye Dome Lighting` (EDL) - အနက် (depth) ကို ပိုမိုသိသာထင်ရှားစွာမြင်စေသည့် post processing effect တစ်ခုဖြစ်ပါသည်။ Pixel တစ်ခုချင်းစီ၏ အနက် (ကင်မရာအကွာအဝေး) ကို ၎င်း၏အနီးတွင်ရှိသည့် pixel များ၏ အနက်နှင့် နှိုင်းယှဉ်ပြီး အနက်ကွာခြားချက်အပေါ်မူတည်၍ highlight (သိသာထင်ရှားအောင်ပြသ) လုပ်ခြင်းခံရပြီး သိသာနေသည့်အစွန်းများကို ထင်ရှားပေါ်လွင်စေပါသည်။ Scene တစ်ခုလုံးအပေါ်တွင် သက်ရောက်မှုရှိပြီး :ref:`Eye dome Lighting <eye_dome_lighting>` နှင့် ပေါင်းစပ်နိုင်ပါသည်။ အောက်ဖော်ပြပါ ကန့်သတ်ချက်များကို ထိန်းချုပ်ဆောင်ရွက်နိုင်ပါသည်- 

  * :guilabel:`Lighting strength` - အလင်းအမှောင် (contrast) ကိုတိုးစေပြီး ပိုမိုကောင်းမွန်သည့် အနက်အမြင်ရှုထောင့် (depth perception) ကိုရရှိစေသည်။ 
  * :guilabel:`Lighting distance` - Center pixels မှ အသုံးပြုထားသည့် pixels များကြားရှိ အကွာအဝေးကို ကိုယ်စားပြုဖော်ပြပြီး အနားသတ်များကို ထူစေသည့် သက်ရောက်မှုရှိပါသည်။

.. _ambient_occlusion:

* Screen-space |unchecked| :guilabel:`Ambient Occlusion` (SSAO) ကိုပေါင်းထည့်ခြင်း : ambient lightning ထိတွေ့မှုနည်းသည့်ဧရိယာများကို ပိုမိုမှောင်သည့် အရိပ်ချခြင်းကို
  အသုံးပြု၍ depth perception ကို တိုးမြှင့်ရရှိစေသည့် post processing effect တစ်ခုဖြစ်ပါသည်။ Scene တစ်ခုလုံးအား သက်ရောက်မှုရှိပြီး :ref:`Eye dome Lighting <eye_dome_lighting>` နှင့်ပေါင်းစပ်နိုင်ပါသည်။
  အောက်ဖော်ပြပါသတ်မှတ်ချက်များကို ထိန်းချုပ်ကိုင်တွယ်ဆောင်ရွက်နိုင်ပါသည်- 

  * :guilabel:`Radius` - Ambient occlusion တွက်ချက်ရန် မည်မျှအထိရောက်ရှိမည်။
  * :guilabel:`Intensity` - Effect (အကျိုးသက်ရောက်မှု) မည်မျှပြင်းထန်သင့်သည်။  (မြင့်မားသည့် ပမာဏတန်ဖိုးသည် အရာဝတ္ထုများကို ပိုမိုမှောင်မဲစေပါသည်)
  * :guilabel:`Occlusion threshold` - Effect ဖြစ်ပေါ်လာစေရန် အနီးနားရှိအမှတ် မည်မျှကို ပိတ်ထားရန်လိုအပ်သည်။
    (ပမာဏတန်ဖိုး ၅၀% အောက်နည်းပါးပါက ထွက်လာသည့်ရလဒ်ကို ပို၍မှောင်စေမည်ဖြစ်ပါသည်။ သို့ရာတွင် ပိုမိုကြီးမားသည့် occlusion အကွာအဝေးပမာဏကို ပေးစွမ်းနိုင်စွမ်းရှိပါသည်။)

.. _figure_3dmaps_edl_ssao:

.. figure:: img/3dmap_edl_ssao.png
   :align: center

   Eye Dome Lighting (EDL) နှင့်/သို့မဟုတ် Screen-Space Ambient Occlusion (SSAO) အသုံးပြု၍ 3D map အတွင်းရှိ Point clouds များအား ပုံဖော်ပြသခြင်း

   အထက်မှ၊ ဘယ်ဘက်မှညာဘက်သို့ - Effect အသုံးပြုထားခြင်းမရှိပါ။ -- SSAO တစ်ခုတည်းသာ -- EDL တစ်ခုတည်းသာ -- SSAO နှင့် EDL

* |unchecked| :guilabel:`Debug Shadow Map` သည်  scene အား အရိပ်များအတွက်အသုံးပြုသည့် အလင်း၏ ရှုထောင့်မှ
  red-black image အဖြစ် render ပြုလုပ်ပုံဖော်ပါသည်။ (ပြဿနာများဖြေရှင်းရန်အတွက်)
  Widget ကို 3D map view ၏ :guilabel:`Size` နှင့်အညီ အချိုးကျသတ်မှတ်ထားပြီး :guilabel:`Corner` တွင် dock (နေရာအထိုင်ချထား) ပြုလုပ်ထားပါသည်။ 
* |unchecked| :guilabel:`Debug Depth Map` သည် အနီးကပ်ရှိသည့် pixels များကို ပို၍မှောင်စေပြီး scene ၏ depth map အား image တစ်ခုအဖြစ် render ပြုလုပ်ပေးသည်။ (ပြဿနာများဖြေရှင်းရန်အတွက်)
  Widget ကို 3D map view ၏ :guilabel:`Size` နှင့်အညီ အချိုးကျသတ်မှတ်ထားပြီး :guilabel:`Corner` (ထောင့်) တစ်ခုတွင် dock ပြုလုပ်ထားပါသည်။ 


.. _`3d_navigation`:

Navigation options (လမ်းညွှန်ပြသခြင်းဆိုင်ရာ ရွေးချယ်မှုများ)
==============================================================

Map view အား 3D တွင် ကြည့်ရှုကိုင်တွယ်ဆောင်ရွက်ခြင်းများပြုလုပ်ရန်-

* Terrain ကိုစောင်း (Tilt) ပါ။ (Window ၏ center ကိုဖြတ်၍ horizonal axis (ရေပြင်ညီဝင်ရိုး) အတိုင်း လှည့်ခြင်း)

  * |tiltUp| :sup:`Tilt up` နှင့် |tiltDown| :sup:`Tilt down` tools များကို နှိပ်ပါ။ 
  * :kbd:`Shift` ကို ဖိ၍ up/down keys များကို အသုံးပြုပါ။ 
  * မောက်စ်၏ အလယ်ရှိခလုတ်ကိုဖိထားပြီး မောက်စ်ကို forward (ရှေ့သို့ရွှေ့ခြင်း)/ backward (နောက်သို့သို့ရွှေ့ခြင်း) လုပ်ဆောင်ပါ။
  * :kbd:`Shift` ကိုဖိ၍ မောက်စ်၏ ဘယ်ဘက်ခလုတ်အားဖိထားပြီး forward (ရှေ့သို့ရွှေ့ခြင်း)/ backward (နောက်သို့သို့ရွှေ့ခြင်း) လုပ်ဆောင်ပါ။

* Terrain ကို လှည့်ရန် (Window ၏ ဗဟိုကိုဖြတ်၍  ဒေါင်လိုက်ဝင်ရိုးအတိုင်း)

  * ကြည့်ရှုမည့်ဦးတည်ရာ (watching direction) အတိုင်း navigation widget ၏ သံလိုက်အိမ်မြှောင်အား လှည့်ပါ။
  * :kbd:`Shift` ကိုဖိ၍ left (ဘယ်) /right (ညာ) keys များကို အသုံးပြုပါ။ 
  * မောက်စ်၏ အလယ်ရှိခလုတ်ကိုဖိထားပြီး မောက်စ်ကို ဘယ်/ညာသို့ ဆွဲရွှေ့ပါ။
  * :kbd:`Shift` ကိုဖိ၍ မောက်စ်၏ ဘယ်ဘက်ခလုတ်အားဖိထားပြီး မောက်စ်ကို ဘယ်/ညာသို့ ဆွဲရွှေ့ပါ။

* ကင်မရာ၏တည်နေရာ (view center နှင့်အတူ) အား ပြင်ဆင်ပြောင်းလဲမှုများပြုလုပ်ရန်၊ ၎င်းအား ရေပြင်ညီ (horizontal plan) အတွင်း အပြောင်းအရွှေ့ပြုလုပ်ရန်။

  * မောက်စ်၏ ဘယ်ဘက်ခလုတ်အား ဖိထား၍ မောက်စ်ကိုဆွဲရွှေ့ပါ။  :sup:`Camera control` button ကို ဖွင့်ထားရမည်ဖြစ်ပါသည်။
  * navigation widget ၏ ဦးတည်ရာပြမြှားများ (directional arrows) များကို နှိပ်ထားပါ။
  * ကင်မရာအား အရှေ့နှင့်အနောက်၊ ဘယ်နှင့်ညာ အသီးသီးသို့ ရွှေ့ရန် up/down/left/right (ပေါ်/အောက်/ဘယ်/ညာ) keys များကိုအသုံးပြုပါ။

* ကင်မရာ၏ altitude (အမြင့်) အားပြောင်းလဲပြင်ဆင်ခြင်း - ကီးဘုတ်ရှိ :kbd:`Page Up`/:kbd:`Page Down` keys ကိုနှိပ်ပါ။ 
* ကင်မရာ၏ ဦးတည်ချက်အား ပြောင်းလဲပြင်ဆင်ခြင်း (ကင်မရာသည် ၎င်း၏တည်နေရာတွင်သာရှိနေမည်ဖြစ်သော်လည်း view center point မှာမူ ရွေ့နေမည်ဖြစ်ပါသည်။)

  * ကင်မရာအား အပေါ်/အောက် နှင့် ဘယ်/ညာ ရွှေ့ရန် ကီးဘုတ်ရှိ :kbd:`Ctrl` ကို ဖိ၍ the arrow keys ကို အသုံးပြုပါ။ 
  * ကီးဘုတ်ရှိ :kbd:`Ctrl` ကို ဖိထားပြီး မောက်စ်၏ ဘယ်ဘက်ခလုတ်အား ဖိထား၍ မောက်စ်ကို ဆွဲရွှေ့ပါ။

* Zoom ချဲ့ခြင်းနှင့်ချုံ့ခြင်း

  * Navigation widget တွင်ပါရှိသည့် သက်ဆိုင်ရာ |zoomIn| :sup:`Zoom In` နှင့် |zoomOut| :sup:`Zoom Out` ကို ဖိထားပါ။
  * မောက်စ်၏ ဘီးလုံးကို scroll လုပ်ပါ။ (ပိုမိုကောင်းမွန်သည့် မြင်ကွင်းများ ရရှိစေရန် :kbd:`Ctrl` key ကို နှိပ်ထားပါ)
  * Zoom in (အောက်ဘက်သို့ဖိဆွဲပါ) နှင့် zoom out (အပေါ်ဘက်သို့ဖိဆွဲပါ) ပြုလုပ်ရန် မောက်စ်၏ ညာဘက်ရှိခလုတ်ကိုဖိ၍ မောက်စ်အား ဖိဆွဲပါ။ 

ကင်မရာ၏မြင်ကွင်းအား နဂိုမူလအနေအထားသို့ ပြန်လည်ရောက်ရှိရန် 3D canvas panel ၏ အပေါ်ဘက်ထိပ်တွင် ရှိသည့် |zoomFullExtent| :sup:`Zoom Full` button ကိုနှိပ်ပါ။

.. _`create_animation`:

Creating an animation (လှုပ်ရှားပုံရိပ်တစ်ခုအား ဖန်တီးခြင်း)
=============================================================

Animation တစ်ခုသည် keyframes - သတ်မှတ်ထားသည့်အချိန်များအတွင်းရှိသည့် ကင်မရာ၏တည်နေရာပေါ်တွင် အခြေခံထားပါသည်။ 
Animation တစ်ခုအားဖန်တီးရန်-

#. Animation player widget ကို ပြသရန် |play| :sup:`Animations` tool ကို ဖွင့်ပါ။ 
#. |symbologyAdd| :sup:`Add keyframe` button ကို ကလစ်နှိပ်ပြီး  :guilabel:`Keyframe time` ကို စက္ကန့် ဖြင့်ထည့်သွင်းပါ။ 
   လက်ရှိတွင် :guilabel:`Keyframe` combo box သည် သတ်မှတ်ထားသည့်အချိန် (set time) ကို ပြသမည်ဖြစ်ပါသည်။
#. Navigation tools ကို အသုံးပြု၍ လက်ရှိ keyframe time နှင့် ဆက်စပ်မှုရှိစေရန် ကင်မရာ၏ တည်နေရာကို ရွှေ့ပါ။
#. Keyframes (အချိန်နှင့် တည်နေရာများနှင့်အတူ) များကို လိုအပ်သလိုထပ်မံထည့်သွင်းလိုပါက အထက်တွင်ဖော်ပြခဲ့သည့်အဆင့်များအတိုင်းဆောင်ရွက်ပါ။ 
#. Animation ကို preview ကြည့်ရှုရန် |play| button ကိုနှိပ်ပါ။
   QGIS သည် ကင်မရာ၏ တည်နေရာ/အလှည့် များကို အသုံးပြု၍ သတ်မှတ်ထားသည့်အချိန်များအတွင်း scene များကို ထုတ်ပေးမည်ဖြစ်ပြီး ၎င်းတို့အား ထို keyframes များအကြားတွင် interpolation (ရှိပြီးသားအရာများကိုအခြေခံပြီး မရှိသေးသောအရာများကိုဖော်ဆောင်ခြင်း) ဆောင်ရွက်သွားမည်ဖြစ်ပါသည်။ 
   Animation များအတွက် အမျိုးမျိုးသော :guilabel:`Interpolation` mode များကို ရရှိနိုင်ပါသည်။ (ဥပမာ - linear ၊ inQuad ၊ outQuad ၊ inCirc... -- အသေးစိတ်အား
   https://doc.qt.io/qt-5/qeasingcurve.html#EasingFunction-typedef တွင်ကြည့်ရှုရန်)

   Animation အား time slider (အချိန်ကိုဆွဲ၍ရွှေ့နိုင်သည့်အရာ) ကို ရွှေ့၍ ကြိုတင်ကြည့်ရှုခြင်း (preview) ဆောင်ရွက်နိုင်ပါသည်။
   :guilabel:`Loop` box အား အမှန်ခြစ်ထားခြင်းဖြင့် animation အား ထပ်ခါတလဲပြန်လည်ပြသခြင်းကို 
   ဆောင်ရွက်နိုင်မည်ဖြစ်ပြီး animation အား ရပ်လိုပါက |play| ကို ကလစ်နှိပ်၍ ရပ်တံ့နိုင်ပါသည်။

Scene များကို ကိုယ်စားပြုဖော်ပြသည့် series of images (အတွဲလိုက်ပုံရိပ်) များကို ထုတ်လုပ်နိုင်ရန်အတွက် |fileSave| :sup:`Export animation frames` ကို ကလစ်နှိပ်ပါ။
ဖိုင်နာမည် filename :guilabel:`Template` နှင့် သိမ်းဆည်းရန်လမ်းကြောင်း :guilabel:`Output directory` စသည်တို့အပြင် :guilabel:`Frames persecond` အရေအတွက်၊  :guilabel:`Output width` နှင့် :guilabel:`Output height` တို့ကိုပါ ပြုပြင်သတ်မှတ်ဆောင်ရွက်နိုင်ပါသည်။ 

3D vector layers (သုံးဖက်မြင် Vector layer များ)
=================================================

3D map view တွင် အမြင့်တန်ဖိုးများပါဝင်သည့် vector layer တစ်ခုကို vector layer properties ၏ :guilabel:`3D View` section တွင်ပါရှိသည့် 
:guilabel:`Enable 3D Renderer` ကို အမှန်ခြစ်ပေးခြင်းဖြင့် ပြသနိုင်ပါသည်။
3D vector layer အား ပုံဖော်ပြသခြင်း ဆောင်ရွက်နိုင်ရန်အတွက် မြောက်များစွာသော option များပါဝင်ပါသည်။

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |3d| image:: /static/common/3d.png
   :width: 1.5em
.. |3dNavigation| image:: /static/common/mAction3DNavigation.png
   :width: 1.3em
.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
.. |dock| image:: /static/common/dock.png
   :width: 1.5em
.. |fileSave| image:: /static/common/mActionFileSave.png
   :width: 1.5em
.. |identify| image:: /static/common/mActionIdentify.png
   :width: 1.5em
.. |measure| image:: /static/common/mActionMeasure.png
   :width: 1.5em
.. |new3DMap| image:: /static/common/mActionNew3DMap.png
   :width: 1.5em
.. |options| image:: /static/common/mActionOptions.png
   :width: 1em
.. |pan| image:: /static/common/mActionPan.png
   :width: 1.5em
.. |play| image:: /static/common/mActionPlay.png
   :width: 1.5em
.. |saveMapAsImage| image:: /static/common/mActionSaveMapAsImage.png
   :width: 1.5em
.. |showPresets| image:: /static/common/mActionShowPresets.png
   :width: 1.5em
.. |symbologyAdd| image:: /static/common/symbologyAdd.png
   :width: 1.5em
.. |tiltDown| image:: /static/common/mActionTiltDown.png
   :width: 1.5em
.. |tiltUp| image:: /static/common/mActionTiltUp.png
   :width: 1.5em
.. |unchecked| image:: /static/common/unchecked.png
   :width: 1.3em
.. |zoomFullExtent| image:: /static/common/mActionZoomFullExtent.png
   :width: 1.5em
.. |zoomIn| image:: /static/common/mActionZoomIn.png
   :width: 1.5em
.. |zoomOut| image:: /static/common/mActionZoomOut.png
   :width: 1.5em
