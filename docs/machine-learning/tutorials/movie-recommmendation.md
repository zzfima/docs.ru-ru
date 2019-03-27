---
title: Использование ML.NET в сценарии рекомендации фильмов
description: Узнайте, как использовать ML.NET в сценарии рекомендации фильмов пользователям.
author: briacht
ms.author: johalex
ms.date: 03/08/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: 9b7ef12591e0a231b633f461547ec0eeaec1a530
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "58308124"
---
# <a name="tutorial-create-a-movie-recommender-with-mlnet"></a><span data-ttu-id="9edbe-103">Учебник. Создание системы рекомендации фильмов с помощью ML.NET</span><span class="sxs-lookup"><span data-stu-id="9edbe-103">Tutorial: Create a Movie Recommender with ML.NET</span></span>

<span data-ttu-id="9edbe-104">В этом практическом руководстве демонстрируется создание системы рекомендации фильмов на основе ML.NET в консольном приложении .NET Core на языке C# с помощью Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="9edbe-104">This sample tutorial illustrates using ML.NET to build a movie recommender via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="9edbe-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9edbe-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9edbe-106">выбрать алгоритм машинного обучения;</span><span class="sxs-lookup"><span data-stu-id="9edbe-106">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="9edbe-107">подготовить и загрузить данные;</span><span class="sxs-lookup"><span data-stu-id="9edbe-107">Prepare and load your data</span></span>
> * <span data-ttu-id="9edbe-108">создать и обучить модель;</span><span class="sxs-lookup"><span data-stu-id="9edbe-108">Build and train a model</span></span>
> * <span data-ttu-id="9edbe-109">оценить модель;</span><span class="sxs-lookup"><span data-stu-id="9edbe-109">Evaluate a model</span></span>
> * <span data-ttu-id="9edbe-110">развернуть и использовать модель.</span><span class="sxs-lookup"><span data-stu-id="9edbe-110">Deploy and consume a model</span></span>

> [!NOTE]
> <span data-ttu-id="9edbe-111">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="9edbe-111">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9edbe-112">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="9edbe-112">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9edbe-113">Сейчас в этом руководстве и соответствующем примере используется **ML.NET версии 0.11**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-113">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="9edbe-114">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="9edbe-114">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="9edbe-115">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="9edbe-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="9edbe-116">Рабочий процесс машинного обучения</span><span class="sxs-lookup"><span data-stu-id="9edbe-116">Machine learning workflow</span></span>
<span data-ttu-id="9edbe-117">Решение поставленной задачи, как и любой задачи в ML.NET, состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="9edbe-117">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="9edbe-118">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9edbe-118">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="9edbe-119">Создание и обучение модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-119">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="9edbe-120">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-120">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="9edbe-121">Использование модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-121">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="9edbe-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9edbe-122">Prerequisites</span></span>

* <span data-ttu-id="9edbe-123">[Visual Studio 2017 15.6 или более поздней версии](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) с установленной рабочей нагрузкой "Кроссплатформенная разработка .NET Core".</span><span class="sxs-lookup"><span data-stu-id="9edbe-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="9edbe-124">Выбор подходящей задачи машинного обучения</span><span class="sxs-lookup"><span data-stu-id="9edbe-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="9edbe-125">Есть несколько подходов к проблеме предоставления рекомендаций, например в отношении фильмов или связанных продуктов. В данном случае мы будем прогнозировать оценку (от 1 до 5), которую пользователь поставил бы определенному фильму, и рекомендуем этот фильм, если оценка выше установленного порога (чем выше оценка, тем больше вероятность того, что фильм понравится пользователю).</span><span class="sxs-lookup"><span data-stu-id="9edbe-125">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9edbe-126">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="9edbe-126">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="9edbe-127">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="9edbe-127">Create a project</span></span>

1. <span data-ttu-id="9edbe-128">Откройте Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="9edbe-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="9edbe-129">Выберите **Файл** > **Создать** > **Проект** в меню.</span><span class="sxs-lookup"><span data-stu-id="9edbe-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="9edbe-130">В диалоговом окне **Новый проект** выберите узел **Visual C#**, а затем — узел **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="9edbe-131">Выберите шаблон проекта **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="9edbe-132">В текстовом поле **Имя** введите "MovieRecommender", а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-132">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="9edbe-133">Создайте каталог с именем *Data* в папке проекта, чтобы сохранить в нем набор данных:</span><span class="sxs-lookup"><span data-stu-id="9edbe-133">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="9edbe-134">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Добавить** > **Новая папка**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="9edbe-135">Введите имя папки Data и нажмите клавишу "ВВОД".</span><span class="sxs-lookup"><span data-stu-id="9edbe-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="9edbe-136">Установите пакеты NuGet **Microsoft.ML** и **Microsoft.ML.Recommender**:</span><span class="sxs-lookup"><span data-stu-id="9edbe-136">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="9edbe-137">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9edbe-138">Выберите nuget.org в качестве источника пакетов, перейдите на вкладку **Обзор**, выполните поиск по фразе **Microsoft.ML**, выберите из списка этот пакет и нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9edbe-139">Нажмите кнопку **ОК** в диалоговом окне **Предварительный просмотр изменений**, а затем нажмите кнопку **Принимаю** в диалоговом окне **Принятие условий лицензионного соглашения**, если вы согласны с указанными условиями лицензионного соглашения для выбранных пакетов.</span><span class="sxs-lookup"><span data-stu-id="9edbe-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="9edbe-140">Повторите эти действия для пакета **Microsoft.ML.Recommender**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-140">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9edbe-141">В этом руководстве используются версии пакетов **Microsoft.ML 0.11.0** и **Microsoft.ML.Recommender 0.11.0**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-141">This tutorial uses **Microsoft.ML v0.11.0** and **Microsoft.ML.Recommender v0.11.0**.</span></span>
    
