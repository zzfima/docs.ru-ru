---
title: Учебник. Анализ тональности отзывов о фильмах с помощью предварительно обученной модели TensorFlow
description: В этом руководстве показано, как классифицировать тональность комментариев на веб-сайте с помощью предварительно обученной модели TensorFlow. Двоичный классификатор тональности — это консольное приложение на C#, разработанное с помощью Visual Studio.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 417abb5052df95c8496d97894d3e11d2956d7a1a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774400"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="6aa85-104">Учебник. Анализ тональности отзывов о фильмах с помощью предварительно обученной модели TensorFlow в ML.NET</span><span class="sxs-lookup"><span data-stu-id="6aa85-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="6aa85-105">В этом руководстве показано, как классифицировать тональность комментариев на веб-сайте с помощью предварительно обученной модели TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="6aa85-106">Двоичный классификатор тональности — это консольное приложение на C#, разработанное с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6aa85-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="6aa85-107">Модель TensorFlow, используемая в этом руководстве, была обучена на отзывах о фильмах из базы данных IMDB.</span><span class="sxs-lookup"><span data-stu-id="6aa85-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="6aa85-108">Завершив разработку приложения, вы сможете добавить текст отзыва о фильме, и приложение сообщит вам, положительный это отзыв или отрицательный.</span><span class="sxs-lookup"><span data-stu-id="6aa85-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="6aa85-109">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="6aa85-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6aa85-110">Загрузить предварительно обученную модель TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="6aa85-111">Преобразовать текст комментария на веб-сайте в признаки, пригодные для модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="6aa85-112">Использование модели для прогноза</span><span class="sxs-lookup"><span data-stu-id="6aa85-112">Use the model to make a prediction</span></span>

<span data-ttu-id="6aa85-113">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="6aa85-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6aa85-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6aa85-114">Prerequisites</span></span>

