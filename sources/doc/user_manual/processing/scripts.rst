
.. highlight:: python
   :linenothreshold: 5

Writing new Processing algorithms as Python scripts (Processing algorithm အသစ်များကို Python script များအဖြစ် ရေးသားခြင်း)
===========================================================================================================================

.. only:: html

   .. contents::
      :local:

Python ကိုအသုံးပြုပြီး Processing algorithm များရေးသားခြင်းအတွက် နည်းလမ်း နှစ်မျိုးရှိပါသည်။

* :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ကို :ref:`ချဲ့ထွင်ခြင်း <scripts_extend>` 
* :ref:`@alg decorator ကိုအသုံးပြုခြင်း <scripts_alg>`

QGIS အတွင်းတွင် code များရေးနိုင်သော :guilabel:`Processing Script Editor` ကိုဖွင့်ရန် :guilabel:`Processing Toolbox` ၏အပေါ်ဘက် :guilabel:`Scripts` menu ထဲရှိ :guilabel:`Create new script` ကိုအသုံးပြုနိုင်ပါသည်။ လုပ်ငန်းကိုလွယ်ကူရိုးရှင်းစေရန်အတွက် ၎င်း menu မှ :guilabel:`Create new script from template` ကိုအသုံးပြုပြီး script template တစ်ခုဖြင့်စတင်နိုင်ပါသည်။ ၎င်းသည် :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ကို ချဲ့ထွင်ပေးသော template တစ်ခုကိုဖွင့်ပေးပါသည်။

:file:`.py` extension တစ်ခုဖြင့် :file:`scripts` folder ထဲတွင် script ကိုသိမ်းဆည်းလျှင် algorithm သည် :guilabel:`Processing Toolbox` ထဲတွင် အသုံးပြုနိုင်မည်ဖြစ်သည်။

.. _scripts_extend:

Extending QgsProcessingAlgorithm (QgsProcessingAlgorithm ကိုချဲ့ထွင်ခြင်း)
---------------------------------------------------------------------------

အောက်ပါ code များသည်

#. Vector layer တစ်ခုကို ထည့်သွင်းအသုံးပြုသော အချက်အလက်အဖြစ် အသုံးပြုပါသည်။
#. Feature အရေအတွက်ကို ရေတွက်ပါသည်။
#. Buffer လုပ်ဆောင်မှုတစ်ခုဖန်တီးပေးပါသည်။
#. Buffer လုပ်ဆောင်မှု၏ရလာဒ်မှ raster layer တစ်ခုဖန်တီးပေးပါသည်။
#. Buffer layer ၊ raster layer နှင့် feature အရေအတွက်များကို ပြန်ထုတ်ပေးပါသည်။

