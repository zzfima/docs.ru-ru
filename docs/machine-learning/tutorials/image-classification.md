---
title: Учебник. Повторное обучение классификатора изображений TensorFlow (передача обучения)
description: Из этой статьи вы узнаете, как повторно обучить модель TensorFlow для классификации изображений с помощью передачи обучения и ML.NET. Исходная модель была обучена для классификации отдельных изображений. После повторного обучения новая модель сортирует изображения по различным категориям.
ms.date: 06/12/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 2ad9e71f572cb694897fd12ecbb15da069afe338
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67026079"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a>Учебник. Повторное обучение классификатора изображений TensorFlow с помощью передачи обучения и ML.NET

Из этой статьи вы узнаете, как повторно обучить модель TensorFlow для классификации изображений с помощью передачи обучения и ML.NET. Исходная модель была обучена для классификации отдельных изображений. После повторного обучения новая модель сортирует изображения по различным категориям. 

Обучение модели для [классификации изображений](https://en.wikipedia.org/wiki/Outline_of_object_recognition) с нуля предусматривает настройку нескольких миллионов параметров, а также использование огромных объемов помеченных данных обучения и вычислительных ресурсов (сотни часов работы GPU). Хотя передача обучения не настолько эффективна, как обучение пользовательской модели с нуля, этот подход позволяет значительно ускорить соответствующий процесс с использованием всего нескольких тысяч изображений (а не миллионов помеченных изображений) для быстрого создания пользовательской модели (в пределах часа на компьютере без GPU).

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> * Определение проблемы
> * повторно использовать и настраивать предварительно обученную модель;
> * классифицировать изображения.

## <a name="what-is-transfer-learning"></a>Что собой представляет передача обучения?

Хотели ли бы вы иметь возможность повторно использовать предварительно обученную модель для решения похожей проблемы, а также переобучать для этой цели все или некоторые слои такой модели? Подход с повторным использованием части уже обученной модели для создания новой называется [передачей обучения](https://en.wikipedia.org/wiki/Transfer_learning).

## <a name="image-classification-sample-overview"></a>Пример классификации изображений

Этот пример представляет собой консольное приложение, которое использует ML.NET для создания классификатора изображений путем повторного применения предварительно обученной модели для классификации изображений на основе небольшого объема данных обучения.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

## <a name="prerequisites"></a>Предварительные требования

* [Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".

* Пакет Nuget для Microsoft.ML 1.0.0.
* Пакет Nuget для Microsoft.ML.ImageAnalytics 1.0.0.
* Пакет Nuget для Microsoft.ML.TensorFlow 0.12.0.

* [ZIP-файл каталога ресурсов руководства.](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [Модель машинного обучения Inception версии 3.](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>Выбор подходящей задачи машинного обучения

[Глубокое обучение](https://en.wikipedia.org/wiki/Deep_learning) — это разновидность машинного обучения, которая произвела революцию в области компьютерного зрения и распознавания речи.

Модели глубокого обучения обучаются на крупных наборах [помеченных данных](https://en.wikipedia.org/wiki/Labeled_data) с использованием [нейронных сетей](https://en.wikipedia.org/wiki/Artificial_neural_network), которые содержат множество слоев обучения. Глубокое обучение:

* лучше выполняет некоторые задачи, например в области компьютерного зрения;

* хорошо работает с огромными объемами данных.

Классификация изображений — это типичная задача Машинного обучения, которая позволяет автоматически классифицировать изображения по нескольким категориям, например:

* для определения того, содержит ли изображение человеческое лицо;
* для различения изображений котов и собак.

 Или же она помогает определить тип объекта на изображении — еда, игрушка или прибор:

![Изображение с пиццей](./media/image-classification/220px-Pepperoni_pizza.jpg)
![Изображение с плюшевым мишкой](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![Изображение с тостером](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> Изображения выше принадлежат Викискладу и имеют следующие атрибуты:
>
> * 220px-Pepperoni_pizza.jpg, открытый источник, https://commons.wikimedia.org/w/index.php?curid=79505;
> * 119px-Nalle_-_a_small_brown_teddy_bear.jpg, автор — [Jonik](https://commons.wikimedia.org/wiki/User:Jonik), автофотография, лицензия CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166;
> * 193px-Broodrooster.jpg, автор — [M. Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972), собственное фото, лицензия CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403.

При передаче обучения могут использоваться разные стратегии, например *переобучение всех слоев* и *предпоследнего слоя*. В этом руководстве поясняется и демонстрируется, как использовать *стратегию предпоследнего слоя*. В рамках *стратегии предпоследнего слоя* повторно используется модель, которая уже предварительно обучена решать конкретную проблему. Последний слой такой модели затем переобучается для решения новой проблемы. Повторное использование предварительно обученной модели для работы с новой моделью значительно экономит время и ресурсы.

Ваш пример модели классификации изображений повторно использует [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), популярную модель распознавания изображений, обученную на наборе данных `ImageNet`. В ходе этого процесса модель TensorFlow пытается выполнять классификацию целых изображений по множеству классов, например "Зонтик", "Майка" и "Посудомойка".

`Inception v3 model` можно классифицировать как [сверточную глубокую нейронную сеть](https://en.wikipedia.org/wiki/Convolutional_neural_network), которая может обеспечить достаточную производительность при выполнении сложных задач визуального распознавания, достигая в некоторых областях уровней не ниже или даже выше человеческих возможностей. Эта модель (алгоритм) разработана коллективом исследователей на основе исходной публикации [Rethinking the Inception Architecture for Computer Vision за авторством Szegedy и др.](https://arxiv.org/abs/1512.00567)

Так как `Inception model` уже обучена на тысячах различных изображений, она содержит [признаки изображений](https://en.wikipedia.org/wiki/Feature_(computer_vision)), необходимые для их идентификации. Нижние слои признаков изображений распознают простые признаки (например, контуры), а верхние слои — более сложные признаки (например, формы). Последний слой обучается на наборе данных намного меньшего размера, так как вы используете уже обученную модель, которая может классифицировать изображения. Так как ваша модель позволяет классифицировать изображения более чем по двум категориям, она относится к [многоклассовым классификаторам](../resources/tasks.md#multiclass-classification). 

`TensorFlow` — это популярный набор средств глубокого (машинного) обучения, который позволяет обучать глубокие нейронные сети и выполнять общие вычисления с числами. Они реализуется в ML.NET как `transformer`. В этом руководстве он используется для повторного использования `Inception model`.

Как показано на схеме ниже, вам нужно добавить ссылки на пакеты NuGet ML.NET в приложения .NET Core или .NET Framework. На внутреннем уровне ML.NET включает и ссылается на встроенную библиотеку `TensorFlow`, которая позволяет создавать код, загружающий существующую обученную модель `TensorFlow` для оценки.  

![Схема преобразования ML.NET с использованием TensorFlow](./media/image-classification/tensorflow-mlnet.png)

Модель `Inception model` обучена классифицировать изображения по тысяче категорий, но вам столько категорий не нужно. Также вам нужны четко определенные категории. Перейдем к этапу передачи (`transfer`) этого процесса передачи обучения (`transfer learning`). Вы можете передать способность `Inception model` распознавать и классифицировать изображения в новые ограниченные категории своего классификатора изображений.  

 Также вы можете переобучить последний слой такой модели с помощью набора из трех категорий:

* еда;
* игрушка;
* прибор.

Ваш слой будет использовать [алгоритм мультиномиальной логистической регрессии](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) для поиска корректной категории за минимальное время. Для поиска ответа этот алгоритм выполняет классификацию на основе вероятностей, присваивая соответствующей категории значение единицы, а всем остальным — нулевое значение.  

### <a name="dataset"></a>DataSet

Доступны два источника данных: файл `.tsv` и файлы образов.  Файл `tags.tsv` содержит два столбца: первый определен как `ImagePath`, а во втором указана метка `Label`, соответствующая изображению. В примере файла ниже отсутствует строка заголовка. Сам файл выглядит следующим образом:

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

Изображения для обучения и тестирования расположены в папках ресурсов, которые вы скачали в виде ZIP-файла. Эти изображения принадлежат Викискладу.
> *[Викисклад](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), бесплатный репозиторий мультимедиа.* Получено в 10:48 17 октября 2018 г. со страниц:  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>Создание консольного приложения

### <a name="create-a-project"></a>Создание проекта

1. Создайте **консольное приложение .NET Core** с именем TransferLearningTF.

2. Установите **пакет NuGet для Microsoft.ML**:

    В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**. Выберите nuget.org в качестве источника пакета, откройте вкладку "Обзор" и выполните поиск **Microsoft.ML**. Щелкните раскрывающийся список **Версия**, выберите пакет **1.0.0** в списке и нажмите кнопку **Установить**. Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов. Повторите эти шаги для пакетов **Microsoft.ML.ImageAnalytics версии 1.0.0** и **Microsoft.ML.TensorFlow версии 0.12.0**.

### <a name="prepare-your-data"></a>подготавливать данные;

1. Скачайте [ZIP-файл каталога с ресурсами проекта](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip) и распакуйте его.

2. Скопируйте каталог `assets` в каталог проекта *TransferLearningTF*. Этот каталог и его подкаталоги содержат данные и файлы поддержки (за исключением модели Inception, которую вы скачаете и добавите на следующем шаге), необходимые для работы с этим руководством.

3. Скачайте [модель Inception](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) и распакуйте ее.

4. Скопируйте содержание каталога `inception5h`, который вы распаковали, в каталог `assets\inputs-train\inception` проекта *TransferLearningTF*. Этот каталог содержит модель и дополнительные файлы поддержки, необходимые для работы с этим руководством, как показано на следующем рисунке:

   ![Содержание каталога Inception](./media/image-classification/inception-files.png)

5. В обозревателе решений щелкните правой кнопкой мыши каждый файл в каталоге и подкаталогах ресурсов и выберите **Свойства**. В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.

### <a name="create-classes-and-define-paths"></a>Создание классов и определение путей

Добавьте следующие новые операторы `using` в начало файла *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

Создайте глобальные поля для хранения путей к различным ресурсам, а также глобальные переменные для значений `LabelTokey`, `ImageReal` и `PredictedLabelValue`:

* `_assetsPath` содержит путь к ресурсам.
* `_trainTagsTsv` содержит путь к TSV-файлу с тегами данных изображения обучения.
* `_predictTagsTsv` содержит путь к TSV-файлу с тегами данных изображения прогнозирования.
* `_trainImagesFolder` содержит путь к изображениям, используемым для обучения модели.
* `_predictImagesFolder` содержит путь к изображениям, классифицируемым обученной моделью.
* `_inceptionPb` содержит путь к предварительно обученной модели Inception, которая используется для переобучения вашей модели.
* `_inputImageClassifierZip` содержит путь, из которого загружается обученная модель.
* `_outputImageClassifierZip` содержит путь, по которому сохраняется обученная модель.
* `LabelTokey` — это значение `Label`, сопоставленное с ключом.
* `ImageReal` — это столбец, содержащий спрогнозированное значение изображения.
* `PredictedLabelValue` — это столбец, содержащий спрогнозированное значение метки.

Добавьте следующий код в строку непосредственно над методом `Main`, чтобы указать эти пути и другие переменные:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

Создайте несколько классов для входных данных и прогнозов. Добавьте в проект новый класс:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImageData.cs*. Теперь нажмите кнопку **Добавить**.

    Файл *ImageData.cs* откроется в редакторе кода. Добавьте следующую инструкцию `using` в начало файла *ImageData.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

Удалите существующее определение класса и добавьте следующий код для класса `ImageData` в файл *ImageData.cs*:

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData` является классом входных данных изображения и имеет следующие поля <xref:System.String>:

* `ImagePath` содержит имя файла изображения.
* `Label` содержит значение для метки изображения.

Добавьте новый класс в свой проект для `ImagePrediction`:

1. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

1. В диалоговом окне **Добавление нового элемента** выберите **Класс** и измените значение поля **Имя** на *ImagePrediction.cs*. Теперь нажмите кнопку **Добавить**.

    Файл *ImagePrediction.cs* откроется в редакторе кода. Удалите обе инструкции `using` `System.Collections.Generic` и `System.Text` в начале файла *ImagePrediction.cs*:

Удалите существующее определение класса и добавьте следующий код с классом `ImagePrediction` в файл *ImagePrediction.cs*:

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction` является классом прогноза изображения и имеет следующие поля:

* `Score` содержит процентное значение достоверности для конкретной классификации изображения.
* `PredictedLabelValue` содержит значение для прогнозируемой метки классификации изображения.

Класс `ImagePrediction` используется для прогнозирования после обучения модели. Он включает `string` (`ImagePath`) с путем к изображению. `Label` используется для применения и переобучения модели. `PredictedLabelValue` используется для прогнозирования и оценки. Для оценки применяются входные обучающие данные, прогнозируемые значения и модель.

[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели. По существу он аналогичен классу `DBContext` в Entity Framework.

### <a name="initialize-variables-in-main"></a>Инициализация переменных в методе Main

Инициализируйте переменную `mlContext` с использованием нового экземпляра `MLContext`.  Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>Создание структуры для параметров по умолчанию

Модель Inception имеет несколько параметров по умолчанию, которые необходимо передать. Создайте структуру, чтобы сопоставить значения параметров по умолчанию с понятными именами, с помощью следующего кода сразу после метода `Main()`:

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>Создание служебного метода для отображения данных

Поскольку вы будете отображать данные изображения и связанные прогнозы несколько раз, создайте метод программы отображения для обработки отображения изображений и результатов прогнозирования.

Метод `DisplayResults()` выполняет следующие задачи:

* отображение результатов прогнозирования.

Создайте метод `DisplayResults()` сразу после структуры `InceptionSettings` с помощью следующего кода:

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

Метод `Transform()` заполняется `ImagePath` в `ImagePrediction` вместе с прогнозируемыми полями. В ходе процесса ML.NET каждый компонент добавляет столбцы, что упрощает отображение результатов:

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

Вы будете вызывать метод `DisplayResults()` в двух методах классификации изображений.

### <a name="create-a-tsv-file-utility-method"></a>Создание служебного метода для TSV-файла

Метод `ReadFromTsv()` выполняет следующие задачи:

* считывание файла `tags.tsv` с данными изображения;
* добавление пути файла к имени файла изображения;
* загрузка данных файла в объект IEnumerable `ImageData`.

Создайте метод `ReadFromTsv()` сразу после метода `PairAndDisplayResults()`, вставив в него следующий код:

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

Указанный ниже код анализирует файл `tags.tsv`, после чего добавляет путь к файлу к имени файла изображения для свойства `ImagePath` и загружает его и `Label` в объект `ImageData`. Добавьте его в качестве первой строки метода `ReadFromTsv()`.  Вам понадобится полный путь к файлу для отображения результатов прогнозирования.

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
В ML.NET есть три основных понятия: [данные](../resources/glossary.md#data), [преобразователи](../resources/glossary.md#transformer) и [средства оценки](../resources/glossary.md#estimator).

## <a name="reuse-and-tune-pre-trained-model"></a>Повторное использование и настройка предварительно обученной модели

В следующей строке кода в методе `Main()` добавьте приведенный ниже вызов метода `ReuseAndTuneInceptionModel()`:

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

Метод `ReuseAndTuneInceptionModel()` выполняет следующие задачи:

* загрузка данных;
* извлечение и преобразование данных;
* оценка модели TensorFlow;
* настройка (переобучение) модели;
* отображение результатов модели;
* оценка итоговой модели;
* возвращение модели.

Создайте метод `ReuseAndTuneInceptionModel()` сразу после структуры `InceptionSettings` и непосредственно перед методом `DisplayResults()` с помощью следующего кода:

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>Загрузка данных

Данные в ML.NET представлены [классом IDataView](xref:Microsoft.ML.IDataView). `IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые). Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).

Загрузите данные с помощью оболочки `MLContext.Data.LoadFromTextFile`. Добавьте в следующую строку метода `ReuseAndTuneInceptionModel()` приведенный ниже код:

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>Извлечение компонентов и преобразование данных

Предварительная обработка и очистка данных — это очень важные задачи, которые нужно выполнить перед использованием набора данных для машинного обучения.  Использование данных напрямую без этих задач моделирования может дать неправильные результаты.

Алгоритмы машинного обучения распознают данные с [присвоенными признаками](../resources/glossary.md#feature), поэтому при работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат. Этот формат — [числовой вектор](../resources/glossary.md#numerical-feature-vector).

После обучения и оценки создайте прогноз с помощью значений столбца **Label**. Так как вы используете предварительно обученную модель, сопоставьте поля с новой моделью с помощью метода [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A). Этот метод преобразует `Label` в столбец с числовыми ключами (`LabelTokey`) и добавляет его в виде нового столбца набора данных.  Присвойте этому средству оценки `estimator` имя, так как вы также добавите к нему метод обучения. Добавьте следующую строку кода:

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

Ваше средство оценки обработки изображений использует средства присвоения признаков предварительно обученной [глубокой нейронной сети (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) для выделения признаков. При работе с глубокими нейронными сетями вам необходимо преобразовать изображения в подходящий для сети формат. По этой причине вам нужно использовать несколько преобразований изображений, чтобы вы могли предоставить модели данные изображений в подходящем формате:

1. Изображения преобразования `LoadImages` загружаются в память как растровые изображения.
2. Преобразование `ResizeImages` изменяет размер изображений, так как предварительно обученная модель имеет определенные значения ширины и высоты изображений.
3. Преобразование `ExtractPixels` извлекает пиксели из входных изображений и преобразует их в числовой вектор.

Добавьте эти преобразования изображений в следующие строки кода:

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

`LoadTensorFlowModel` является удобным методом, который позволяет загружать модель `TensorFlow` один раз, а затем создает `TensorFlowEstimator` с помощью `ScoreTensorFlowModel`. Компонент `ScoreTensorFlowModel` выделяет указанные выходные данные (признаки изображения `Inception model``softmax2_pre_activation`) и присваивает набору данных оценку с помощью предварительно обученной модели `TensorFlow`.

Узел `softmax2_pre_activation` обеспечивает поддержку модели, определяя классы изображений. Узел `softmax2_pre_activation` возвращает значение вероятности для каждой категории изображения, причем сумма всех таких вероятностей должна равняться 1. Предполагается, что изображение принадлежит только к одной категории, как показано в следующем примере:

| Класс         | Вероятность   |
| ------------- | ------------- |
| `Food`        |  0,001        |
| `Toy`         |  0,95         |
| `Appliance`   |  0,06         |

Добавьте `TensorFlowTransform` к `estimator` с помощью такой строки кода:

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>Выбор алгоритма обучения

Чтобы добавить алгоритм обучения, вызовите метод оболочки `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()`.  Класс [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) добавляется в `estimator` и принимает признаки изображения Inception (`softmax2_pre_activation`) и входные параметры `Label` для обучения на основе исторических данных.  Добавьте метод обучения с помощью следующего кода:

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

Вам также нужно сопоставить `predictedlabel` с `predictedlabelvalue`:

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

Метод `Fit()` обучает модель путем преобразования набора данных и применения обучения. Обучите модель на основе обучающего набора данных и получите обученную модель, добавив в метод `ReuseAndTuneInceptionModel()` следующие строки кода:

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

Метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) делает прогнозы для нескольких входных строк тестового набора данных.  Преобразуйте данные `Training`, добавив в метод `ReuseAndTuneInceptionModel()` следующий код:

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

Преобразуйте представления `DataViews` данных изображений и прогнозов в строго типизированные объекты `IEnumerables`, чтобы связать их для более удобного отображения. Для этого воспользуйтесь методом `MLContext.CreateEnumerable()`, добавив следующий код:

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

Вызовите метод `DisplayResults()`, чтобы отобразить данные и прогнозы, добавив в метод `ReuseAndTuneInceptionModel()` следующую строку кода:

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

Получив прогноз, с помощью метода [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) вы сможете:

* оценить модель (сравнивает спрогнозированные значения с фактическим набором данных `Labels`);

* получить метрики производительности модели.

В качестве следующей строки в методе `ReuseAndTuneInceptionModel()` добавьте приведенный ниже код:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

Для классификации изображений выполняется оценка следующих метрик:

* `Log-loss` — см. раздел [Логарифмические потери](../resources/glossary.md#log-loss). Значение логарифмических потерь должно быть максимально близко к нулю.

* `Per class Log-loss`. Значение логарифмических потерь для каждого класса должно быть максимально близко к нулю.

Используйте следующий код для отображения метрик, передачи результатов и выполнения действий по ним:

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 Добавьте следующий код, чтобы возвращать обученную модель:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a>классифицировать изображения с помощью загруженной модели.

Добавьте такой вызов в метод `ClassifyImages()` в следующей строке кода в методе `Main`:

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

Метод `ClassifyImages()` выполняет следующие задачи:

* считывание TSV-файла в интерфейс `IEnumerable`;
* создание прогноза для классификаций изображений на основе проверочных данных.

Создайте метод `ClassifyImages()` сразу после метода `ReuseAndTuneInceptionModel()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

Сначала вызовите метод `ReadFromTsv()` для создания класса `IEnumerable<ImageData>`, который содержит полный путь для каждого значения `ImagePath`. Вам потребуется такой путь к файлу для связывания данных и результатов прогнозирования. Вам также нужно преобразовать класс `IEnumerable<ImageData>` в класс `IDataView`, который будет использоваться для прогнозирования. Добавьте такой код в следующие две строки в методе `ClassifyImages()`:

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

Как вы это уже сделали с данными изображения для обучения, создайте прогноз категории для проверочных данных изображения с помощью метода [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) переданной модели. Добавьте следующий код в метод `ClassifyImages()`, чтобы создавать прогнозы и преобразовывать `predictions` `IDataView` в `IEnumerable` для связывания и отображения:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

Чтобы связать и отобразить проверочные данные изображения и прогнозы, добавьте такой код для вызова ранее созданного метода `DisplayResults()` в следующую строку метода `ClassifyImages()`:

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>Классификация отдельного изображения с помощью загруженной модели

Добавьте такой вызов в метод `ClassifySingleImage()` в следующей строке кода в методе `Main`:

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

Метод `ClassifySingleImage()` выполняет следующие задачи:

* загрузка экземпляра `ImageData`;
* создание прогноза для классификации изображений на основе проверочных данных.

Создайте метод `ClassifySingleImage()` сразу после метода `ClassifyImages()` и непосредственно перед методом `PairAndDisplayResults()` с помощью следующего кода:

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

Сначала создайте класс `ImageData`, который хранит полный путь и имя файла изображения для одного значения `ImagePath`. Добавьте такой код в следующие строки в методе `ClassifySingleImage()`:

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) — это удобный API, который создает прогноз на основе одного экземпляра данных. Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одному столбцу данных. Передайте значение `imageData` классу `PredictionEngine`, чтобы спрогнозировать категорию изображения, добавив следующий код в `ClassifySingleImage()`:

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

Отобразите результат прогнозирования с помощью следующей строки кода в методе `ClassifySingleImage()`:

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>Результаты

Выполнив предыдущие шаги, запустите консольное приложение (CTRL+F5). Результаты выполнения должны выглядеть примерно так, как указано ниже.  Кроме того, могут выводиться предупреждения или сообщения об обработке, но для удобства здесь мы убрали их.

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

Поздравляем! Вы успешно создали модель машинного обучения для классификации изображений на основе предварительно обученной модели `TensorFlow` в ML.NET.

Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF).

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> * Определение проблемы
> * повторно использовать и настраивать предварительно обученную модель;
> * классифицировать изображения с помощью загруженной модели.

Ознакомьтесь с примерами Машинного обучения в репозитории GitHub, чтобы подробнее изучить расширенный пример классификации изображений.
> [!div class="nextstepaction"]
> [Репозиторий GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/)