* <span data-ttu-id="6aa85-115">[Visual Studio 2017 версии 15.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="6aa85-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="6aa85-116">Установка</span><span class="sxs-lookup"><span data-stu-id="6aa85-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="6aa85-117">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="6aa85-117">Create the application</span></span>

1. <span data-ttu-id="6aa85-118">Создайте **консольное приложение .NET Core** с именем TextClassificationTF.</span><span class="sxs-lookup"><span data-stu-id="6aa85-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="6aa85-119">Создайте каталог с именем *Data* в проекте, чтобы сохранять файлы набора данных.</span><span class="sxs-lookup"><span data-stu-id="6aa85-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="6aa85-120">Установите **пакет NuGet для Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="6aa85-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="6aa85-121">В обозревателе решений щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="6aa85-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6aa85-122">Выберите nuget.org в качестве источника пакета, а затем выберите вкладку **Обзор**. Найдите **Microsoft.ML**, выберите пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6aa85-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="6aa85-123">Продолжите установку, соглашаясь с условиями лицензии для выбранного пакета.</span><span class="sxs-lookup"><span data-stu-id="6aa85-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="6aa85-124">Повторите эти действия для пакета **Microsoft.ML.TensorFlow**.</span><span class="sxs-lookup"><span data-stu-id="6aa85-124">Repeat these steps for **Microsoft.ML.TensorFlow**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="6aa85-125">Добавление модели TensorFlow в проект</span><span class="sxs-lookup"><span data-stu-id="6aa85-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="6aa85-126">Модель для этого руководства взята из репозитория GitHub [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model)</span><span class="sxs-lookup"><span data-stu-id="6aa85-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="6aa85-127">и сохранена в формате TensorFlow SavedModel.</span><span class="sxs-lookup"><span data-stu-id="6aa85-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="6aa85-128">Скачайте файл [sentiment_model zip](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true) и распакуйте его.</span><span class="sxs-lookup"><span data-stu-id="6aa85-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="6aa85-129">ZIP-файл содержит:</span><span class="sxs-lookup"><span data-stu-id="6aa85-129">The zip file contains:</span></span>

    * <span data-ttu-id="6aa85-130">`saved_model.pb`: собственно модель TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="6aa85-131">Модель принимает целочисленный массив признаков фиксированной длины (600 символов), представляющий текст в строке отзыва IMDB, и выводит две вероятности, сумма которых равна 1: вероятность того, что указанный отзыв имеет положительную тональность, и вероятность того, что отзыв имеет отрицательную тональность.</span><span class="sxs-lookup"><span data-stu-id="6aa85-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="6aa85-132">`imdb_word_index.csv`: сопоставление отдельных слов с целочисленным значением.</span><span class="sxs-lookup"><span data-stu-id="6aa85-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="6aa85-133">Сопоставление используется для создания входных признаков для модели TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="6aa85-134">Скопируйте содержимое самого внутреннего каталога `sentiment_model` в каталог `sentiment_model` проекта *TextClassificationTF*.</span><span class="sxs-lookup"><span data-stu-id="6aa85-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="6aa85-135">Этот каталог содержит модель и дополнительные файлы поддержки, необходимые для работы с этим руководством, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="6aa85-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Содержимое каталога sentiment_model](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="6aa85-137">В обозревателе решений щелкните правой кнопкой мыши каждый файл в каталоге `sentiment_model` и подкаталоге и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6aa85-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="6aa85-138">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="6aa85-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="6aa85-139">Добавление операторов using и глобальных переменных</span><span class="sxs-lookup"><span data-stu-id="6aa85-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="6aa85-140">Добавьте следующие новые операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="6aa85-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="6aa85-141">Создайте две глобальные переменные прямо над методом `Main`, чтобы указать путь к сохраненному файлу модели и длину вектора признаков.</span><span class="sxs-lookup"><span data-stu-id="6aa85-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="6aa85-142">`_modelPath` — путь к файлу обученной модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="6aa85-143">`FeatureLength` — длина целочисленного массива признаков, который ожидается в модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="6aa85-144">Моделирование данных</span><span class="sxs-lookup"><span data-stu-id="6aa85-144">Model the data</span></span>

<span data-ttu-id="6aa85-145">Отзывы на фильмы — это текст произвольной формы.</span><span class="sxs-lookup"><span data-stu-id="6aa85-145">Movie reviews are free form text.</span></span> <span data-ttu-id="6aa85-146">Приложение преобразует текст в формат входных данных, ожидаемый в модели, за несколько отдельных этапов.</span><span class="sxs-lookup"><span data-stu-id="6aa85-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="6aa85-147">Первый этап — разделение текста на отдельные слова и сопоставление каждого слова с кодировкой целого числа при помощи предоставленного файла сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6aa85-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="6aa85-148">Результатом этого преобразования является массив целых чисел переменной длины, которая соответствует числу слов в предложении.</span><span class="sxs-lookup"><span data-stu-id="6aa85-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="6aa85-149">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6aa85-149">Property</span></span>| <span data-ttu-id="6aa85-150">Значение</span><span class="sxs-lookup"><span data-stu-id="6aa85-150">Value</span></span>|<span data-ttu-id="6aa85-151">Тип</span><span class="sxs-lookup"><span data-stu-id="6aa85-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="6aa85-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="6aa85-152">ReviewText</span></span>|<span data-ttu-id="6aa85-153">this film is really good (это очень хороший фильм)</span><span class="sxs-lookup"><span data-stu-id="6aa85-153">this film is really good</span></span>|<span data-ttu-id="6aa85-154">string</span><span class="sxs-lookup"><span data-stu-id="6aa85-154">string</span></span>|
|<span data-ttu-id="6aa85-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="6aa85-155">VariableLengthFeatures</span></span>|<span data-ttu-id="6aa85-156">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="6aa85-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="6aa85-157">int[]</span><span class="sxs-lookup"><span data-stu-id="6aa85-157">int[]</span></span>|

<span data-ttu-id="6aa85-158">Затем размер массива признаков переменной длины изменяется на фиксированную длину 600.</span><span class="sxs-lookup"><span data-stu-id="6aa85-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="6aa85-159">Это ожидаемая длина для модели TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="6aa85-160">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6aa85-160">Property</span></span>| <span data-ttu-id="6aa85-161">Значение</span><span class="sxs-lookup"><span data-stu-id="6aa85-161">Value</span></span>|<span data-ttu-id="6aa85-162">Тип</span><span class="sxs-lookup"><span data-stu-id="6aa85-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="6aa85-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="6aa85-163">ReviewText</span></span>|<span data-ttu-id="6aa85-164">this film is really good (это очень хороший фильм)</span><span class="sxs-lookup"><span data-stu-id="6aa85-164">this film is really good</span></span>|<span data-ttu-id="6aa85-165">string</span><span class="sxs-lookup"><span data-stu-id="6aa85-165">string</span></span>|
|<span data-ttu-id="6aa85-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="6aa85-166">VariableLengthFeatures</span></span>|<span data-ttu-id="6aa85-167">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="6aa85-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="6aa85-168">int[]</span><span class="sxs-lookup"><span data-stu-id="6aa85-168">int[]</span></span>|
|<span data-ttu-id="6aa85-169">Функции</span><span class="sxs-lookup"><span data-stu-id="6aa85-169">Features</span></span>|<span data-ttu-id="6aa85-170">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="6aa85-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="6aa85-171">int[600]</span><span class="sxs-lookup"><span data-stu-id="6aa85-171">int[600]</span></span>|

1. <span data-ttu-id="6aa85-172">Создайте класс для входных данных после метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="6aa85-173">У класса входных данных `MovieReview` есть `string` (строка) для комментариев пользователей (`ReviewText`).</span><span class="sxs-lookup"><span data-stu-id="6aa85-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="6aa85-174">Создайте класс для признаков переменной длины после метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="6aa85-175">Свойство `VariableLengthFeatures` имеет атрибут [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A), который указывает вектор.</span><span class="sxs-lookup"><span data-stu-id="6aa85-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="6aa85-176">Все элементы вектора должны относиться к одному типу.</span><span class="sxs-lookup"><span data-stu-id="6aa85-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="6aa85-177">В наборах данных с большим количеством столбцов загрузка нескольких столбцов в виде одного вектора сокращает количество передаваемых данных при преобразовании данных.</span><span class="sxs-lookup"><span data-stu-id="6aa85-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="6aa85-178">Этот класс используется в действии `ResizeFeatures`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="6aa85-179">Имена его свойств (в этом случае — только одного свойства) используются для указания того, какие столбцы в DataView могут использоваться в качестве _входных данных_ для пользовательского действия сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6aa85-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="6aa85-180">Создайте класс для признаков фиксированной длины после метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="6aa85-181">Этот класс используется в действии `ResizeFeatures`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="6aa85-182">Имена его свойств (в этом случае — только одного свойства) используются для указания того, какие столбцы в DataView могут использоваться в качестве _выходных данных_ для пользовательского действия сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6aa85-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="6aa85-183">Обратите внимание, что имя свойства `Features` определяется моделью TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="6aa85-184">Это имя свойства нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="6aa85-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="6aa85-185">Создайте класс для прогноза после метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="6aa85-186">`MovieReviewSentimentPrediction` — этот класс прогноза используется после обучения модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="6aa85-187">`MovieReviewSentimentPrediction` имеет один массив `float` (`Prediction`) и атрибут `VectorType`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="6aa85-188">Создание MLContext, словаря подстановки и действия для изменения размера признаков</span><span class="sxs-lookup"><span data-stu-id="6aa85-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="6aa85-189">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для всех операций ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6aa85-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="6aa85-190">Инициализация `mlContext` создает новую среду ML.NET, которую могут совместно использовать объекты рабочего процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="6aa85-191">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="6aa85-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="6aa85-192">Замените строку `Console.WriteLine("Hello World!")` в методе `Main` следующим кодом, чтобы объявить и инициализировать переменную mlContext:</span><span class="sxs-lookup"><span data-stu-id="6aa85-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="6aa85-193">Создайте словарь для кодирования слов в виде целых чисел с помощью метода [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A), чтобы загрузить данные сопоставления из файла, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6aa85-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="6aa85-194">Слово</span><span class="sxs-lookup"><span data-stu-id="6aa85-194">Word</span></span>     |<span data-ttu-id="6aa85-195">Индекс</span><span class="sxs-lookup"><span data-stu-id="6aa85-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="6aa85-196">kids (дети)</span><span class="sxs-lookup"><span data-stu-id="6aa85-196">kids</span></span>     |  <span data-ttu-id="6aa85-197">362</span><span class="sxs-lookup"><span data-stu-id="6aa85-197">362</span></span>    |
    |<span data-ttu-id="6aa85-198">want</span><span class="sxs-lookup"><span data-stu-id="6aa85-198">want</span></span>     |  <span data-ttu-id="6aa85-199">181</span><span class="sxs-lookup"><span data-stu-id="6aa85-199">181</span></span>    |
    |<span data-ttu-id="6aa85-200">wrong (неправильно)</span><span class="sxs-lookup"><span data-stu-id="6aa85-200">wrong</span></span>    |  <span data-ttu-id="6aa85-201">355</span><span class="sxs-lookup"><span data-stu-id="6aa85-201">355</span></span>    |
    |<span data-ttu-id="6aa85-202">effects (эффекты)</span><span class="sxs-lookup"><span data-stu-id="6aa85-202">effects</span></span>  |  <span data-ttu-id="6aa85-203">302</span><span class="sxs-lookup"><span data-stu-id="6aa85-203">302</span></span>    |
    |<span data-ttu-id="6aa85-204">feeling (чувство)</span><span class="sxs-lookup"><span data-stu-id="6aa85-204">feeling</span></span>  |  <span data-ttu-id="6aa85-205">547</span><span class="sxs-lookup"><span data-stu-id="6aa85-205">547</span></span>    |

    <span data-ttu-id="6aa85-206">Добавьте приведенный ниже код для создания карты подстановки.</span><span class="sxs-lookup"><span data-stu-id="6aa85-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="6aa85-207">Добавьте `Action`, чтобы преобразовать массив целых чисел переменной длины в массив целых чисел фиксированного размера с помощью следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="6aa85-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="6aa85-208">Загрузка предварительно обученной модели TensorFlow</span><span class="sxs-lookup"><span data-stu-id="6aa85-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="6aa85-209">Добавьте код для загрузки модели TensorFlow:</span><span class="sxs-lookup"><span data-stu-id="6aa85-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="6aa85-210">После загрузки модели можно извлечь схему ее входных и выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6aa85-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="6aa85-211">Схемы отображаются только для интереса и изучения.</span><span class="sxs-lookup"><span data-stu-id="6aa85-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="6aa85-212">Для работы окончательного варианта приложения этот код не требуется.</span><span class="sxs-lookup"><span data-stu-id="6aa85-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    <span data-ttu-id="6aa85-213">Схема входных данных — это массив фиксированной длины из слов, закодированных в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="6aa85-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="6aa85-214">Схема выходных данных — это массив вероятностей с плавающей запятой, указывающий, является ли тональности обзора отрицательной или положительной.</span><span class="sxs-lookup"><span data-stu-id="6aa85-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="6aa85-215">Сумма этих значений равна 1, так как вероятность положительной тональности является дополнением вероятности отрицательной тональности.</span><span class="sxs-lookup"><span data-stu-id="6aa85-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="6aa85-216">Создание конвейера ML.NET</span><span class="sxs-lookup"><span data-stu-id="6aa85-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="6aa85-217">Создайте конвейер и разделите входной текст на слова с помощью преобразования [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A), чтобы разбить текст на слова в виде следующей строки кода:</span><span class="sxs-lookup"><span data-stu-id="6aa85-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="6aa85-218">В преобразовании [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) используются пробелы для разбиения текста или строки на слова.</span><span class="sxs-lookup"><span data-stu-id="6aa85-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="6aa85-219">Оно создает новый столбец и разделяет каждую входную строку на вектор подстрок на основе определяемого пользователем разделителя.</span><span class="sxs-lookup"><span data-stu-id="6aa85-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="6aa85-220">Сопоставьте слова с кодировкой целых чисел, используя таблицу подстановки, приведенную выше:</span><span class="sxs-lookup"><span data-stu-id="6aa85-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. <span data-ttu-id="6aa85-221">Измените размер кодировок целых чисел переменной длины на фиксированную длину, необходимую для модели:</span><span class="sxs-lookup"><span data-stu-id="6aa85-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. <span data-ttu-id="6aa85-222">Классифицируйте входные данные с помощью загруженной модели TensorFlow:</span><span class="sxs-lookup"><span data-stu-id="6aa85-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="6aa85-223">Имя выходных данных модели TensorFlow — `Prediction/Softmax`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="6aa85-224">Обратите внимание, что имя `Prediction/Softmax` определяется моделью TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="6aa85-225">Это имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="6aa85-225">You cannot change this name.</span></span>

1. <span data-ttu-id="6aa85-226">Создайте новый столбец для прогнозирования выходных данных:</span><span class="sxs-lookup"><span data-stu-id="6aa85-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="6aa85-227">Необходимо скопировать столбец `Prediction/Softmax` в столбец с именем, которое можно использовать как свойство в классе C# `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="6aa85-228">В имени свойства C# нельзя использовать символ `/`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="6aa85-229">Создание модели ML.NET из конвейера</span><span class="sxs-lookup"><span data-stu-id="6aa85-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="6aa85-230">Добавьте код для создания модели из конвейера:</span><span class="sxs-lookup"><span data-stu-id="6aa85-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="6aa85-231">Модель ML.NET создается из цепочки средств оценки в конвейере с помощью вызова метода `Fit`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="6aa85-232">В этом случае мы не будем подбирать данные для создания модели, так как модель TensorFlow уже обучена.</span><span class="sxs-lookup"><span data-stu-id="6aa85-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="6aa85-233">Мы предоставим пустой объект представления данных в соответствии с требованиями метода `Fit`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="6aa85-234">Использование модели для прогноза</span><span class="sxs-lookup"><span data-stu-id="6aa85-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="6aa85-235">Добавьте метод `PredictSentiment` под методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="6aa85-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="6aa85-236">Добавьте следующий код в качестве первой строки в методе `PredictSentiment()` для создания `PredictionEngine`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="6aa85-237">Класс [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) представляет собой удобный API, позволяющий осуществить прогнозирование на основе единственного экземпляра данных.</span><span class="sxs-lookup"><span data-stu-id="6aa85-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="6aa85-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) не является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="6aa85-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="6aa85-239">Допустимо использовать в средах прототипов или средах с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="6aa85-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="6aa85-240">Для улучшенной производительности и потокобезопасности в рабочей среде используйте службу `PredictionEnginePool`, которая создает [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) объектов [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) для использования во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="6aa85-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="6aa85-241">См. руководство по [использованию `PredictionEnginePool` в веб-API ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span><span class="sxs-lookup"><span data-stu-id="6aa85-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6aa85-242">Расширение службы `PredictionEnginePool` сейчас доступно в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="6aa85-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="6aa85-243">Добавьте комментарий для проверки прогнозирования обученной модели в методе `Predict()`, создав экземпляр `MovieReview`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. <span data-ttu-id="6aa85-244">Передайте тестовые данные комментариев в `Prediction Engine`, добавив следующие строки кода в метод `PredictSentiment()`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. <span data-ttu-id="6aa85-245">Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одной строке данных.</span><span class="sxs-lookup"><span data-stu-id="6aa85-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="6aa85-246">Свойство.</span><span class="sxs-lookup"><span data-stu-id="6aa85-246">Property</span></span>| <span data-ttu-id="6aa85-247">Значение</span><span class="sxs-lookup"><span data-stu-id="6aa85-247">Value</span></span>|<span data-ttu-id="6aa85-248">Тип</span><span class="sxs-lookup"><span data-stu-id="6aa85-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="6aa85-249">Прогноз</span><span class="sxs-lookup"><span data-stu-id="6aa85-249">Prediction</span></span>|<span data-ttu-id="6aa85-250">[0.5459937, 0.454006255]</span><span class="sxs-lookup"><span data-stu-id="6aa85-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="6aa85-251">float[]</span><span class="sxs-lookup"><span data-stu-id="6aa85-251">float[]</span></span>|