.. testcode::

    from qgis.PyQt.QtCore import QCoreApplication
    from qgis.core import (QgsProcessing,
                           QgsProcessingAlgorithm,
                           QgsProcessingException,
                           QgsProcessingOutputNumber,
                           QgsProcessingParameterDistance,
                           QgsProcessingParameterFeatureSource,
                           QgsProcessingParameterVectorDestination,
                           QgsProcessingParameterRasterDestination)
    from qgis import processing


    class ExampleProcessingAlgorithm(QgsProcessingAlgorithm):
        """
        Vector layer တစ်ခုကို အသုံးပြုပြီး အချို့သော layer အသစ်များကိုဖန်တီးကာ ရလာဒ်အချို့ပြန်ထုတ်ပေးသည့် နမူနာ algorithm ဖြစ်ပါသည်။
        """

        def tr(self, string):
            """
            self.tr() function ဖြင့် ဘာသာပြန်နိုင်သော စာသားကိုပြန်ထုတ်ပေးပါသည်။
            """
            return QCoreApplication.translate('Processing', string)

        def createInstance(self):
            # Algorithm ၏ မိတ္တူအသစ်တစ်ခုကို ပြန်ထုတ်ပေးရပါမည်။
            return ExampleProcessingAlgorithm()

        def name(self):
            """
            တမူထူးခြားသော algorithm နာမည်ကို ပြန်ထုတ်ပေးပါသည်။
            """
            return 'bufferrasterextend'

        def displayName(self):
            """
            ဘာသာပြန်ထားသော algorithm အမည်ကို ပြန်ထုတ်ပေးပါသည်။
            """
            return self.tr('Buffer and export to raster (extend)')

        def group(self):
            """
            ၎င်း algorithm နှင့်သက်ဆိုင်သော အုပ်စု၏အမည်ကို ပြန်ထုတ်ပေးပါသည်။
            """
            return self.tr('Example scripts')

        def groupId(self):
            """
            ၎င်း algorithm နှင့်သက်ဆိုင်သော အုပ်စု၏ တမူထူးခြားသည့် ID ကိုပြန်ထုတ်ပေးပါသည်။
            """
            return 'examplescripts'

        def shortHelpString(self):
            """
            Algorithm အတွက် အကူအညီစာသားအတိုတစ်ခုကို ပြန်ထုတ်ပေးပါသည်။
            """
            return self.tr('Example algorithm short description')

        def initAlgorithm(self, config=None):
            """
            Algorithm တွင်ထည့်သွင်းအသုံးပြုသော အချက်အလက်နှင့် ရလာဒ်များကို ဤတွင်သတ်မှတ်ပါသည်။
            """
            # 'INPUT' သည် အဓိကထည့်သွင်းလုပ်ဆောင်သော parameter များအတွက် အကြုံပြုထားသော အမည် ဖြစ်ပါသည်။
            self.addParameter(
                QgsProcessingParameterFeatureSource(
                    'INPUT',
                    self.tr('Input vector layer'),
                    types=[QgsProcessing.TypeVectorAnyGeometry]
                )
            )
            self.addParameter(
                QgsProcessingParameterVectorDestination(
                    'BUFFER_OUTPUT',
                    self.tr('Buffer output'),
                )
            )
            # 'OUTPUT' သည် အဓိကထွက်လာသည့် ရလာဒ် parameter အတွက် အကြုံပြုထားသော အမည်ဖြစ်ပါသည်။
            self.addParameter(
                QgsProcessingParameterRasterDestination(
                    'OUTPUT',
                    self.tr('Raster output')
                )
            )
            self.addParameter(
                QgsProcessingParameterDistance(
                    'BUFFERDIST',
                    self.tr('BUFFERDIST'),
                    defaultValue = 1.0,
            # ထည့်သွင်းအသုံးပြုသော layer ယူနစ်များနှင့် ကိုက်ညီသော အကွာအဝေးယူနစ်များကို ဖန်တီးပါ-
                    parentParameterName='INPUT'
                )
            )
            self.addParameter(
                QgsProcessingParameterDistance(
                    'CELLSIZE',
                    self.tr('CELLSIZE'),
                    defaultValue = 10.0,
                    parentParameterName='INPUT'
                )
            )
            self.addOutput(
                QgsProcessingOutputNumber(
                    'NUMBEROFFEATURES',
                    self.tr('Number of features processed')
                )
            )

        def processAlgorithm(self, parameters, context, feedback):
            """
            Processing လုပ်ဆောင်သော နေရာဖြစ်ပါသည်။
            """
            # ပထမဆုံးအနေဖြင့် ထည့်သွင်းအသုံးပြုသော layer မှ feature အရေအတွက်ကို ရယူပါ။
            # self.parameterAsSource ကိုခေါ်ယူခြင်းဖြင့် ၎င်းကို ပြန်လည်ရယူနိုင်ရန် ဤ layer ကို 
            # QgsProcessingParameterFeatureSource parameter အဖြစ်သတ်မှတ်ပါ။
            input_featuresource = self.parameterAsSource(parameters,
                                                         'INPUT',
                                                         context)
            numfeatures = input_featuresource.featureCount()

            # Buffer အကွာအဝေးနှင့် raster cell အရွယ်အစား ကိန်းဂဏန်းတန်ဖိုးများကို ရယူပါသည်။
            # ၎င်းတို့သည် ကိန်းဂဏန်းတန်ဖိုးများ ဖြစ်သောကြောင့် self.parameterAsDouble အသုံးပြုပြီး ၎င်းတို့ကို ပြန်လည်ရယူပါသည်။
            bufferdist = self.parameterAsDouble(parameters, 'BUFFERDIST',
                                                context)
            rastercellsize = self.parameterAsDouble(parameters, 'CELLSIZE',
                                                    context)
            if feedback.isCanceled():
                return {}
            buffer_result = processing.run(
                'native:buffer',
                {
            # ဤတွင် INPUT နှင့် BUFFER_OUTPUT များ၏မူရင်း parameter တန်ဖိုးများကို Buffer algorithm သို့ပို့ဆောင်ပေးပါသည်။
                    'INPUT': parameters['INPUT'],
                    'OUTPUT': parameters['BUFFER_OUTPUT'],
                    'DISTANCE': bufferdist,
                    'SEGMENTS': 10,
                    'DISSOLVE': True,
                    'END_CAP_STYLE': 0,
                    'JOIN_STYLE': 0,
                    'MITER_LIMIT': 10
                },
            # Buffer algorithm ကို ပိုကြီးသော အခြား algorithm ထဲတွင် အဆင့်တစ်ခုအဖြစ် လုပ်ဆောင်သောကြောင့်
                # is_child_algorithm option ကို True အဖြစ်သတ်မှတ်သင့်ပါသည်
                is_child_algorithm=True,
                #
            # အသုံးပြုသူများသို့ သင့်တော်သောတုန့်ပြန်မှုပေးရန်နှင့် ပယ်ဖျက်ခြင်းတောင်းဆိုမှုများကို ကိုင်တွယ်နိုင်ရန်အတွက်
            # အခြေအနေနှင့် တုန့်ပြန်သော object များကို child algorithm များသို့ပို့ဆောင်ပေးရန် အရေးကြီးပါသည်။
                context=context,
                feedback=feedback)

            # ပယ်ဖျက်မှုအတွက် စစ်ဆေးခြင်း
            if feedback.isCanceled():
                return {}

            # Buffer မှ ရလာသော ရလာဒ်ကို ထည့်သွင်းအသုံးပြုသော အချက်အလက်အဖြစ် အသုံးပြုပြီး 
            # သီးခြား raster ဖန်တီးခြင်း algorithm ကို လုပ်ဆောင်ပါ။
            rasterized_result = processing.run(
                'qgis:rasterize',
                {
				    # Buffer ၏ရလာဒ် dictionary မှ 'OUTPUT' တန်ဖိုးကို raster ဖန်တီးပေးသော child algorithm သို့ ပို့ဆောင်ပေးပါသည်။
                    'LAYER': buffer_result['OUTPUT'],
                    'EXTENT': buffer_result['OUTPUT'],
                    'MAP_UNITS_PER_PIXEL': rastercellsize,
            # မူရင်း parameter တန်ဖိုးကိုအသုံးပြုပါ။
                    'OUTPUT': parameters['OUTPUT']
                },
                is_child_algorithm=True,
                context=context,
                feedback=feedback)

            if feedback.isCanceled():
                return {}

            # ရလာဒ်များကို ပြန်ထုတ်ပေးပါသည်။
            return {'OUTPUT': rasterized_result['OUTPUT'],
                    'BUFFER_OUTPUT': buffer_result['OUTPUT'],
                    'NUMBEROFFEATURES': numfeatures}

Processing algorithm ၏ စံလုပ်ဆောင်ချက်များ - 

* createInstance (မဖြစ်မနေလုပ်ဆောင်ရမည်)
    Algorithm ၏ မိတ္တူအသစ်တစ်ခုကို ပြန်ထုတ်ပေးရပါမည်။ အမျိုးအစား၏ နာမည်ကိုပြောင်းလိုက်လျှင် ကိုက်ညီစေရန်အတွက် ပြန်ထုတ်ပေးသည့် တန်ဖိုးကိုလည်း အသစ်ပြောင်းလဲပေးပါ။

* name (မဖြစ်မနေလုပ်ဆောင်ရမည်)
    တမူထူးခြားသော algorithm နာမည်ကို ပြန်ထုတ်ပေးပါသည်။ Algorithm ကို သဏ္ဍာန်ခွဲဖော်ပြခြင်းအတွက် အသုံးပြုပါသည်။

* displayName (မဖြစ်မနေလုပ်ဆောင်ရမည်)
    ဘာသာပြန်ထားသော algorithm အမည်ကို ပြန်ထုတ်ပေးပါသည်။

* group
    ၎င်း algorithm နှင့်သက်ဆိုင်သော အုပ်စု၏နာမည်ကို ပြန်ထုတ်ပေးပါသည်။

