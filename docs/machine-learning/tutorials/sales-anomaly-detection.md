---
title: Использование ML.NET в сценарии обнаружения аномалий по продажам
description: Узнайте, как использовать ML.NET в сценарии обнаружения аномалий при продаже продукта, чтобы понять, как анализировать данные на предмет пиковых аномалий и точек изменений для принятия соответствующих мер.
ms.date: 05/29/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d31765aa4ff2a0be9c4f140f33de1f5678fc7612
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423942"
---
# <a name="tutorial-use-mlnet-for-product-sales-anomaly-detection"></a>Учебник. Использование ML.NET для обнаружения аномалий при продаже продукта 

В этом практическом руководстве демонстрируется использование ML.NET для обнаружения аномалий при продаже продукта и принятия соответствующих мер в консольном приложении .NET Core на языке C# с помощью Visual Studio 2019. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> * Загрузка данных
> * Обучение модели для обнаружения пиковых аномалий
> * Обнаружение пиковых аномалий с помощью обученной модели
> * Обучение модели для обнаружения аномалий в точке изменений
> * Обнаружение аномалий в точке изменений с помощью обученной модели

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

* [Набор данных product-sales.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> Формат данных в `product-sales.csv` основан на наборе данных Shampoo Sales Over a Three Year Period, изначально опубликованном DataMarket и предоставленном Time Series Data Library (TSDL), за авторством Роба Нундмана (Rob Hyndman). Набор данных Shampoo Sales Over a Three Year Period предоставляется по стандартной открытой лицензии DataMarket.

## <a name="create-a-console-application"></a>Создание консольного приложения

1. Создайте **консольное приложение .NET Core** с именем ProductSalesAnomalyDetection.

2. Создайте каталог с именем *Data* в проекте, чтобы сохранять файлы набора данных.

3. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакетов, перейдите на вкладку "Обзор", выполните поиск по фразе **Microsoft.ML**, выберите в списке пакет **v1.0.0** и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов. Повторите эти действия для пакета **Microsoft.ML.TimeSeries v0.12.0**.

4. Добавьте следующие операторы `using` в начало файла *Program.cs*:

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Скачивание данных

1. Скачайте набор данных и сохраните его в ранее созданную папку *Data*:

   * Щелкните файл [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) правой кнопкой мыши и выберите команду "Сохранить ссылку (объект) как...".

     Файл \*.csv нужно сохранить в папке *Data*. Если вы сохранили файл \*.csv в другом месте, переместите его в папку *Data*.

2. В обозревателе решений щелкните правой кнопкой мыши файл \*.csv и выберите пункт **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

В следующей таблице представлены данные из вашего файла \*.csv:

|Месяц.  |ProductSales |
|-------|-------------|
|1-Jan  |    271      |
|2-Jan  |    150,9    |
|.....  |    .....    |
|1-Feb  |    199,3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Создание классов и определение путей

Далее определите структуру данных для входного класса.

Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите команду **Добавить > Новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ProductSalesData.cs*. Теперь нажмите кнопку **Добавить**.

Файл *ProductSalesData.cs* откроется в редакторе кода. Добавьте следующую инструкцию `using` в начало файла *ProductSalesData.cs*:

```csharp
using Microsoft.ML.Data;
```

Удалите из файла *ProductSalesData.cs* существующее определение класса и добавьте следующий код с двумя классами `ProductSalesData` и `ProductSalesPrediction`:

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

`ProductSalesData` — это класс входных данных. Атрибут [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) определяет столбцы в наборе данных, которые следует загрузить (по индексам). 

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

Создайте два глобальных поля для хранения пути к недавно скачанному файлу набора данных и файлу сохраненной модели:

* `_dataPath` содержит путь к набору данных, используемому для обучения модели;
* `_docsize` содержит количество записей в файле набора данных. Вы будете использовать эти сведения для вычисления `pvalueHistoryLength`.

Добавьте следующий код в строку прямо перед методом `Main`, чтобы указать эти пути:

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели. По существу он аналогичен классу `DBContext` в Entity Framework.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом, чтобы объявить и инициализировать переменную `mlContext`:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a>Загрузка данных

Данные в ML.NET представлены [классом IDataView](xref:Microsoft.ML.IDataView). `IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые). Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала). Добавьте в следующую строку метода `Main()` приведенный ниже код.

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

Метод [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) определяет схему данных и считывает файл. Он принимает переменные, содержащие пути к данным, и возвращает объект `IDataView`.

## <a name="ml-task---time-series-anomaly-detection"></a>Задача машинного обучения — обнаружение аномалий временных рядов 

Функция обнаружения аномалий регистрирует неожиданные или необычные события или особенности поведения. Кроме того, она подсказывает, где нужно искать проблему, и помогает ответить на вопрос "Является ли это странным?".

![Является ли это странным](./media/sales-anomaly-detection/anomalydetection.png)

Обнаружение аномалий — это процесс обнаружения выбросов временных рядов данных, точек заданных входных временных рядов, где поведение отличается от ожидаемого или является "странным".

Это может оказаться полезным во многих ситуациях. Например:

При наличии автомобиля вы, возможно, захотите узнать, правильны ли показания датчика масла или возникла утечка.
Если вы отслеживаете энергопотребление, то захотите узнать, имеет ли место простой.

Существуют два вида аномалий временных рядов, которые можно обнаружить. 

* **Пиковые значения** указывают временные всплески аномального поведения в системе. 

* **Точки изменений** указывают начало устойчивых изменений с течением времени в системе. 

В ML.NET алгоритмы обнаружения пиковых значений IID или обнаружения точек изменений IID подходят для [независимых и одинаково распределенных наборов данных](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables). 

Вы проанализируете одни и те же данные о продажах продукта для обнаружения пиковых значений и точек изменений. Процесс создания и обучения модели одинаков для обоих видов обнаружения; основное различие заключается в используемом алгоритме обнаружения.

## <a name="spike-detection"></a>Обнаружение пиковых значений 

Целью обнаружения пиковых значений является выявление внезапных, но при этом временных всплесков, которые значительно отличаются от большинства значений данных временных рядов. Важно своевременно обнаружить эти подозрительные редкие элементы, события или наблюдения, чтобы свести их влияние к минимуму. Для обнаружения разнообразных аномалий, таких как простои, кибератаки и вирусное веб-содержимое, можно использовать описанный ниже подход. На следующем рисунке представлен пример пиковых значений в наборе данных временных рядов.

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a>Создание метода DetectSpike()

В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `DetectSpike()`:

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

Метод `DetectSpike()` выполняет следующие задачи:

* обучение модели;
* Обнаруживает пиковые значения на основе исторических данных о продажах.
* Отображает результаты.

Создайте метод `DetectSpike()` сразу после метода `Main()`, вставив в него следующий код:

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

Используйте [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator), чтобы обучить модель для обнаружения пиковых значений. Добавьте его в метод `DetectChangepoint()` со следующим кодом:

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

Обучите модель на основе данных `productSales`, добавив следующую строку кода в метод `DetectSpike()`:

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

Метод [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) обучает модель путем преобразования набора данных и применения обучения.

Добавьте указанный ниже код для преобразования данных `productSales` в следующую строку метода `DetectSpike()`:

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

Предыдущий код использует метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A), чтобы сделать прогнозы для нескольких входных строк тестового набора данных.

Преобразуйте `transformedData` в строго типизированный `IEnumerable` для более удобного отображения с помощью метода [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A), используя следующий код:

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

Создайте отображаемую строку заголовка с помощью следующего кода <xref:System.Console.WriteLine?displayProperty=nameWithType>:

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

В результатах обнаружения пиковых значений будут отображены следующие сведения:

* `Alert` указывает на оповещение о пиковом значении для заданной точки данных.

* `Score` является значением `ProductSales` для заданной точки данных в наборе данных.

* `P-Value` — "P" означает вероятность. Указывает, с какой вероятностью эта точка данных является аномалией. 

Используйте следующий код, чтобы выполнить итерацию по `predictions` `IEnumerable` и отобразить результаты:

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a>Результаты обнаружения пиковых значений

Результаты выполнения должны выглядеть примерно так, как показано ниже. Во время обработки отображаются сообщения. Вы можете видеть предупреждения или обработанные сообщения. Для удобства они удалены из следующих результатов.

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>Обнаружение точек изменений

`Change points` — это постоянные изменения в распределении значений по потоку событий временных рядов, такие как изменения уровня и тенденции. Эти постоянные изменения длятся гораздо дольше, чем `spikes`, и могут указывать на катастрофические события. `Change points` обычно не видны невооруженным глазом, но могут быть обнаружены в данных с помощью таких подходов, которые описаны в следующем методе.  На следующем рисунке представлен пример обнаружения точек изменений.

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a>Создание метода DetectChangepoint()

В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `DetectChangepoint()`:

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

Метод `DetectChangepoint()` выполняет следующие задачи:

* обучение модели;
* Обнаруживает точки изменений на основе исторических данных о продажах.
* Отображает результаты.

Создайте метод `DetectChangepoint()` сразу после метода `Main()`, вставив в него следующий код:

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

[IidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) используется для обучения модели для обнаружения точек изменений. Добавьте его в метод `DetectChangepoint()` со следующим кодом:

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

Как и раньше, обучите модель на основе данных `productSales`, добавив следующую строку кода в метод `DetectChangePoint()`:

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

Используйте метод `Transform()` для преобразования данных `Training`, добавив в `DetectChangePoint()` следующий код:

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

Как и ранее, преобразуйте `transformedData` в строго типизированный `IEnumerable` для более удобного отображения с помощью метода `CreateEnumerable()`, используя следующий код:

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

Создайте отображаемый заголовок, добавив в следующую строку метода `DetectChangePoint()` приведенный ниже код.

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

В результатах обнаружения точек изменений будут отображены следующие сведения:

* `Alert` указывает на оповещение о точке изменений для заданной точки данных.
* `Score` является значением `ProductSales` для заданной точки данных в наборе данных.
* `P-Value` — "P" означает вероятность. Указывает, с какой вероятностью эта точка данных является аномалией. 
* `Martingale value` — используется для определения того, насколько "странной" является точка данных, на основе последовательности P-значений.  

Используйте следующий код, чтобы выполнить итерацию по `predictions` `IEnumerable` и отобразить результаты:

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a>Результаты обнаружения точек изменений

Результаты выполнения должны выглядеть примерно так, как показано ниже. Во время обработки отображаются сообщения. Вы можете видеть предупреждения или обработанные сообщения. Для удобства они удалены из следующих результатов.

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

Поздравляем! Вы успешно создали модели машинного обучения для обнаружения аномалий в виде пиковых значений и точек изменений в данных о продажах.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Загрузка данных
> * Обучение модели для обнаружения пиковых аномалий
> * Обнаружение пиковых аномалий с помощью обученной модели
> * Обучение модели для обнаружения аномалий в точке изменений
> * Обнаружение аномалий в точке изменений с помощью обученной модели

## <a name="next-steps"></a>Следующие шаги

Ознакомьтесь с примерами машинного обучения в репозитории GitHub, чтобы подробнее изучить расширенный пример с обнаружением аномалий для энергопотребления.
> [!div class="nextstepaction"]
> [Репозиторий GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/TimeSeries_PowerAnomalyDetection)