1. <span data-ttu-id="6aa85-252">Выведите прогноз тональности, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="6aa85-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="6aa85-253">Добавьте вызов `PredictSentiment` в конце метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="6aa85-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="6aa85-254">Результаты</span><span class="sxs-lookup"><span data-stu-id="6aa85-254">Results</span></span>

<span data-ttu-id="6aa85-255">Скомпонуйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="6aa85-255">Build and run your application.</span></span>

<span data-ttu-id="6aa85-256">Результаты выполнения должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6aa85-256">Your results should be similar to the following.</span></span> <span data-ttu-id="6aa85-257">Во время обработки отображаются сообщения.</span><span class="sxs-lookup"><span data-stu-id="6aa85-257">During processing, messages are displayed.</span></span> <span data-ttu-id="6aa85-258">Вы можете видеть предупреждения или обработанные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6aa85-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="6aa85-259">Для удобства эти сообщения удалены из следующих результатов.</span><span class="sxs-lookup"><span data-stu-id="6aa85-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="6aa85-260">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="6aa85-260">Congratulations!</span></span> <span data-ttu-id="6aa85-261">Вы успешно создали модель машинного обучения для классификации и прогнозирования тональности сообщений с помощью предварительно обученной модели `TensorFlow` в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6aa85-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="6aa85-262">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="6aa85-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="6aa85-263">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="6aa85-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6aa85-264">Загрузить предварительно обученную модель TensorFlow.</span><span class="sxs-lookup"><span data-stu-id="6aa85-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="6aa85-265">Преобразовать текст комментария на веб-сайте в признаки, пригодные для модели.</span><span class="sxs-lookup"><span data-stu-id="6aa85-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="6aa85-266">Использование модели для прогноза</span><span class="sxs-lookup"><span data-stu-id="6aa85-266">Use the model to make a prediction</span></span>