* groupId
    ၎င်း algorithm နှင့်သက်ဆိုင်သော အုပ်စု၏ တမူထူးခြားသော ID ကို ပြန်ထုတ်ပေးပါသည်။
	
* shortHelpString
    Algorithm အတွက် အကူအညီစာသားအတိုကို ပြန်ထုတ်ပေးပါသည်။
	
* initAlgorithm (မဖြစ်မနေလုပ်ဆောင်ရမည်)
    Algorithm ၏ ထည့်သွင်းအသုံးပြုသော အချက်အလက်များနှင့် ထွက်လာသောရလာဒ် များကို ဤတွင်သတ်မှတ်ပါသည်။

	``INPUT`` နှင့် ``OUTPUT`` သည် အဓိက ထည့်သွင်းအသုံးပြုသော အချက်အလက်နှင့် အဓိကထွက်လာမည့် ရလာဒ် parameter များအတွက် အကြံပြုထားသော အမည်များ ဖြစ်ပါသည်။

	Parameter တစ်ခုသည် အခြား parameter ပေါ်တွင် မှီခိုနေလျှင် ၎င်းချိတ်ဆက်မှုကို သတ်မှတ်ဖော်ပြန်ရန် ``parentParameterName`` ကိုအသုံးပြုပါသည် (Layer တစ်ခု၏ field/band သို့မဟုတ် layer တစ်ခု၏ အကွာအဝေးယူနစ်များ ဖြစ်နိုင်ပါသည်)။

* processAlgorithm (မဖြစ်မနေလုပ်ဆောင်ရမည်)
	Processing လုပ်ဆောင်သော နေရာဖြစ်ပါသည်။

	အထူးရည်ရွယ်ချက် function များကိုအသုံးပြုပြီး parameter ကိုပြန်လည်ရယူပါသည်၊ ဥပမာ- ``parameterAsSource`` နှင့် ``parameterAsDouble``။

	Processing algrithm တွင် အခြား processing algorithm များကိုလုပ်ဆောင်ရန် ``processing.run`` ကိုအသုံးပြုနိုင်ပါသည်။ ပထမထည့်သွင်းရမည့် parameter မှာ algorithm ၏အမည်ဖြစ်ပြီး ဒုတိယထည့်သွင်းရမည်မှာ algorithm အတွက် parameter များ၏ dictionary ဖြစ်ပါသည်။ အခြား algorithm အတွင်းမှ algorithm တစ်ခုကိုလုပ်ဆောင်သောအခါ ``is_child_algorithm`` ကို သာမန်အားဖြင့် ``True`` အဖြစ်သတ်မှတ်ပါသည်။ ``context`` နှင့် ``feedback`` တို့သည် အလုပ်လုပ်ဆောင်မည့် environment အကြောင်းနှင့် အသုံးပြုသူနှင့် ဆက်သွယ်သော channel တို့ကို algorithm သို့အကြောင်းကြားပေးပါသည် (ပယ်ဖျက်သောတောင်းဆိုမှုကို သိမ်းပေးထားခြင်း၊ ပြီးစီးမှုပမာဏကို ကို တင်ပြခြင်း၊ အခြေအနေပေါ်မူတည်သော တုန့်ပြန်မှုများကို ဖော်ပြခြင်း)။ Parent algorithm ၏ parameter များကို "child" algorithms ၏ parameter များအဖြစ် အသုံးပြုသောအခါ မူရင်း parameter တန်ဖိုးများကို အသုံးပြုသင့်ပါသည် (ဥပမာ- ``parameters['OUTPUT']``)

	ဖြစ်နိုင်လျှင် နေရာအတော်များများတွင် ပယ်ဖျက်ခြင်းအတွက် တုန့်ပြန်မှု (feedback) ကို စစ်ဆေးခြင်းသည် ကောင်းမွန်သောအကျင့် ဖြစ်ပါသည်။ ထိုသို့လုပ်ဆောင်ခြင်းဖြင့် မလိုချင်သော processing လုပ်ဆောင်ခြင်းများကို စောင့်နေခိုင်းမည့်အစား တုံ့ပြန်နိုင်သော ပယ်ဖျက်မှုကို ခွင့်ပြုပေးနိုင်ပါသည်။

    Algorithm သည် dictionary တစ်ခုအဖြစ် သတ်မှတ်သော ရလာဒ် parameter များအားလုံးအတွက် တန်ဖိုးများကို ပြန်ထုတ်ပေးသင့်ပါသည်။ ယခုကိစ္စတွင် ၎င်းသည် buffer နှင့် raster အဖြစ်ထွက်လာသော layer များ၊ နှင့် process လုပ်ထားသော feature များ၏အရေအတွက် ဖြစ်ပါသည်။ Dictionary key များသည် မူလ parameter/ရလာဒ် အမည်များနှင့် ကိုက်ညီနေရမည်ဖြစ်သည်။
	
.. _scripts_alg:

The @alg decorator
-------------------

@alg decorator ကိုအသုံးပြုခြင်းဖြင့် Python code များရေးခြင်း နှင့် သင့်တော်သော processing algorithm တစ်ခုဖန်တီးရန်အတွက် အခြားလိုအပ်သော သတင်းအချက်အလက်များကို ပံ့ပိုးရန်အတွက် စာကြောင်းအပိုများ ထပ်ဖြည့်ခြင်း အားဖြင့် ကိုယ်ပိုင် algorithm များကိုဖန်တီးနိုင်ပါသည်။ ၎င်းသည် algorithm များဖန်တီးခြင်းနှင့် ထည့်သွင်းအသုံးပြုသောအချက်အလက်များနှင့် ထွက်လာသောရလာဒ်များ၏သတ်မှတ်ချက်များကို လွယ်ကူရှင်းလင်းစေပါသည်။

Decorator ကိုအသုံးပြုခြင်း၏ အဓိက အားနည်းချက်တစ်ခုမှာ ဤနည်းဖြင့်ဖန်တီးထားသော algorithm များကို အသုံးပြုသူ၏ Proessing Scripts provider သို့ အမြဲတမ်းထည့်ပေါင်းပေးမည်ဖြစ်ပါသည်။ စိတ်ကြိုက်ရွေးထားသော provider သို့ ၎င်း algorithm များကိုထည့်ပေါင်း၍မရနိုင်ပါ။ ဥပမာ- plugin များတွင် အသုံးပြုရန်။