4. <span data-ttu-id="9edbe-142">Добавьте следующие операторы `using` в начало файла *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="9edbe-142">Add the following `using` statements at the top of your *Program.cs* file:</span></span>
    
    [!code-csharp[UsingStatements](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="9edbe-143">Скачивание данных</span><span class="sxs-lookup"><span data-stu-id="9edbe-143">Download your data</span></span>

1. <span data-ttu-id="9edbe-144">Скачайте два набора данных и сохраните их в ранее созданную папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="9edbe-144">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

*   <span data-ttu-id="9edbe-145">Щелкните файл [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) правой кнопкой мыши и выберите команду "Сохранить ссылку (объект) как...".</span><span class="sxs-lookup"><span data-stu-id="9edbe-145">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
*   <span data-ttu-id="9edbe-146">Щелкните файл [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) правой кнопкой мыши и выберите команду "Сохранить ссылку (объект) как...".</span><span class="sxs-lookup"><span data-stu-id="9edbe-146">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="9edbe-147">Файлы \*.csv нужно сохранить в папке *Data*. Если вы сохранили файлы \*.csv в другом месте, переместите их в папку *Data*.</span><span class="sxs-lookup"><span data-stu-id="9edbe-147">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="9edbe-148">В обозревателе решений щелкните правой кнопкой мыши каждый из файлов \*.csv и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-148">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="9edbe-149">В разделе **Дополнительно** для параметра **Копировать в выходной каталог** установите значение **Копировать более позднюю версию**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-149">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![Значение "Копировать более позднюю версию" в Visual Studio](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="9edbe-151">Загрузка данных</span><span class="sxs-lookup"><span data-stu-id="9edbe-151">Load your data</span></span>

<span data-ttu-id="9edbe-152">Первый шаг в процессе работы с ML.NET — подготовка и загрузка данных для обучения и тестирования модели.</span><span class="sxs-lookup"><span data-stu-id="9edbe-152">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="9edbe-153">Данные для оценки рекомендаций разделяются на наборы `Train` и `Test`.</span><span class="sxs-lookup"><span data-stu-id="9edbe-153">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="9edbe-154">Данные `Train` служат для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="9edbe-154">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="9edbe-155">Данные `Test` используются для прогнозирования на основе обученной модели и оценки ее эффективности.</span><span class="sxs-lookup"><span data-stu-id="9edbe-155">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="9edbe-156">Данные `Train` и `Test` обычно делятся в отношении 80/20.</span><span class="sxs-lookup"><span data-stu-id="9edbe-156">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="9edbe-157">Ниже приведен пример данных из ваших файлов \*.csv.</span><span class="sxs-lookup"><span data-stu-id="9edbe-157">Below is a preview of the data from your \*.csv files:</span></span>

![пример данных](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="9edbe-159">В файлах \*.csv четыре столбца:</span><span class="sxs-lookup"><span data-stu-id="9edbe-159">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="9edbe-160">В машинном обучении столбцы, используемые для прогнозирования, называются [признаками](../resources/glossary.md#feature), а столбец с итоговым прогнозом — [меткой](../resources/glossary.md#label).</span><span class="sxs-lookup"><span data-stu-id="9edbe-160">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="9edbe-161">Нам нужно прогнозировать рейтинг фильмов, поэтому меткой (`Label`) является столбец rating.</span><span class="sxs-lookup"><span data-stu-id="9edbe-161">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="9edbe-162">Остальные столбцы (`userId`, `movieId` и `timestamp`) — это признаки `Features`, используемые для прогнозирования метки `Label`.</span><span class="sxs-lookup"><span data-stu-id="9edbe-162">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="9edbe-163">Функции</span><span class="sxs-lookup"><span data-stu-id="9edbe-163">Features</span></span>      | <span data-ttu-id="9edbe-164">Метка</span><span class="sxs-lookup"><span data-stu-id="9edbe-164">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId `      |               |
| `timestamp`     |               |

<span data-ttu-id="9edbe-165">Какие признаки (`Features`) будут использоваться для прогнозирования метки (`Label`) — решать вам.</span><span class="sxs-lookup"><span data-stu-id="9edbe-165">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="9edbe-166">Для выбора подходящих признаков (`Features`) можно также использовать такие методы, как [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md).</span><span class="sxs-lookup"><span data-stu-id="9edbe-166">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="9edbe-167">В данном случае столбец `timestamp` следует исключить из числа признаков (`Feature`), так как метка времени не влияет на оценку фильма пользователем и поэтому не повышает точность прогноза:</span><span class="sxs-lookup"><span data-stu-id="9edbe-167">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="9edbe-168">Функции</span><span class="sxs-lookup"><span data-stu-id="9edbe-168">Features</span></span>      | <span data-ttu-id="9edbe-169">Метка</span><span class="sxs-lookup"><span data-stu-id="9edbe-169">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId `      |               |

<span data-ttu-id="9edbe-170">Далее необходимо определить структуру данных для входного класса.</span><span class="sxs-lookup"><span data-stu-id="9edbe-170">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="9edbe-171">Добавьте в проект новый класс:</span><span class="sxs-lookup"><span data-stu-id="9edbe-171">Add a new class to your project:</span></span>

1. <span data-ttu-id="9edbe-172">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите команду **Добавить > Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-172">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="9edbe-173">В диалоговом окне **Добавление нового элемента** выберите **Класс** и в поле **Имя** укажите *MovieRatingData.cs*.</span><span class="sxs-lookup"><span data-stu-id="9edbe-173">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="9edbe-174">Теперь нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9edbe-174">Then, select the **Add** button.</span></span>

<span data-ttu-id="9edbe-175">Файл *MovieRatingData.cs* откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="9edbe-175">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="9edbe-176">Добавьте следующий оператор `using` в начало файла *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9edbe-176">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="9edbe-177">Создайте класс `MovieRating`, удалив из файла *MovieRatingData.cs* существующее определение класса и добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-177">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](../../../samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="9edbe-178">`MovieRating` — это класс входных данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-178">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="9edbe-179">Атрибут [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) определяет столбцы в наборе данных, которые следует загрузить (по индексам).</span><span class="sxs-lookup"><span data-stu-id="9edbe-179">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="9edbe-180">Столбцы `userId` и `movieId` — это признаки `Features` (входные данные модели для прогнозирования метки `Label`), а столбец rating — это прогнозируемая метка `Label` (выходные данные модели).</span><span class="sxs-lookup"><span data-stu-id="9edbe-180">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="9edbe-181">Создайте еще один класс, `MovieRatingPrediction`, который будет представлять результаты прогнозирования. Для этого добавьте следующий код после класса `MovieRating` в файле *MovieRatingData.cs*:</span><span class="sxs-lookup"><span data-stu-id="9edbe-181">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](../../../samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="9edbe-182">В файле *Program.cs* замените строку `Console.WriteLine("Hello World!")` в методе `Main()` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="9edbe-182">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="9edbe-183">[Класс MLContext](xref:Microsoft.ML.MLContext) является отправной точкой для любых операций ML.NET. В результате инициализации класса `mlContext` создается среда ML.NET, которая может использоваться всеми объектами в рамках процесса создания модели.</span><span class="sxs-lookup"><span data-stu-id="9edbe-183">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="9edbe-184">По существу он аналогичен классу `DBContext` в Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9edbe-184">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="9edbe-185">После метода `Main()` создайте метод `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-185">After `Main()`, create a method called `LoadData()`:</span></span>
```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{


}
```

> [!NOTE]
> <span data-ttu-id="9edbe-186">Этот метод будет вызывать ошибку, пока вы не добавите оператор return при выполнении дальнейших инструкций.</span><span class="sxs-lookup"><span data-stu-id="9edbe-186">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="9edbe-187">Инициализируйте переменные, содержащие пути к данным, загрузите данные из файлов CSV и получите наборы данных `Train` и `Test` как объекты `IDataView`, добавив следующий код в метод `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-187">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="9edbe-188">Данные в ML.NET представлены [классом IDataView](xref:Microsoft.Data.DataView.IDataView).</span><span class="sxs-lookup"><span data-stu-id="9edbe-188">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.Data.DataView.IDataView).</span></span> <span data-ttu-id="9edbe-189">`IDataView` позволяет гибко и полно описывать табличные данные (числовые и текстовые).</span><span class="sxs-lookup"><span data-stu-id="9edbe-189">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="9edbe-190">Данные можно загружать в объект `IDataView` из текстового файла или в режиме реального времени (например, из базы данных SQL или файлов журнала).</span><span class="sxs-lookup"><span data-stu-id="9edbe-190">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="9edbe-191">Метод [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) определяет схему данных и считывает файл.</span><span class="sxs-lookup"><span data-stu-id="9edbe-191">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="9edbe-192">Он принимает переменные, содержащие пути к данным, и возвращает объект `IDataView`.</span><span class="sxs-lookup"><span data-stu-id="9edbe-192">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="9edbe-193">В данном случае вы указываете пути к файлам `Test` и `Train`, а также заголовок текстового файла (чтобы использовались правильные имена столбцов) и разделитель данных в виде запятой (по умолчанию разделителем является символ табуляции).</span><span class="sxs-lookup"><span data-stu-id="9edbe-193">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="9edbe-194">Добавьте в метод `Main()` следующие две строки кода для вызова метода `LoadData()` и получения наборов данных `Train` и `Test`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-194">Add the following as the next two lines of code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]


## <a name="build-and-train-your-model"></a><span data-ttu-id="9edbe-195">Создание и обучение модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-195">Build and train your model</span></span>

<span data-ttu-id="9edbe-196">В ML.NET есть три основных понятия: [данные](../basic-concepts-model-training-in-mldotnet.md#data), [преобразователи](../basic-concepts-model-training-in-mldotnet.md#transformer) и [средства оценки](../basic-concepts-model-training-in-mldotnet.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="9edbe-196">There are three major concepts in ML.NET: [Data](../basic-concepts-model-training-in-mldotnet.md#data), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer), and [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator).</span></span>

<span data-ttu-id="9edbe-197">Алгоритмам машинного обучения требуются данные в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="9edbe-197">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="9edbe-198">Преобразователи (`Transformers`) приводят данные к совместимому формату.</span><span class="sxs-lookup"><span data-stu-id="9edbe-198">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![схема работы преобразователя](./media/movie-recommendation/transformer.png)

<span data-ttu-id="9edbe-200">Преобразователи (`Transformers`) в ML.NET создаются с помощью средств оценки (`Estimators`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-200">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="9edbe-201">Средства оценки (`Estimators`) принимают данные и возвращают преобразователи (`Transformers`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-201">`Estimators` take in data and return `Transformers`.</span></span>

![схема работы средства оценки](./media/movie-recommendation/estimator.png)

<span data-ttu-id="9edbe-203">Алгоритм рекомендаций, который вы будете использовать для обучения модели, — это пример средства оценки (`Estimator`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-203">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="9edbe-204">Чтобы создать средство оценки (`Estimator`), выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9edbe-204">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="9edbe-205">Создайте метод `BuildAndTrainModel()` сразу после метода `LoadData()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-205">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>
```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{


}
```
> [!NOTE]
> <span data-ttu-id="9edbe-206">Этот метод будет вызывать ошибку, пока вы не добавите оператор return при выполнении дальнейших инструкций.</span><span class="sxs-lookup"><span data-stu-id="9edbe-206">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="9edbe-207">Определите преобразования данных, добавив в метод `BuildAndTrainModel()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-207">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>
   
[!code-csharp[DataTransformations](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="9edbe-208">Так как столбцы `userId` и `movieId` содержат индексы пользователей и фильмов, а не реальные значения, необходимо с помощью метода [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) преобразовать столбцы `userId` и `movieId` в столбцы признаков (`Feature`), содержащие числовые ключи (допустимый формат для алгоритмов рекомендаций), а затем добавить их в качестве новых столбцов наборов данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-208">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="9edbe-209">userId</span><span class="sxs-lookup"><span data-stu-id="9edbe-209">userId</span></span> | <span data-ttu-id="9edbe-210">movieId</span><span class="sxs-lookup"><span data-stu-id="9edbe-210">movieId</span></span> | <span data-ttu-id="9edbe-211">Метка</span><span class="sxs-lookup"><span data-stu-id="9edbe-211">Label</span></span> | <span data-ttu-id="9edbe-212">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="9edbe-212">userIdEncoded</span></span> | <span data-ttu-id="9edbe-213">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="9edbe-213">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="9edbe-214">1</span><span class="sxs-lookup"><span data-stu-id="9edbe-214">1</span></span> | <span data-ttu-id="9edbe-215">1</span><span class="sxs-lookup"><span data-stu-id="9edbe-215">1</span></span> | <span data-ttu-id="9edbe-216">4</span><span class="sxs-lookup"><span data-stu-id="9edbe-216">4</span></span> | <span data-ttu-id="9edbe-217">userKey1</span><span class="sxs-lookup"><span data-stu-id="9edbe-217">userKey1</span></span> | <span data-ttu-id="9edbe-218">movieKey1</span><span class="sxs-lookup"><span data-stu-id="9edbe-218">movieKey1</span></span> |
| <span data-ttu-id="9edbe-219">1</span><span class="sxs-lookup"><span data-stu-id="9edbe-219">1</span></span> | <span data-ttu-id="9edbe-220">3</span><span class="sxs-lookup"><span data-stu-id="9edbe-220">3</span></span> | <span data-ttu-id="9edbe-221">4</span><span class="sxs-lookup"><span data-stu-id="9edbe-221">4</span></span> | <span data-ttu-id="9edbe-222">userKey1</span><span class="sxs-lookup"><span data-stu-id="9edbe-222">userKey1</span></span> | <span data-ttu-id="9edbe-223">movieKey2</span><span class="sxs-lookup"><span data-stu-id="9edbe-223">movieKey2</span></span> |
| <span data-ttu-id="9edbe-224">1</span><span class="sxs-lookup"><span data-stu-id="9edbe-224">1</span></span> | <span data-ttu-id="9edbe-225">6</span><span class="sxs-lookup"><span data-stu-id="9edbe-225">6</span></span> | <span data-ttu-id="9edbe-226">4</span><span class="sxs-lookup"><span data-stu-id="9edbe-226">4</span></span> | <span data-ttu-id="9edbe-227">userKey1</span><span class="sxs-lookup"><span data-stu-id="9edbe-227">userKey1</span></span> | <span data-ttu-id="9edbe-228">movieKey3</span><span class="sxs-lookup"><span data-stu-id="9edbe-228">movieKey3</span></span> |


<span data-ttu-id="9edbe-229">Выберите алгоритм машинного обучения и добавьте его к определениям преобразований данных, добавив в метод `BuildAndTrainModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-229">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="9edbe-230">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) — это алгоритм обучения для предоставления рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="9edbe-230">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="9edbe-231">[Разложение матрицы](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) — стандартный подход к формированию рекомендаций при наличии данных о том, как пользователи оценивали продукты в прошлом, как в нашем случае.</span><span class="sxs-lookup"><span data-stu-id="9edbe-231">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="9edbe-232">Есть и другие алгоритмы рекомендаций, которые используются при наличии других данных (дополнительные сведения см. в. разделе [Другие алгоритмы рекомендаций](#other-recommendation-algorithms) ниже).</span><span class="sxs-lookup"><span data-stu-id="9edbe-232">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span> 

<span data-ttu-id="9edbe-233">В данном случае алгоритм разложения матрицы (`Matrix Factorization`) использует метод, называемый "совместная фильтрация". Он основывается на том допущении, что если мнение двух людей по какому-либо вопросу совпадает, то и по другому вопросу они будут склонны иметь одинаковое мнение.</span><span class="sxs-lookup"><span data-stu-id="9edbe-233">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="9edbe-234">Например, если два пользователя одинаково оценили определенный фильм, то второму из них с большой вероятностью понравится другой фильм, который посмотрел и высоко оценил первый пользователь.</span><span class="sxs-lookup"><span data-stu-id="9edbe-234">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="9edbe-235">Пользователь 1</span><span class="sxs-lookup"><span data-stu-id="9edbe-235">User 1</span></span> | <span data-ttu-id="9edbe-236">Посмотрел фильм и поставил отметку "Нравится"</span><span class="sxs-lookup"><span data-stu-id="9edbe-236">Watched and liked movie</span></span> | <span data-ttu-id="9edbe-237">Посмотрел фильм и поставил отметку "Нравится"</span><span class="sxs-lookup"><span data-stu-id="9edbe-237">Watched and liked movie</span></span> | <span data-ttu-id="9edbe-238">Посмотрел фильм и поставил отметку "Нравится"</span><span class="sxs-lookup"><span data-stu-id="9edbe-238">Watched and liked movie</span></span> |
| <span data-ttu-id="9edbe-239">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="9edbe-239">User 2</span></span> | <span data-ttu-id="9edbe-240">Посмотрел фильм и поставил отметку "Нравится"</span><span class="sxs-lookup"><span data-stu-id="9edbe-240">Watched and liked movie</span></span> | <span data-ttu-id="9edbe-241">Посмотрел фильм и поставил отметку "Нравится"</span><span class="sxs-lookup"><span data-stu-id="9edbe-241">Watched and liked movie</span></span> | <span data-ttu-id="9edbe-242">Не смотрел фильм — РЕКОМЕНДОВАТЬ</span><span class="sxs-lookup"><span data-stu-id="9edbe-242">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="9edbe-243">Алгоритм разложения матрицы (`Matrix Factorization`) имеет ряд [параметров](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), о которых можно прочитать в разделе [Гиперпараметры алгоритма](#algorithm-hyperparameters) ниже.</span><span class="sxs-lookup"><span data-stu-id="9edbe-243">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="9edbe-244">Обучите модель на основе данных `Train` и получите обученную модель, добавив в метод `BuildAndTrainModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-244">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="9edbe-245">Метод [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.Data.DataView.IDataView,Microsoft.Data.DataView.IDataView%29) обучает модель с помощью предоставленных наборов обучающих данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-245">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.Data.DataView.IDataView,Microsoft.Data.DataView.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="9edbe-246">С технической точки зрения, он выполняет определения средств оценки (`Estimator`), преобразовывая данные и применяя алгоритм обучения, а затем возвращает обученную модель, то есть преобразователь (`Transformer`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-246">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="9edbe-247">Добавьте в метод `Main()` следующую строку кода для вызова метода `BuildAndTrainModel()` и получения обученной модели:</span><span class="sxs-lookup"><span data-stu-id="9edbe-247">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="9edbe-248">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-248">Evaluate your model</span></span>

<span data-ttu-id="9edbe-249">После обучения модели оцените ее эффективность с помощью тестовых данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-249">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span> 

<span data-ttu-id="9edbe-250">Создайте метод `EvaluateModel()` сразу после метода `BuildAndTrainModel()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-250">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>
```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{


}
```

<span data-ttu-id="9edbe-251">Преобразуйте данные `Test`, добавив в метод `EvaluateModel()` следующий код: [!code-csharp[Transform](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span><span class="sxs-lookup"><span data-stu-id="9edbe-251">Transform the `Test` data by adding the following code to `EvaluateModel()`: [!code-csharp[Transform](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span></span>

<span data-ttu-id="9edbe-252">Метод [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) делает прогнозы для нескольких входных строк тестового набора данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-252">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="9edbe-253">Оцените модель, добавив в метод `EvaluateModel()` следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-253">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="9edbe-254">После получения прогноза метод [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) оценивает модель, сравнивая спрогнозированные значения с фактическими метками (`Labels`) в тестовом наборе данных, а затем возвращает метрики эффективности модели.</span><span class="sxs-lookup"><span data-stu-id="9edbe-254">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="9edbe-255">Чтобы вывести метрики оценки в консоль, добавьте в метод `EvaluateModel()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-255">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="9edbe-256">Добавьте в метод `Main()` следующую строку кода для вызова метода `EvaluateModel()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-256">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="9edbe-257">Теперь выходные данные должны выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="9edbe-257">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="9edbe-258">В этих выходных данных 20 итераций.</span><span class="sxs-lookup"><span data-stu-id="9edbe-258">In this output, there are 20 iterations.</span></span> <span data-ttu-id="9edbe-259">В каждой итерации мера погрешности уменьшается, приближаясь к 0.</span><span class="sxs-lookup"><span data-stu-id="9edbe-259">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="9edbe-260">Для измерения отклонения значений, спрогнозированных моделью, от фактических значений в тестовом наборе данных часто применяется среднеквадратичная погрешность (`root of mean squared error`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-260">The `root of mean squared error` (RMS or RMSE) is frequently used to measure the differences between values predicted by a model and the values observed in a test dataset.</span></span> <span data-ttu-id="9edbe-261">С технической точки зрения она вычисляется как квадратный корень из среднего значения квадратов погрешностей.</span><span class="sxs-lookup"><span data-stu-id="9edbe-261">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="9edbe-262">Значение среднеквадратичной погрешности должно быть максимально близко к 1.</span><span class="sxs-lookup"><span data-stu-id="9edbe-262">You want your RMSE score to be as close to 1 as possible.</span></span>

<span data-ttu-id="9edbe-263">R-квадрат (`R Squared`) — это доля отклонения спрогнозированных значений, описываемая моделью.</span><span class="sxs-lookup"><span data-stu-id="9edbe-263">`R Squared` is the variation percentage in the predicted values explained by your model.</span></span> <span data-ttu-id="9edbe-264">Он имеет значение от 0 до 1. Чем ближе значение к 0, тем лучше модель.</span><span class="sxs-lookup"><span data-stu-id="9edbe-264">It's a value between 0 and 1, and the closer the value is to 0, the better the model is.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="9edbe-265">Использование модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-265">Use your model</span></span>

<span data-ttu-id="9edbe-266">Теперь обученную модель можно использовать для прогнозирования на основе новых данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-266">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="9edbe-267">Создайте метод `UseModelForSinglePrediction()` сразу после метода `EvaluateModel()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-267">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>
```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{


}
```

<span data-ttu-id="9edbe-268">Для прогнозирования оценки используйте класс `PredictionEngine`. Добавьте в метод `UseModelForSinglePrediction()` следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-268">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="9edbe-269">[Класс PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) представляет собой удобный интерфейс API, позволяющий передать один экземпляр данных, на основе которого затем производится прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="9edbe-269">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass a single instance of data and then perform a prediction on this single instance of data.</span></span>

<span data-ttu-id="9edbe-270">Создайте экземпляр `MovieRating` с именем `testInput` и передайте его в PredictionEngine, добавив следующие строки кода в метод `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-270">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="9edbe-271">Функция [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) создает прогноз по одному столбцу данных.</span><span class="sxs-lookup"><span data-stu-id="9edbe-271">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="9edbe-272">Затем по значению `Score` (спрогнозированная оценка) можно определить, следует ли рекомендовать фильм с movieId 10 пользователю 6.</span><span class="sxs-lookup"><span data-stu-id="9edbe-272">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="9edbe-273">Чем больше значение `Score`, тем выше вероятность того, что пользователю понравится определенный фильм.</span><span class="sxs-lookup"><span data-stu-id="9edbe-273">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="9edbe-274">В данном случае допустим, что нужно рекомендовать фильмы с прогнозируемой оценкой более 3,5.</span><span class="sxs-lookup"><span data-stu-id="9edbe-274">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="9edbe-275">Чтобы вывести результаты, добавьте в метод `UseModelForSinglePrediction()` следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-275">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="9edbe-276">Добавьте в метод `Main()` следующую строку кода для вызова метода `UseModelForSinglePrediction()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-276">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="9edbe-277">Выходные данные этого метода должны выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="9edbe-277">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="9edbe-278">Сохранение модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-278">Save your model</span></span>
<span data-ttu-id="9edbe-279">Чтобы модель можно было использовать для прогнозирования в приложениях для конечных пользователей, ее нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="9edbe-279">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="9edbe-280">Создайте метод `SaveModel()` сразу после метода `UseModelForSinglePrediction()`, вставив в него следующий код:</span><span class="sxs-lookup"><span data-stu-id="9edbe-280">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>
```csharp
public static void SaveModel(MLContext mlContext, ITransformer model)
{


}
```

<span data-ttu-id="9edbe-281">Сохраните обученную модель, добавив в метод `SaveModel()` следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="9edbe-281">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="9edbe-282">Этот метод сохраняет обученную модель в ZIP-файле (в папке Data), который затем можно использовать в других приложениях .NET.</span><span class="sxs-lookup"><span data-stu-id="9edbe-282">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="9edbe-283">Добавьте в метод `Main()` следующую строку кода для вызова метода `SaveModel()`:</span><span class="sxs-lookup"><span data-stu-id="9edbe-283">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="9edbe-284">Использование сохраненной модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-284">Use your saved model</span></span>
<span data-ttu-id="9edbe-285">После сохранения обученной модели ее можно использовать в различных средах (сведения о реализации обученной модели машинного обучения в приложениях см. в [этом практическом руководстве](../how-to-guides/consuming-model-ml-net.md)).</span><span class="sxs-lookup"><span data-stu-id="9edbe-285">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="9edbe-286">Результаты</span><span class="sxs-lookup"><span data-stu-id="9edbe-286">Results</span></span>

<span data-ttu-id="9edbe-287">Выполнив описанные выше действия, запустите консольное приложение (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="9edbe-287">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="9edbe-288">Результаты выполнения одного прогноза должны выглядеть примерно так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9edbe-288">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="9edbe-289">Кроме того, могут выводиться предупреждения или сообщения об обработке, но для удобства здесь мы убрали их.</span><span class="sxs-lookup"><span data-stu-id="9edbe-289">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="9edbe-290">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="9edbe-290">Congratulations!</span></span> <span data-ttu-id="9edbe-291">Вы успешно создали модель машинного обучения для рекомендации фильмов.</span><span class="sxs-lookup"><span data-stu-id="9edbe-291">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="9edbe-292">Исходный код для этого руководства можно найти в репозитории [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="9edbe-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="9edbe-293">Улучшение модели</span><span class="sxs-lookup"><span data-stu-id="9edbe-293">Improve your model</span></span>

<span data-ttu-id="9edbe-294">Повысить эффективность модели для получения более точных прогнозов можно несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="9edbe-294">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="9edbe-295">Данные</span><span class="sxs-lookup"><span data-stu-id="9edbe-295">Data</span></span> 

<span data-ttu-id="9edbe-296">Чтобы повысить качество модели рекомендаций, можно дополнить обучающие данные для каждого пользователя и фильма.</span><span class="sxs-lookup"><span data-stu-id="9edbe-296">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="9edbe-297">[Перекрестная проверка](../how-to-guides/train-cross-validation-ml-net.md) — это способ оценки моделей, при котором данные разделяются на части случайным образом, после чего некоторые части используются для обучения, а остальные — для тестирования.</span><span class="sxs-lookup"><span data-stu-id="9edbe-297">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="9edbe-298">В плане качества модели такой метод лучше, чем фиксированное разделение общего набора на обучающие и тестовые данные, которое применялось в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="9edbe-298">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="9edbe-299">Функции</span><span class="sxs-lookup"><span data-stu-id="9edbe-299">Features</span></span>

<span data-ttu-id="9edbe-300">В этом руководстве использовались только три признака (`Features`) из набора данных (`user id`, `movie id` и `rating`).</span><span class="sxs-lookup"><span data-stu-id="9edbe-300">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span> 

<span data-ttu-id="9edbe-301">Хотя для начала этого достаточно, на практике может потребоваться добавить дополнительные атрибуты или признаки `Features` (например, возраст, пол, географическое местоположение и другие).</span><span class="sxs-lookup"><span data-stu-id="9edbe-301">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="9edbe-302">Добавление релевантных признаков (`Features`) может помочь повысить эффективность модели рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="9edbe-302">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span> 

<span data-ttu-id="9edbe-303">Если вы не уверены, какие признаки (`Features`) являются наиболее релевантными для конкретной задачи машинного обучения, можно использовать специальные методы, предоставляемые платформой ML.NET с целью выявления наиболее весомых признаков (`Features`): Feature Contribution Calculation (определение вклада признака) и [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) (важность комбинаций признаков).</span><span class="sxs-lookup"><span data-stu-id="9edbe-303">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="9edbe-304">Гиперпараметры алгоритма</span><span class="sxs-lookup"><span data-stu-id="9edbe-304">Algorithm hyperparameters</span></span>

<span data-ttu-id="9edbe-305">Алгоритмы, предоставляемые платформой ML.NET по умолчанию, достаточно эффективны, однако их можно еще более улучшить, настроив их [гиперпараметры](../resources/glossary.md#hyperparameter).</span><span class="sxs-lookup"><span data-stu-id="9edbe-305">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="9edbe-306">В случае с разложением матрицы (`Matrix Factorization`) можно поэкспериментировать с такими гиперпараметрами, как [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) и [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank).</span><span class="sxs-lookup"><span data-stu-id="9edbe-306">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="9edbe-307">Например, в этом учебнике алгоритм имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9edbe-307">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded", 
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="9edbe-308">Другие алгоритмы рекомендаций</span><span class="sxs-lookup"><span data-stu-id="9edbe-308">Other Recommendation Algorithms</span></span>
<span data-ttu-id="9edbe-309">Алгоритм разложения матрицы с совместной фильтрацией — лишь один из подходов к рекомендации фильмов.</span><span class="sxs-lookup"><span data-stu-id="9edbe-309">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="9edbe-310">Зачастую данные по оценкам могут отсутствовать, то есть доступны только данные по просмотренным пользователями фильмам.</span><span class="sxs-lookup"><span data-stu-id="9edbe-310">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="9edbe-311">В других случаях могут быть доступны дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="9edbe-311">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="9edbe-312">Алгоритм</span><span class="sxs-lookup"><span data-stu-id="9edbe-312">Algorithm</span></span>       | <span data-ttu-id="9edbe-313">Сценарий</span><span class="sxs-lookup"><span data-stu-id="9edbe-313">Scenario</span></span>           | <span data-ttu-id="9edbe-314">Пример</span><span class="sxs-lookup"><span data-stu-id="9edbe-314">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="9edbe-315">Разложение матрицы одного класса</span><span class="sxs-lookup"><span data-stu-id="9edbe-315">One Class Matrix Factorization</span></span> | <span data-ttu-id="9edbe-316">Следует использовать при наличии только столбцов userId и movieId.</span><span class="sxs-lookup"><span data-stu-id="9edbe-316">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="9edbe-317">Такой тип рекомендаций предназначен для сценария совместных покупок, то есть покупателям будет рекомендоваться набор продуктов исходя из их истории заказов.</span><span class="sxs-lookup"><span data-stu-id="9edbe-317">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="9edbe-318">> Попробовать</span><span class="sxs-lookup"><span data-stu-id="9edbe-318">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="9edbe-319">Факторизационные машины с полями</span><span class="sxs-lookup"><span data-stu-id="9edbe-319">Field Aware Factorization Machines</span></span> | <span data-ttu-id="9edbe-320">Следует использовать для рекомендаций при наличии дополнительных признаков, помимо userId, productId и rating (таких как описание или цена продукта).</span><span class="sxs-lookup"><span data-stu-id="9edbe-320">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="9edbe-321">Этот алгоритм также использует метод совместной фильтрации.</span><span class="sxs-lookup"><span data-stu-id="9edbe-321">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="9edbe-322">> Попробовать</span><span class="sxs-lookup"><span data-stu-id="9edbe-322">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="9edbe-323">Проблема нового пользователя</span><span class="sxs-lookup"><span data-stu-id="9edbe-323">New user scenario</span></span>
<span data-ttu-id="9edbe-324">Одна из распространенных проблем при использовании совместной фильтрации — это проблема "холодного запуска", когда для нового пользователя еще нет данных, на основе которых можно было бы делать выводы.</span><span class="sxs-lookup"><span data-stu-id="9edbe-324">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="9edbe-325">Для ее решения новому пользователю часто предлагается создать профиль и, например, оценить фильмы, которые он уже видел.</span><span class="sxs-lookup"><span data-stu-id="9edbe-325">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="9edbe-326">Хотя такой подход требует некоторых усилий от пользователя, он позволяет получить начальные данные, на которые можно было бы опираться.</span><span class="sxs-lookup"><span data-stu-id="9edbe-326">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="9edbe-327">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="9edbe-327">Resources</span></span>
<span data-ttu-id="9edbe-328">В этом учебнике используются данные из [набора данных MovieLens](http://files.grouplens.org/datasets/movielens/).</span><span class="sxs-lookup"><span data-stu-id="9edbe-328">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9edbe-329">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9edbe-329">Next steps</span></span>
<span data-ttu-id="9edbe-330">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="9edbe-330">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="9edbe-331">выбрать алгоритм машинного обучения;</span><span class="sxs-lookup"><span data-stu-id="9edbe-331">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="9edbe-332">подготовить и загрузить данные;</span><span class="sxs-lookup"><span data-stu-id="9edbe-332">Prepare and load your data</span></span>
> * <span data-ttu-id="9edbe-333">создать и обучить модель;</span><span class="sxs-lookup"><span data-stu-id="9edbe-333">Build and train a model</span></span>
> * <span data-ttu-id="9edbe-334">оценить модель;</span><span class="sxs-lookup"><span data-stu-id="9edbe-334">Evaluate a model</span></span>
> * <span data-ttu-id="9edbe-335">развернуть и использовать модель.</span><span class="sxs-lookup"><span data-stu-id="9edbe-335">Deploy and consume a model</span></span>

<span data-ttu-id="9edbe-336">Переходите к следующему руководству:</span><span class="sxs-lookup"><span data-stu-id="9edbe-336">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="9edbe-337">Анализ тональности</span><span class="sxs-lookup"><span data-stu-id="9edbe-337">Sentiment Analysis</span></span>](sentiment-analysis.md)