အောက်ပါ code များသည် @alg decorator ကိုအသုံးပြုပြီး အောက်ပါတို့ကိုလုပ်ဆောင်ပါသည်-

#. Vector layer ကို ထည့်သွင်းအသုံးပြုမည့်အချက်အလက်အဖြစ် အသုံးပြုပါသည်။
#. Feature များ၏အရေအတွက်ကို ရေတွက်ပါသည်။
#. Buffer လုပ်ဆောင်မှုတစ်ခုကို ပြုလုပ်ပါသည်။
#. လုပ်ဆောင်ထားသော buffer ၏ရလာဒ်မှ raster layer တစ်ခုဖန်တီးပါသည်။
#. Buffer layer ၊ raster layer နှင့် feature အရေအတွက်တို့ကို ပြန်ထုတ်ပေးပါသည်။

.. testcode::

    from qgis import processing
    from qgis.processing import alg
    from qgis.core import QgsProject

    @alg(name='bufferrasteralg', label='Buffer and export to raster (alg)',
         group='examplescripts', group_label='Example scripts')
    # 'INPUT' သည် အဓိကထည့်သွင်းလုပ်ဆောင်သော parameter အတွက် အကြုံပြုထားသော အမည် ဖြစ်ပါသည်။
    @alg.input(type=alg.SOURCE, name='INPUT', label='Input vector layer')
    # 'OUTPUT' is the recommended name for the main output parameter
    # 'OUTPUT' သည် အဓိကရလာဒ် parameter အတွက် အကြုံပြုထားသော အမည်ဖြစ်ပါသည်။
    @alg.input(type=alg.RASTER_LAYER_DEST, name='OUTPUT',
               label='Raster output')
    @alg.input(type=alg.VECTOR_LAYER_DEST, name='BUFFER_OUTPUT',
               label='Buffer output')
    @alg.input(type=alg.DISTANCE, name='BUFFERDIST', label='BUFFER DISTANCE',
               default=1.0)
    @alg.input(type=alg.DISTANCE, name='CELLSIZE', label='RASTER CELL SIZE',
               default=10.0)
    @alg.output(type=alg.NUMBER, name='NUMBEROFFEATURES',
                label='Number of features processed')

    def bufferrasteralg(instance, parameters, context, feedback, inputs):
        """
        Algorithm ၏ရှင်းလင်းဖော်ပြချက်။
        (ဒီနေရာတွင် comment မရှိလျှင် အမှားတစ်ခုရရှိပါလိမ့်မည်)
        """
        input_featuresource = instance.parameterAsSource(parameters,
                                                         'INPUT', context)
        numfeatures = input_featuresource.featureCount()
        bufferdist = instance.parameterAsDouble(parameters, 'BUFFERDIST',
                                                context)
        rastercellsize = instance.parameterAsDouble(parameters, 'CELLSIZE',
                                                    context)
        if feedback.isCanceled():
            return {}
        buffer_result = processing.run('native:buffer',
                                   {'INPUT': parameters['INPUT'],
                                    'OUTPUT': parameters['BUFFER_OUTPUT'],
                                    'DISTANCE': bufferdist,
                                    'SEGMENTS': 10,
                                    'DISSOLVE': True,
                                    'END_CAP_STYLE': 0,
                                    'JOIN_STYLE': 0,
                                    'MITER_LIMIT': 10
                                    },
                                   is_child_algorithm=True,
                                   context=context,
                                   feedback=feedback)
        if feedback.isCanceled():
            return {}
        rasterized_result = processing.run('qgis:rasterize',
                                   {'LAYER': buffer_result['OUTPUT'],
                                    'EXTENT': buffer_result['OUTPUT'],
                                    'MAP_UNITS_PER_PIXEL': rastercellsize,
                                    'OUTPUT': parameters['OUTPUT']
                                   },
                                   is_child_algorithm=True, context=context,
                                   feedback=feedback)
        if feedback.isCanceled():
            return {}
        return {'OUTPUT': rasterized_result['OUTPUT'],
                'BUFFER_OUTPUT': buffer_result['OUTPUT'],
                'NUMBEROFFEATURES': numfeatures}

တွေ့ရသည့်အတိုင်း algorithm နှစ်မျိုးပါဝင်ပါသည် ('native:buffer' နှင့် 'qgis:rasterize')။ နောက်ဆုံးတစ်ခုသည် ('qgis:rasterize') ပထမဆုံးတစ်ခု ('native:buffer') ဖြင့် ဖန်တီးခဲ့သော buffer layer မှ raster layer တစ်ခုကို ဖန်တီးပေးပါသည်။

ရှေ့ကသင်ခန်းစာများကိုဖတ်ခဲ့လျှင် ဤ processing လုပ်ဆောင်သော code များကိုနားလည်ရန် ခက်ခဲမည်မဟုတ်ပါ။ သို့သော် အစပိုင်းစာကြောင်းများသည် အချို့သောရှင်းလင်းချက်များ လိုအပ်ပါသည်။ Toolbox သို့မဟုတ် model designer ကဲ့သို့သော မည်သည့် GUI အစိတ်အပိုင်းဖြင့်မဆို လုပ်ဆောင်နိုင်သော algorithm အဖြစ် code ကိုပြောင်းလဲရန် လိုအပ်သော အချက်အလက်များကို ၎င်းတို့က ထောက်ပံ့ပေးပါသည်။

ထိုစာကြောင်းများအားလုံးကို algorithm ၏ coding ကိုလွယ်ကူရှင်းလင်းအောင် ကူညီပေးသော ``@alg`` decorator function များသို့ ခေါ်ယူပေးပါသည်။

* Toolbox ထဲရှိ algorithm ၏အမည်နှင့် တည်နေရာကိုသတ်မှတ်ရန် @alg decorator ကိုအသုံးပြုပါသည်။
* Algorithm ၏ထည့်သွင်းအသုံးပြုသော အချက်အလက်များကို သတ်မှတ်ရန် @alg.input decorator ကိုအသုံးပြုပါသည်။
* Algorithm ၏ ရလာဒ်များကို သတ်မှတ်ရန် @alg.output decorator ကိုအသုံးပြုပါသည်။

.. _processing_algs_input_output:

Input and output types for Processing Algorithms (Processing Algorithm များအတွက် Input နှင့် Output အမျိုးအစားများ)
--------------------------------------------------------------------------------------------------------------------

သက်ဆိုင်သော alg decorator မပြောင်းလဲမှုများနှင့် processing ထဲတွင် လုပ်ဆောင်ပေးသော Input နှင့် Output အမျိုးအစားများစာရင်းကို အောက်တွင် ဖော်ပြထားပါသည်။ (:source:`algfactory.py <python/processing/algfactory.py>` file တွင် ပြီးပြည့်စုံသော alg constants စာရင်းပါဝင်ပါသည်။) Class အမည်ဖြင့် စီထားပါသည်။

Input types (ထည့်သွင်းအသုံးပြုမည့်အချက်အလက် အမျိုးအစားများ)
............................................................

.. list-table::
   :widths: 45 31 24
   :header-rows: 1
   :class: longtable

   * - Class
     - Alg constant
     - ရှင်းလင်းဖော်ပြချက်
   * - :class:`QgsProcessingParameterAnnotationLayer <qgis.core.QgsProcessingParameterAnnotationLayer>`
     - ``alg.ANNOTATION_LAYER``
     - Annotation (မှတ်ချက်) layer တစ်ခု
   * - :class:`QgsProcessingParameterAuthConfig <qgis.core.QgsProcessingParameterAuthConfig>`
     - ``alg.AUTH_CFG``
     - အသုံးပြုနိုင်သော authentication ပြင်ဆင်မှုများထဲမှ ရွေးချယ်နိုင်ခြင်း သို့မဟုတ် authentication ပြင်ဆင်မှုအသစ်များ ဖန်တီးနိုင်စေခြင်း
   * - :class:`QgsProcessingParameterBand <qgis.core.QgsProcessingParameterBand>`
     - ``alg.BAND``
     - Raster layer band တစ်ခု
   * - :class:`QgsProcessingParameterBoolean <qgis.core.QgsProcessingParameterBoolean>`
     - ``alg.BOOL``
     - မှား/မှန် တန်ဖိုး
   * - :class:`QgsProcessingParameterColor <qgis.core.QgsProcessingParameterColor>`
     - ``alg.COLOR``
     - အရောင်တစ်မျိုး
   * - :class:`QgsProcessingParameterCoordinateOperation <qgis.core.QgsProcessingParameterCoordinateOperation>`
     - ``alg.COORDINATE_OPERATION``
     - ကိုဩဒိနိတ်လုပ်ဆောင်မှုတစ်ခု (CRS ပြောင်းလဲခြင်းအတွက်)
   * - :class:`QgsProcessingParameterCrs <qgis.core.QgsProcessingParameterCrs>`
     - ``alg.CRS``
     - Coordinate Reference System (ကိုဩဒိနိတ်အညွှန်းစနစ်တစ်ခု)
   * - :class:`QgsProcessingParameterDatabaseSchema <qgis.core.QgsProcessingParameterDatabaseSchema>`
     - ``alg.DATABASE_SCHEMA``
     - Database ပုံစံတစ်ခု
   * - :class:`QgsProcessingParameterDatabaseTable <qgis.core.QgsProcessingParameterDatabaseTable>`
     - ``alg.DATABASE_TABLE``
     - Database ဇယားတစ်ခု
   * - :class:`QgsProcessingParameterDateTime <qgis.core.QgsProcessingParameterDateTime>`
     - ``alg.DATETIME``
     - ရက်စွဲအချိန်တစ်ခု (ရက်စွဲချည်းပဲ သို့မဟုတ် အချိန်)
   * - :class:`QgsProcessingParameterDistance <qgis.core.QgsProcessingParameterDistance>`
     - ``alg.DISTANCE``
     - အကွာအဝေးတန်ဖိုးများအဝွက် ဒဿမကိန်းဂဏန်း parameter
   * - :class:`QgsProcessingParameterEnum <qgis.core.QgsProcessingParameterEnum>`
     - ``alg.ENUM``
     - ကြိုတင်သတ်မှတ်ထားသောတန်ဖိုးများအစုမှ ရွေးချယ်နိုင်သော enumeration (ရေတွက်မှု) တစ်ခု
   * - :class:`QgsProcessingParameterExpression <qgis.core.QgsProcessingParameterExpression>`
     - ``alg.EXPRESSION``
     - Expression တစ်ခု
   * - :class:`QgsProcessingParameterExtent <qgis.core.QgsProcessingParameterExtent>`
     - ``alg.EXTENT``
     - အနည်းဆုံး x တန်ဖိုး၊ အများဆုံး x တန်ဖိုး၊ အနည်းဆုံး y တန်ဖိုး၊ အများဆုံး y တန်ဖိုး တို့ဖြင့်သတ်မှတ်ထားသော မြေပြင်အကျယ်အဝန်း
   * - :class:`QgsProcessingParameterField <qgis.core.QgsProcessingParameterField>`
     - ``alg.FIELD``
     - Vector layer တစ်ခု၏ attribute ဇယားထဲရှိ field တစ်ခု
   * - :class:`QgsProcessingParameterFile <qgis.core.QgsProcessingParameterFile>`
     - ``alg.FILE``
     - ရှိနေပြီးသား file တစ်ခု၏ file အမည်တစ်ခု
   * - :class:`QgsProcessingParameterFileDestination <qgis.core.QgsProcessingParameterFileDestination>`
     - ``alg.FILE_DEST``
     - အသစ်ဖန်တီးထားသော ရလာဒ် file ၏ file နာမည်တစ်ခု
   * - :class:`QgsProcessingParameterFolderDestination <qgis.core.QgsProcessingParameterFolderDestination>`
     - ``alg.FOLDER_DEST``
     - Folder တစ်ခု (သိမ်းဆည်းမည့် folder)
   * - :class:`QgsProcessingParameterGeometry <qgis.core.QgsProcessingParameterGeometry>`
     - ``alg.GEOMETRY``
     - ဂျီဩမေတြီ တစ်ခု
   * - :class:`QgsProcessingParameterNumber <qgis.core.QgsProcessingParameterNumber>`
     - ``alg.INT``
     - ကိန်းပြည့်တစ်ခု
   * - :class:`QgsProcessingParameterLayout <qgis.core.QgsProcessingParameterLayout>`
     - ``alg.LAYOUT``
     - Layout တစ်ခု
   * - :class:`QgsProcessingParameterLayoutItem <qgis.core.QgsProcessingParameterLayoutItem>`
     - ``alg.LAYOUT_ITEM``
     - Layout item တစ်ခု
   * - :class:`QgsProcessingParameterMapLayer <qgis.core.QgsProcessingParameterMapLayer>`
     - ``alg.MAPLAYER``
     - မြေပုံ layer တစ်ခု
   * - :class:`QgsProcessingParameterMapTheme <qgis.core.QgsProcessingParameterMapTheme>`
     - ``alg.MAP_THEME``
     - Project မြေပုံ ကဏ္ဍတစ်ခု
   * - :class:`QgsProcessingParameterMatrix <qgis.core.QgsProcessingParameterMatrix>`
     - ``alg.MATRIX``
     - Matrix တစ်ခု
   * - :class:`QgsProcessingParameterMeshLayer <qgis.core.QgsProcessingParameterMeshLayer>`
     - ``alg.MESH_LAYER``
     - Mesh layer တစ်ခု
   * - :class:`QgsProcessingParameterMultipleLayers <qgis.core.QgsProcessingParameterMultipleLayers>`
     - ``alg.MULTILAYER``
     - Layer အစုတစ်ခု
   * - :class:`QgsProcessingParameterNumber <qgis.core.QgsProcessingParameterNumber>`
     - ``alg.NUMBER``
     - ဂဏန်းတန်ဖိုးတစ်ခု
   * - :class:`QgsProcessingParameterPoint <qgis.core.QgsProcessingParameterPoint>`
     - ``alg.POINT``
     - အမှတ်တစ်ခု
   * - :class:`QgsProcessingParameterPointCloudDestination <qgis.core.QgsProcessingParameterPointCloudDestination>`
     - ``alg.POINTCLOUD_LAYER_DEST``
     - Point cloud layer အတွက် နေရာ parameter ၊ algorithm ဖြင့်ဖန်တီးထားသော point cloud layer တစ်ခုအတွက် တည်နေရာလမ်းကြောင်း ကိုသတ်မှတ်ခြင်းအတွက်။
   * - :class:`QgsProcessingParameterPointCloudLayer <qgis.core.QgsProcessingParameterPointCloudLayer>`
     - ``alg.POINTCLOUD_LAYER``
     - Point cloud layer တစ်ခု
   * - :class:`QgsProcessingParameterProviderConnection <qgis.core.QgsProcessingParameterProviderConnection>`
     - ``alg.PROVIDER_CONNECTION``
     - Database provider တစ်ခုအတွက် အသုံးပြုနိုင်သော ချိတ်ဆက်မှုတစ်ခု
   * - :class:`QgsProcessingParameterRange <qgis.core.QgsProcessingParameterRange>`
     - ``alg.RANGE``
     - ကိန်းဂဏန်းအပိုင်းအခြားတစ်ခု
   * - :class:`QgsProcessingParameterRasterLayer <qgis.core.QgsProcessingParameterRasterLayer>`
     - ``alg.RASTER_LAYER``
     - Raster layer တစ်ခု
   * - :class:`QgsProcessingParameterRasterDestination <qgis.core.QgsProcessingParameterRasterDestination>`
     - ``alg.RASTER_LAYER_DEST``
     - Raster layer တစ်ခုအတွက် နေရာ parameter ၊ algorithm ဖြင့်ဖန်တီးထားသော raster layer တစ်ခုအတွက် တည်နေရာလမ်းကြောင်း ကိုသတ်မှတ်ခြင်းအတွက်။
   * - :class:`QgsProcessingParameterScale <qgis.core.QgsProcessingParameterScale>`
     - ``alg.SCALE``
     - မြေပုံ စကေးတစ်ခု
   * - :class:`QgsProcessingParameterFeatureSink <qgis.core.QgsProcessingParameterFeatureSink>`
     - ``alg.SINK``
     - Feature sink တစ်ခု
   * - :class:`QgsProcessingParameterFeatureSource <qgis.core.QgsProcessingParameterFeatureSource>`
     - ``alg.SOURCE``
     - Feature အရင်းအမြစ် တစ်ခု
   * - :class:`QgsProcessingParameterString <qgis.core.QgsProcessingParameterString>`
     - ``alg.STRING``
     - စာသားတစ်ခု
   * - :class:`QgsProcessingParameterVectorLayer <qgis.core.QgsProcessingParameterVectorLayer>`
     - ``alg.VECTOR_LAYER``
     - Vector layer တစ်ခု
   * - :class:`QgsProcessingParameterVectorDestination <qgis.core.QgsProcessingParameterVectorDestination>`
     - ``alg.VECTOR_LAYER_DEST``
     - Vector layer တစ်ခုအတွက် နေရာ parameter ၊ algorithm ဖြင့်ဖန်တီးထားသော vector layer တစ်ခုအတွက် တည်နေရာလမ်းကြောင်း ကိုသတ်မှတ်ခြင်းအတွက်။
   * - :class:`QgsProcessingParameterVectorTileDestination <qgis.core.QgsProcessingParameterVectorTileDestination>`
     -
     - Vector tile layer တစ်ခုအတွက် နေရာ parameter ၊ algorithm ဖြင့်ဖန်တီးထားသော vector tile layer တစ်ခုအတွက် တည်နေရာလမ်းကြောင်း ကိုသတ်မှတ်ခြင်းအတွက်။


Output types (ရလာဒ်အမျိုးအစားများ)
...................................

.. list-table::
   :widths: 47 24 29
   :header-rows: 1
   :class: longtable

   * - Class
     - Alg constant
     - ရှင်းလင်းဖော်ပြချက်
   * - :class:`QgsProcessingOutputBoolean <qgis.core.QgsProcessingOutputBoolean>`
     - ``alg.BOOL``
     - အမှား/အမှန် တန်ဖိုးတစ်ခု
   * - :class:`QgsProcessingOutputNumber <qgis.core.QgsProcessingOutputNumber>`
     - ``alg.DISTANCE``
     - အကွာအဝေးတန်ဖိုးများအတွက် ဒဿမကိန်းဂဏန်း parameter တစ်ခု
   * - :class:`QgsProcessingOutputFile <qgis.core.QgsProcessingOutputFile>`
     - ``alg.FILE``
     - ရှိနေပြီးသား file တစ်ခု၏ file နာမည်တစ်ခု
   * - :class:`QgsProcessingOutputFolder <qgis.core.QgsProcessingOutputFolder>`
     - ``alg.FOLDER``
     - Folder တစ်ခု
   * - :class:`QgsProcessingOutputHtml <qgis.core.QgsProcessingOutputHtml>`
     - ``alg.HTML``
     - HTML
   * - :class:`QgsProcessingOutputNumber <qgis.core.QgsProcessingOutputNumber>`
     - ``alg.INT``
     - ကိန်းပြည့်တစ်ခု
   * - :class:`QgsProcessingOutputLayerDefinition <qgis.core.QgsProcessingOutputLayerDefinition>`
     - ``alg.LAYERDEF``
     - Layer အဓိပ္ပါယ်ဖွင့်ဆိုချက်တစ်ခု
   * - :class:`QgsProcessingOutputMapLayer <qgis.core.QgsProcessingOutputMapLayer>`
     - ``alg.MAPLAYER``
     - မြေပုံ layer တစ်ခု
   * - :class:`QgsProcessingOutputMultipleLayers <qgis.core.QgsProcessingOutputMultipleLayers>`
     - ``alg.MULTILAYER``
     - Layer အစုတစ်ခု
   * - :class:`QgsProcessingOutputNumber <qgis.core.QgsProcessingOutputNumber>`
     - ``alg.NUMBER``
     - ကိန်းဂဏန်းတန်ဖိုး တစ်ခု
   * - :class:`QgsProcessingOutputPointCloudLayer <qgis.core.QgsProcessingOutputPointCloudLayer>`
     - ``alg.POINTCLOUD_LAYER``
     - Point cloud layer တစ်ခု
   * - :class:`QgsProcessingOutputRasterLayer <qgis.core.QgsProcessingOutputRasterLayer>`
     - ``alg.RASTER_LAYER``
     - Raster layer တစ်ခု
   * - :class:`QgsProcessingOutputString <qgis.core.QgsProcessingOutputString>`
     - ``alg.STRING``
     - စာသားတစ်ခု
   * - :class:`QgsProcessingOutputVectorLayer <qgis.core.QgsProcessingOutputVectorLayer>`
     - ``alg.VECTOR_LAYER``
     - Vector layer တစ်ခု
   * - :class:`QgsProcessingOutputVectorTileLayer <qgis.core.QgsProcessingOutputVectorTileLayer>`
     -
     - Vector tile layer တစ်ခု


Handing algorithm output (Algorithm ရလာဒ်များကို လက်ဆင့်ကမ်းခြင်း)
-------------------------------------------------------------------

Layer တစ်ခု (raster သို့မဟုတ် vector) ကိုကိုယ်စားပြုသော ရလာဒ်တစ်ခုကို ကြေညာသောအခါ လုပ်ဆောင်မှုပြီးစီးသည်နှင့် algorithm က ၎င်းကို QGIS ထဲကိုပေါင်းထည့်ပါလိမ့်မည်။

* Raster layer ရလာဒ် - QgsProcessingParameterRasterDestination /
  alg.RASTER_LAYER_DEST.
* Vector layer ရလာဒ် - QgsProcessingParameterVectorDestination /
  alg.VECTOR_LAYER_DEST.

``processing.run()`` နည်းလမ်းသည် ၎င်းဖန်တီးထားသော layer များကို အသုံးပြုသူ၏ လက်ရှိ project သို့ထည့်မပေါင်းလျှင်တောင်မှ အသုံးပြုသူမှထည့်သွင်းထားသည့် တည်နေရာတွင်သိမ်းဆည်းသောကြောင့် (သို့မဟုတ် အသုံးပြုသူမှ တည်နေရာကိုမသတ်မှတ်ထားလျှင် ယာယီတည်နေရာတွင်) ထွက်လာမည့် layer နှစ်ခု (buffer နှင့် raster buffer) ကို ခေါ်ယူထည့်သွင်းပါလိမ့်မည်။

Layer တစ်ခုကို algorithm တစ်ခု၏ ရလာဒ်အဖြစ် ဖန်တီးလျှင် ၎င်းကို ဖန်တီးခဲ့သောနည်းလမ်းအတိုင်း‌ ကြေညာရပါမည်။ ထိုသို့မလုပ်လျှင် ကြေညာထားမှုသည် တကယ်ဖန်တီးခဲ့မှုနှင့် မကိုက်ညီသောကြောင့် modeler ထဲတွင် algorithm ကိုမှန်မှန်ကန်ကန် အသုံးပြုလို့ရနိုင်မည် မဟုတ်ပါ။

ရလာဒ် dictionary ထဲတွင် စာသားများ၊ ဂဏန်းများ နှင့်အခြားအရာများကို သတ်မှတ်ပေးခြင်းဖြင့် ၎င်းတို့ကို ပြန်လည်ထုတ်ပေးနိုင်ပါသည် ("NUMBEROFFEATURES" အတွက်သရုပ်ဖော်ထားသကဲ့သို့)၊ သို့သော် ၎င်းတို့ကို algorithm မှထွက်လာသောရလာဒ်များအဖြစ် အတိအလင်းသတ်မှတ်သင့်ပါသည်။ Algorithm ကို model ၏အစိတ်အပိုင်းတစ်ခုအဖြစ် အသုံးပြုသောအခါ နောက်ပိုင်းတွင်အသုံးပြုမည့် algorithm များအတွက်အသုံးဝင်သောကြောင့် algorithm များမှ အသုံးဝင်သောရလာဒ်တန်ဖိုးများကို ရနိုင်သမျှ ထုတ်ပေးရန် အကြံပြုပါသည်။


Communicating with the user (အသုံးပြုသူများနှင့် ဆက်သွယ်ခြင်း)
---------------------------------------------------------------

Algorithm သည်လုပ်ဆောင်သောအချိန်ကြာမြင့်မည်ဆိုလျှင် ပြီးစီးနေမှုပမာဏကို ဖော်ပြသင့်ပါသည်။ ထိုသို့ဖော်ပြရန် ``feedback`` (:class:`QgsProcessingFeedback <qgis.core.QgsProcessingFeedback>`) ကိုအသုံးပြုနိုင်ပါသည်။

:meth:`setProgressText(text) <qgis.core.QgsProcessingFeedback.setProgressText>` နှင့် :meth:`setProgress(percent) <qgis.core.QgsFeedback.setProgress>` များကိုအသုံးပြုပြီး ပြီးစီးမှုစာသားနှင့် ပြီးစီးမှုပြ bar တို့၏ နောက်ဆုံးရအခြေအနေကို update ပြုလုပ်နိုင်ပါသည်။

:meth:`pushCommandInfo(text) <qgis.core.QgsProcessingFeedback.pushCommandInfo>`၊ :meth:`pushDebugInfo(text) <qgis.core.QgsProcessingFeedback.pushDebugInfo>`၊ :meth:`pushInfo(text) <qgis.core.QgsProcessingFeedback.pushInfo>` နှင့်
:meth:`reportError(text) <qgis.core.QgsProcessingFeedback.reportError>` များကိုအသုံးပြုပြီး အခြားအချက်အလက်များကိုလည်း ဖော်ပြနိုင်ပါသည်။

Script တွင်ပြဿနာတစ်ခုခုရှိနေလျှင် မှန်ကန်သော ပြင်ဆင်နည်းမှာ :class:`QgsProcessingException <qgis.core.QgsProcessingException>` ကိုအသုံးပြုရန်ဖြစ်ပါသည်။ Exception (ချွင်းချက်)၏ constructor (တည်ဆောက်သူ) ဆီသို့ message စာတစ်ခု ပေးပို့နိုင်ပါသည်။ Algorithm ကိုမည်သည့်နေရာမှ လုပ်ဆောင်သည် (toolbox ၊ modeler ၊ Python console ၊ ...) ဆိုတာပေါ်မူတည်ပြီး processing မှ ၎င်းကိုကိုင်တွယ်ဖြေရှင်းပြီး အသုံးပြုသူနှင့် ဆက်သွယ်ပေးပါသည်။


Documenting your scripts (မိမိ၏ Script များကို မှတ်တမ်းပြုစုခြင်း)
-------------------------------------------------------------------

:class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ၏ :meth:`helpString() <qgis.core.QgsProcessingAlgorithm.helpString>` နှင့် :meth:`helpUrl() <qgis.core.QgsProcessingAlgorithm.helpUrl>` နည်းလမ်းများကို ထည့်သွင်းပြီး မိမိ၏ script များကို မှတ်တမ်းပြုစုနိုင်ပါသည်။ 

Flags
------

QGIS ကို မိမိ၏ algorithm အကြောင်းကို ပိုမိုသိစေရန် :class:`QgsProcessingAlgorithm <qgis.core.QgsProcessingAlgorithm>` ၏ :meth:`flags() <qgis.core.QgsProcessingAlgorithm.flags>` နည်းလမ်းကို အစားထိုးရေးသားနိုင်ပါသည်။ ဥပမာ- ပယ်ဖျက်နိုင်သော၊ thread လုံခြုံမှုမရှိသော modeler မှ script ကိုဝှက်ထားနိုင်ကြောင်းကို QGIS ကို သိအောင် လုပ်ပေးနိုင်ပါသည်။

.. tip::
    ပုံမှန်အားဖြင့် processing task ကိုလုပ်ဆောင်နေစဉ်တွင် QGIS ကို တုန့်ပြန်မှုရှိနေစေရန် Processing က algroithm များကို သီးခြား thread တစ်ခုထဲတွင် လုပ်ဆောင်ပါသည်။ မိမိ၏ algorithm က မကြာခဏဆိုသလို ပိတ်ကျနေလျှင် နောက်ကွယ် thread ထဲတွင် လုပ်ဆောင်ရန် လုံခြုံမှုမရှိသော API call များကိုအသုံးပြုနေခြင်း ဖြစ်နိုင်ပါသည်။ Algorithm ကို အဓိက thread ထဲတွင်လုပ်ဆောင်ရန် Processing ကိုတွန်းအားပေးမည့်အစား algorithm ၏ flags() နည်းလမ်းမှ QgsProcessingAlgorithm.FlagNoThreading flag ကို ပြန်ထုတ်ပေးသင့်ပါသည်။

Best practices for writing script algorithms (Script algorithm များရေးသားခြင်းအတွက် အကောင်းဆုံး အလေ့အကျင့်များ)
----------------------------------------------------------------------------------------------------------------

ကိုယ်ပိုင် script algorithm များရေးသားပြီး အခြား QGIS အသုံးပြုသူများကို မျှဝေလိုလျှင် ထည့်သွင်းစဉ်းစားသင့်သည့် အကြံပေးချက်အချို့ကို အောက်မှာ အကျဉ်းချုပ် ဖော်ပြထားပါသည်။ ရိုးရှင်းသော အောက်ပါစည်းမျဉ်းများကိုအသုံးပြုလျှင် toolbox ၊ modeler သို့မဟုတ် batch processing လုပ်သော interface များကဲ့သို့သော အမျိုးမျိုးသော processing element များတွင် တသတ်မတ်တည်းဖြစ်နေစေပါလိမ့်မည်။

* ရလာဒ် layer များကို ခေါ်ယူထည့်သွင်းခြင်း မလုပ်ပါနှင့်။ Processing ကိုသာ ရလာဒ်များကို ကိုင်တွယ်စေပြီး လိုအပ်မှသာ layer များကို ခေါ်ယူထည့်သွင်းပါစေ။
* Algorithm မှဖန်တီးခဲ့သော ရလာဒ်များကို အမြဲတမ်း ကြေညာပါ။
* Messge box များကို မပြသပါနှင့် သို့မဟုတ် script မှ မည်သည့် GUI element ကိုမှအသုံးမပြုပါနှင့်။ အသုံးပြုသူများနှင့် ဆက်သွယ်လိုလျှင် တုန့်ပြန်မှု object (:class:`QgsProcessingFeedback <qgis.core.QgsProcessingFeedback>`) ကိုအသုံးပြုပါ သို့မဟုတ် :class:`QgsProcessingException <qgis.core.QgsProcessingException>` တစ်ခုကို အသုံးပြုပါ။

QGIS ထဲတွင် အသုံးပြုနိုင်သော processing algorithm များစွာရှိပြီးသား ဖြစ်ပါသည်။ :source:`QGIS <python/plugins/processing/algs/qgis>` repo တွင် code များကိုသွားရောက်ရှာဖွေနိုင်ပါသည်။
