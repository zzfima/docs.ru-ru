---
title: Анализ тональности с помощью интерфейса командной строки ML.NET
description: Автоматическое создание модели машинного обучения и связанного кода C# на основе примера набора данных
author: cesardl
ms.author: cesardl
ms.date: 12/23/2019
ms.custom: mvc
ms.topic: tutorial,mlnet-tooling
ms.openlocfilehash: d817e173239d2848fb16e94cca8ead563bc900a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187623"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a><span data-ttu-id="dcdbc-103">Анализ тональности с помощью интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="dcdbc-103">Analyze sentiment using the ML.NET CLI</span></span>

<span data-ttu-id="dcdbc-104">Узнайте, как с помощью ML.NET CLI автоматически создать модель ML.NET и базовый код C#.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-104">Learn how to use ML.NET CLI to automatically generate an ML.NET model and underlying C# code.</span></span> <span data-ttu-id="dcdbc-105">Вы предоставите набор данных и задачу машинного обучения, которую требуется реализовать, а CLI с помощью подсистемы AutoML создаст исходный код для формирования и развертывания модели, а также двоичную модель.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-105">You provide your dataset and the machine learning task you want to implement, and the CLI uses the AutoML engine to create model generation and deployment source code, as well as the binary model.</span></span>

<span data-ttu-id="dcdbc-106">Работая с этим учебником, вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-106">In this tutorial, you will do the following steps:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="dcdbc-107">подготовку данных для выбранной задачи машинного обучения;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-107">Prepare your data for the selected machine learning task</span></span>
> - <span data-ttu-id="dcdbc-108">запуск команды mlnet auto-train из CLI;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-108">Run the 'mlnet auto-train' command from the CLI</span></span>
> - <span data-ttu-id="dcdbc-109">просмотр результатов показателей качества;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-109">Review the quality metric results</span></span>
> - <span data-ttu-id="dcdbc-110">изучение созданного кода C# для использования модели в приложении;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-110">Understand the generated C# code to use the model in your application</span></span>
> - <span data-ttu-id="dcdbc-111">анализ созданного кода C#, который использовался для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-111">Explore the generated C# code that was used to train the model</span></span>

> [!NOTE]
> <span data-ttu-id="dcdbc-112">Здесь описано, как использовать средство ML.NET CLI, которое сейчас доступно в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-112">This topic refers to the ML.NET CLI tool, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="dcdbc-113">Дополнительные сведения см. на странице [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-113">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="dcdbc-114">ML.NET CLI входит в состав ML.NET, и его основной целью является упрощение изучения ML.NET для разработчиков .NET, поэтому, чтобы приступить к работе, не нужно писать код с нуля.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-114">The ML.NET CLI is part of ML.NET and its main goal is to "democratize" ML.NET for .NET developers when learning ML.NET so you don't need to code from scratch to get started.</span></span>

<span data-ttu-id="dcdbc-115">Для создания качественных моделей и исходного кода ML.NET на основе предоставляемых наборов обучающих данных средство ML.NET CLI можно запускать в любой командной строке (Windows, Mac или Linux).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-115">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) to generate good quality ML.NET models and source code based on training datasets you provide.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="dcdbc-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="dcdbc-116">Pre-requisites</span></span>

- <span data-ttu-id="dcdbc-117">[Пакет SDK для .NET Core 2.2 или более поздней версии](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-117">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) or later</span></span>
- <span data-ttu-id="dcdbc-118">(Необязательно) [Visual Studio 2017 или 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-118">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>
- [<span data-ttu-id="dcdbc-119">ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="dcdbc-119">ML.NET CLI</span></span>](../how-to-guides/install-ml-net-cli.md)

<span data-ttu-id="dcdbc-120">Вы можете запускать проекты, написанные на C#, из Visual Studio или с помощью `dotnet run` (.NET Core CLI).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-120">You can either run the generated C# code projects from Visual Studio or with `dotnet run` (.NET Core CLI).</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="dcdbc-121">подготавливать данные;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-121">Prepare your data</span></span>

<span data-ttu-id="dcdbc-122">Мы будем работать с существующим набором данных, используемым в сценарии "Анализ тональности", который представляет собой задачу машинного обучения двоичной классификации.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-122">We are going to use an existing dataset used for a 'Sentiment Analysis' scenario, which is a binary classification machine learning task.</span></span> <span data-ttu-id="dcdbc-123">Вы точно так же можете использовать собственный набор данных, а модель и код будут созданы автоматически.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-123">You can use your own dataset in a similar way, and the model and code will be generated for you.</span></span>

1. <span data-ttu-id="dcdbc-124">Скачайте [ZIP-файл набора данных предложений с меткой тональности UCI (ссылка дана в следующем примечании)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) и распакуйте его в любую папку.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-124">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip it on any folder you choose.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcdbc-125">Наборы данных в этом руководстве взяты из документа From Group to Individual Labels using Deep Features ("От групповых до индивидуальных меток с использованием функций глубокого обучения"), Котциас (Kotzias) и</span><span class="sxs-lookup"><span data-stu-id="dcdbc-125">The datasets this tutorial uses a dataset from the 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span></span> <span data-ttu-id="dcdbc-126">KDD 2015, и размещены в репозитории машинного обучения UCI Д. Дуа (D. Dua) и Э. Карра Танискиду (E. Karra Taniskidou) (2017).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="dcdbc-127">UCI Machine Learning Repository (Репозиторий машинного обучения UCI) [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="dcdbc-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="dcdbc-128">Ирвайн, Калифорния: Калифорнийский университет, Школа информационных технологий и компьютерных наук.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-128">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

2. <span data-ttu-id="dcdbc-129">Скопируйте файл `yelp_labelled.txt` в созданную ранее папку (например, `/cli-test`).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-129">Copy the `yelp_labelled.txt` file into any folder you previously created (such as `/cli-test`).</span></span>

3. <span data-ttu-id="dcdbc-130">Откройте предпочитаемую командную строку и перейдите к папке, куда был скопирован файл набора данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-130">Open your preferred command prompt and move to the folder where you copied the dataset file.</span></span> <span data-ttu-id="dcdbc-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-131">For example:</span></span>

    ```console
    cd /cli-test
    ```

    <span data-ttu-id="dcdbc-132">Используйте любой текстовый редактор, например Visual Studio Code, чтобы открыть и проанализировать файл набора данных `yelp_labelled.txt`.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-132">Using any text editor such as Visual Studio Code, you can open, and explore the `yelp_labelled.txt` dataset file.</span></span> <span data-ttu-id="dcdbc-133">Вы увидите следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-133">You can see that the structure is:</span></span>

    - <span data-ttu-id="dcdbc-134">У файла нет заголовка.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-134">The file has no header.</span></span> <span data-ttu-id="dcdbc-135">Вы будете использовать индекс столбца.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-135">You will use the column's index.</span></span>

    - <span data-ttu-id="dcdbc-136">Существует только два столбца:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-136">There are just two columns:</span></span>

        | <span data-ttu-id="dcdbc-137">Текст (индекс столбца — 0)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-137">Text (Column index 0)</span></span> | <span data-ttu-id="dcdbc-138">Надпись (индекс столбца — 1)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-138">Label (Column index 1)</span></span>|
        |--------------------------|-------|
        | <span data-ttu-id="dcdbc-139">Ого... Отличное место.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-139">Wow... Loved this place.</span></span> | <span data-ttu-id="dcdbc-140">1</span><span class="sxs-lookup"><span data-stu-id="dcdbc-140">1</span></span> |
        | <span data-ttu-id="dcdbc-141">Корочка так себе.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-141">Crust is not good.</span></span> | <span data-ttu-id="dcdbc-142">0</span><span class="sxs-lookup"><span data-stu-id="dcdbc-142">0</span></span> |
        | <span data-ttu-id="dcdbc-143">Невкусно, и текстура просто отвратительна.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-143">Not tasty and the texture was just nasty.</span></span> | <span data-ttu-id="dcdbc-144">0</span><span class="sxs-lookup"><span data-stu-id="dcdbc-144">0</span></span> |
        | <span data-ttu-id="dcdbc-145">…ЕЩЕ БОЛЬШЕ СТРОК ТЕКСТА…</span><span class="sxs-lookup"><span data-stu-id="dcdbc-145">...MANY MORE TEXT ROWS...</span></span> | <span data-ttu-id="dcdbc-146">…(1 или 0)…</span><span class="sxs-lookup"><span data-stu-id="dcdbc-146">...(1 or 0)...</span></span> |

    <span data-ttu-id="dcdbc-147">Закройте файл набора данных в редакторе.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-147">Make sure you close the dataset file from the editor.</span></span>

    <span data-ttu-id="dcdbc-148">Теперь вы готовы использовать CLI в сценарии "Анализ тональности".</span><span class="sxs-lookup"><span data-stu-id="dcdbc-148">Now, you are ready to start using the CLI for this 'Sentiment Analysis' scenario.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcdbc-149">После завершения работы с этим руководством попробуйте применить собственные наборы данных, при условии что они подходят для любой задачи машинного обучения, поддерживаемой в предварительной версии ML.NET CLI, — *"Двоичная классификация", "Многоклассовая классификация" и "Регрессия"* .</span><span class="sxs-lookup"><span data-stu-id="dcdbc-149">After finishing this tutorial you can also try with your own datasets as long as they are ready to be used for any of the ML tasks currently supported by the ML.NET CLI Preview which are *'Binary Classification', 'Multi-class Classification' and 'Regression'*).</span></span>

## <a name="run-the-mlnet-auto-train-command"></a><span data-ttu-id="dcdbc-150">Запуск команды mlnet auto-train</span><span class="sxs-lookup"><span data-stu-id="dcdbc-150">Run the 'mlnet auto-train' command</span></span>

1. <span data-ttu-id="dcdbc-151">Выполните следующую команду ML.NET CLI:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-151">Run the following ML.NET CLI command:</span></span>

    ```console
    mlnet auto-train --task binary-classification --dataset "yelp_labelled.txt" --label-column-index 1 --has-header false --max-exploration-time 10
    ```

    <span data-ttu-id="dcdbc-152">Эта команда запускает **`mlnet auto-train`команду**:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-152">This command runs the **`mlnet auto-train` command**:</span></span>
    - <span data-ttu-id="dcdbc-153">для **задачи машинного обучения** типа **`binary-classification`** ;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-153">for an **ML task** of type **`binary-classification`**</span></span>
    - <span data-ttu-id="dcdbc-154">использует **файл набора данных `yelp_labelled.txt`** в качестве обучающего и тестового набора данных (CLI внутренним образом применит перекрестную проверку или разделит его на два набора данных — один для обучения и один для тестирования);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-154">uses the **dataset file `yelp_labelled.txt`** as training and testing dataset (internally the CLI will either use cross-validation or split it in two datasets, one for training and one for testing)</span></span>
    - <span data-ttu-id="dcdbc-155">где **целевой столбец** (обычно называемый **меткой**), который нужно спрогнозировать представляет собой **столбец с индексом 1** (то есть второй столбец, поскольку индекс отсчитывается от нуля);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-155">where the **objective/target column** you want to predict (commonly called **'label'**) is the **column with index 1** (that is the second column, since the index is zero-based)</span></span>
    - <span data-ttu-id="dcdbc-156">**не использует заголовок файла** с именами столбцов, так как у этого конкретного файла набора данных нет заголовка;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-156">does **not use a file header** with column names since this particular dataset file doesn't have a header</span></span>
    - <span data-ttu-id="dcdbc-157">**целевое время изучения** в эксперименте составляет **10 секунд**.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-157">the **targeted exploration time** for the experiment is **10 seconds**</span></span>

    <span data-ttu-id="dcdbc-158">Вы увидите выходные данные CLI, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-158">You will see output from the CLI, similar to:</span></span>

    <!-- markdownlint-disable MD023 MD025 -->

    # <a name="windows"></a>[<span data-ttu-id="dcdbc-159">Windows</span><span class="sxs-lookup"><span data-stu-id="dcdbc-159">Windows</span></span>](#tab/windows)

    ![Автоматическое обучение с помощью ML.NET CL в PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-powershell.gif)

    # <a name="macos-bash"></a>[<span data-ttu-id="dcdbc-161">macOS Bash</span><span class="sxs-lookup"><span data-stu-id="dcdbc-161">macOS Bash</span></span>](#tab/macosbash)

    ![Автоматическое обучение с помощью ML.NET CL в PowerShell](./media/mlnet-cli/mlnet-auto-train-binary-classification-bash.gif)

    <span data-ttu-id="dcdbc-163">В данном случае, когда у средства CLI было всего 10 секунд и небольшой набор данных, ему удалось выполнить довольно много итераций, то есть провести обучение несколько раз на основе сочетаний различных алгоритмов или конфигурации с преобразованиями различных внутренних данных и гиперпараметров алгоритма.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-163">In this particular case, in only 10 seconds and with the small dataset provided, the CLI tool was able to run quite a few iterations, meaning training multiple times based on different combinations of algorithms/configuration with different internal data transformations and algorithm's hyper-parameters.</span></span>

    <span data-ttu-id="dcdbc-164">В итоге за 10 секунд найдена модель высшего качества с определенным алгоритмом обучения и конкретной конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-164">Finally, the "best quality" model found in 10 seconds is a model using a particular trainer/algorithm with any specific configuration.</span></span> <span data-ttu-id="dcdbc-165">В зависимости от времени изучения команда может выдать другой результат.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-165">Depending on the exploration time, the command can produce a different result.</span></span> <span data-ttu-id="dcdbc-166">Выбор производится с учетом нескольких отображаемых метрик, таких как `Accuracy`.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-166">The selection is based on the multiple metrics shown, such as `Accuracy`.</span></span>

    <span data-ttu-id="dcdbc-167">**Общие сведения о метриках качества модели**</span><span class="sxs-lookup"><span data-stu-id="dcdbc-167">**Understanding the model's quality metrics**</span></span>

    <span data-ttu-id="dcdbc-168">Первая и самая простая для понимания метрика оценки модели двоичной классификации — точность.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-168">The first and easiest metric to evaluate a binary-classification model is the accuracy, which is simple to understand.</span></span> <span data-ttu-id="dcdbc-169">"Точность — это доля правильных прогнозов на основе тестового набора данных".</span><span class="sxs-lookup"><span data-stu-id="dcdbc-169">"Accuracy is the proportion of correct predictions with a test data set.".</span></span> <span data-ttu-id="dcdbc-170">Чем ближе к 100 % (1,00), тем лучше.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-170">The closer to 100% (1.00), the better.</span></span>

    <span data-ttu-id="dcdbc-171">Однако бывают случаи, когда оценки с помощью одной метрики точности недостаточно, особенно если метка (0 и 1 в данном случае) несбалансирована в тестовом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-171">However, there are cases where just measuring with the Accuracy metric is not enough, especially when the label (0 and 1 in this case) is unbalanced in the test dataset.</span></span>

    <span data-ttu-id="dcdbc-172">Сведения о [дополнительных метриках и **подробные сведения о метриках** ML.NET (точность, AUC, AUCPR, F1-мера, которые используются для оценки различных моделей)](../resources/metrics.md).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-172">For additional metrics and more **detailed information about the metrics** such as Accuracy, AUC, AUCPR, and F1-score used to evaluate the different models, see [Understanding ML.NET metrics](../resources/metrics.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcdbc-173">Можно взять этот же набор данных и указать для `--max-exploration-time` несколько минут (например, три минуты или 180 секунд), и в результате вы получите модель еще лучшего качества с другой конфигурацией обучающего конвейера для этого набора данных (размером 1000 строк).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-173">You can try this very same dataset and specify a few minutes for `--max-exploration-time` (for instance three minutes so you specify 180 seconds) which will find a better "best model" for you with a different training pipeline configuration for this dataset (which is pretty small, 1000 rows).</span></span>

    <span data-ttu-id="dcdbc-174">Чтобы найти готовую для работы модель высшего или хорошего качества, предназначенную для крупных наборов данных, необходимо проводить эксперименты с помощью CLI, указывая более продолжительное время изучения в зависимости от размера набора данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-174">In order to find a "best/good quality" model that is a "production-ready model" targeting larger datasets, you should make experiments with the CLI usually specifying much more exploration time depending on the size of the dataset.</span></span> <span data-ttu-id="dcdbc-175">На самом деле во многих случаях может потребоваться несколько часов, особенно если речь идет о наборе данных с большим числом строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-175">In fact, in many cases you might require multiple hours of exploration time especially if the dataset is large on rows and columns.</span></span>

1. <span data-ttu-id="dcdbc-176">В результате выполнения предыдущей команды создаются следующие активы:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-176">The previous command execution has generated the following assets:</span></span>

    - <span data-ttu-id="dcdbc-177">готовый к использованию ZIP-файл сериализованной модели ("модели высшего качества");</span><span class="sxs-lookup"><span data-stu-id="dcdbc-177">A serialized model .zip ("best model") ready to use.</span></span>
    - <span data-ttu-id="dcdbc-178">код C# для запуска или оценки созданной модели (для прогнозирования в приложениях пользователей);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-178">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="dcdbc-179">обучающий код C#, используемый для создания этой модели (в целях обучения);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-179">C# training code used to generate that model (Learning purposes).</span></span>
    - <span data-ttu-id="dcdbc-180">файл журнала со всеми изученными итерациями, содержащими подробные сведения о каждом опробованном алгоритме с сочетанием его гиперпараметров и преобразований данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-180">A log file with all the iterations explored having specific detailed information about each algorithm tried with its combination of hyper-parameters and data transformations.</span></span>

    <span data-ttu-id="dcdbc-181">Первые два актива (ZIP-файл модели и код C# для запуска этой модели) можно использовать непосредственно в приложениях конечных пользователей (веб-приложениях и службах ASP.NET Core, классических приложениях и т. д.) для прогнозирования с помощью созданной модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-181">The first two assets (.ZIP file model and C# code to run that model) can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

    <span data-ttu-id="dcdbc-182">Третий актив, обучающий код, показывает, какой код ML.NET API использовало средство CLI для обучения созданной модели, поэтому можно определить, какой конкретный алгоритм обучения и гиперпараметры были выбраны средством CLI.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-182">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI.</span></span>

<span data-ttu-id="dcdbc-183">Эти активы ресурсы рассматриваются в следующих шагах руководства.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-183">Those enumerated assets are explained in the following steps of the tutorial.</span></span>

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a><span data-ttu-id="dcdbc-184">Изучение созданного кода C# для запуска модели прогнозирования</span><span class="sxs-lookup"><span data-stu-id="dcdbc-184">Explore the generated C# code to use for running the model to make predictions</span></span>

1. <span data-ttu-id="dcdbc-185">В Visual Studio (2017 или 2019) откройте созданное решение в папке `SampleBinaryClassification`, находящейся в исходной конечной папке (имя папки в учебнике — `/cli-test`).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-185">In Visual Studio (2017 or 2019) open the solution generated in the folder named `SampleBinaryClassification` within your original destination folder (in the tutorial was named `/cli-test`).</span></span> <span data-ttu-id="dcdbc-186">Вы увидите решение, аналогичное следующему:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-186">You should see a solution similar to:</span></span>

    > [!NOTE]
    > <span data-ttu-id="dcdbc-187">В этом руководстве рекомендуется использовать Visual Studio, но можно также изучить созданный код C# (два проекта) в любом текстовом редакторе и запустить созданное консольное приложение с помощью `dotnet CLI` на компьютерах с ОС macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-187">In the tutorial we suggest to use Visual Studio, but you can also explore the generated C# code (two projects) with any text editor and run the generated console app with the `dotnet CLI` on macOS, Linux or Windows machine.</span></span>

    ![Решение VS, созданное с помощью CLI](./media/mlnet-cli/generated-csharp-solution-detailed.png)

    - <span data-ttu-id="dcdbc-189">Созданную **библиотеку классов**, содержащую сериализованную модель машинного обучения (в ZiP-файле) и классы данных (модели данных), можно использовать непосредственно в приложениях конечных пользователей даже путем прямого указания на нее (или путем перемещения кода).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-189">The generated **class library** containing the serialized ML model (.zip file) and the data classes (data models) is something you can directly use in your end-user application, even by directly referencing that class library (or moving the code, as you prefer).</span></span>
    - <span data-ttu-id="dcdbc-190">Созданное **консольное приложение** содержит код выполнения, который нужно проверить, после чего можно многократно использовать код оценки (код, который запускает модель машинного обучения для прогнозирования), перемещая этот простой код (всего несколько строк) в приложения конечных пользователей для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-190">The generated **console app** contains execution code that you must review and then you usually reuse the 'scoring code' (code that runs the ML model to make predictions) by moving that simple code (just a few lines) to your end-user application where you want to make the predictions.</span></span>

1. <span data-ttu-id="dcdbc-191">Откройте файлы классов **ModelInput.cs** и **ModelOutput.cs** в проекте библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-191">Open the **ModelInput.cs** and **ModelOutput.cs** class files within the class library project.</span></span> <span data-ttu-id="dcdbc-192">Вы увидите, что это классы данных или классы POCO, используемые для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-192">You will see that these classes are 'data classes' or POCO classes used to hold data.</span></span> <span data-ttu-id="dcdbc-193">Это стереотипный код, который удобно использовать, если в наборе данных десятки или даже сотни столбцов.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-193">It is 'boilerplate code' but useful to have it generated if your dataset has tens or even hundreds of columns.</span></span>
    - <span data-ttu-id="dcdbc-194">Класс `ModelInput` используется при чтении данных из набора данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-194">The `ModelInput` class is used when reading data from the dataset.</span></span>
    - <span data-ttu-id="dcdbc-195">Класс `ModelOutput` используется для получения результата прогнозирования (данные прогнозирования).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-195">The `ModelOutput` class is used to get the prediction result (prediction data).</span></span>

1. <span data-ttu-id="dcdbc-196">Откройте файл Program.cs и изучите код.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-196">Open the Program.cs file and explore the code.</span></span> <span data-ttu-id="dcdbc-197">С помощью всего нескольких строк вы сможете запустить модель и создать пример прогноза.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-197">In just a few lines, you are able to run the model and make a sample prediction.</span></span>

    ```csharp
    static void Main(string[] args)
    {
        MLContext mlContext = new MLContext();

        // Training code used by ML.NET CLI and AutoML to generate the model
        //ModelBuilder.CreateModel();

        ITransformer mlModel = mlContext.Model.Load(MODEL_FILEPATH, out DataViewSchema inputSchema);
        var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // Create sample data to do a single prediction with it
        ModelInput sampleData = CreateSingleDataSample(mlContext, DATA_FILEPATH);

        // Try a single prediction
        ModelOutput predictionResult = predEngine.Predict(sampleData);

        Console.WriteLine($"Single Prediction --> Actual value: {sampleData.Label} | Predicted value: {predictionResult.Prediction}");
    }
    ```

    - <span data-ttu-id="dcdbc-198">Первая часть кода просто создает объект `MLContext`, необходимый при каждом выполнении кода ML.NET.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-198">The first line of code simply creates an `MLContext` object needed whenever you run ML.NET code.</span></span>

    - <span data-ttu-id="dcdbc-199">Вторая часть кода закомментирована, поскольку обучать модель не требуется, так как она уже обучена с помощью средства CLI и сохранена в сериализованном ZIP-файле модели.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-199">The second line of code is commented because you don't need to train the model since it was already trained for you by the CLI tool and saved into the model's serialized .ZIP file.</span></span> <span data-ttu-id="dcdbc-200">Но если вы хотите увидеть, *каким образом модель была обучена* с помощью CLI, нужно раскомментировать эту строку и запустить или отладить обучающий код, использованный для этой конкретной модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-200">But if you want to see *"how the model was trained"* by the CLI, you could uncomment that line and run/debug the training code used for that particular ML model.</span></span>

    - <span data-ttu-id="dcdbc-201">Третья строка кода используется для загрузки модели из сериализованного ZIP-файла с помощью API `mlContext.Model.Load()` с указанием пути к ZIP-файлу этой модели.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-201">In the third line of code, you load the model from the serialized model .ZIP file with the `mlContext.Model.Load()` API by providing the path to that model .ZIP file.</span></span>

    - <span data-ttu-id="dcdbc-202">Четвертая строка кода используется для создания объекта `PredictionEngine` с помощью API `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)`.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-202">In the fourth line of code you load create the `PredictionEngine` object with the `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)` API.</span></span> <span data-ttu-id="dcdbc-203">Объект `PredictionEngine` требуется всякий раз, когда нужно сделать прогноз на основе одного примера данных (в этом случае используется один фрагмент текста для прогнозирования его тональности).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-203">You need the `PredictionEngine` object whenever you want to make a prediction targeting a single sample of data (In this case, a single piece of text to predict its sentiment).</span></span>

    - <span data-ttu-id="dcdbc-204">Пятая строка кода используется для создания *одного примера данных*, который будет применяться для прогнозирования, путем вызова функции `CreateSingleDataSample()`.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-204">The fifth line of code is where you create that *single sample data* to be used for the prediction by calling the function `CreateSingleDataSample()`.</span></span> <span data-ttu-id="dcdbc-205">Так как средство CLI не знает, какого рода образцы данных нужно использовать, в этой функции, оно загрузит первую строку набора данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-205">Since the CLI tool doesn't know what kind of sample data to use, within that function it is loading the first row of the dataset.</span></span> <span data-ttu-id="dcdbc-206">Для этого случая можно также создать собственные жестко закодированные данные, а не пользоваться текущей реализацией функции `CreateSingleDataSample()` после обновления этого простого кода, реализующего функцию:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-206">However, for this case you can also create you own 'hard-coded' data instead of the current implementation of the `CreateSingleDataSample()` function by updating this simpler code implementing that function:</span></span>

        ```csharp
        private static ModelInput CreateSingleDataSample()
        {
            ModelInput sampleForPrediction = new ModelInput() { Col0 = "The ML.NET CLI is great for getting started. Very cool!", Label = true };
            return sampleForPrediction;
        }
        ```

1. <span data-ttu-id="dcdbc-207">Запустите проект с помощью исходного примера данных, загруженного из первой строки набора данных, или предоставьте пример собственных настраиваемых жестко закодированных данных.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-207">Run the project, either using the original sample data loaded from the first row of the dataset or by providing your own custom hard-coded sample data.</span></span> <span data-ttu-id="dcdbc-208">Вы должны получить прогноз, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-208">You should get a prediction comparable to:</span></span>

    # <a name="windows"></a>[<span data-ttu-id="dcdbc-209">Windows</span><span class="sxs-lookup"><span data-stu-id="dcdbc-209">Windows</span></span>](#tab/windows)

    <span data-ttu-id="dcdbc-210">Запустите консольное приложение из Visual Studio, нажав клавишу F5 (кнопку воспроизведения):</span><span class="sxs-lookup"><span data-stu-id="dcdbc-210">Run the console app from Visual Studio by hitting F5 (Play button):</span></span>

    ![Автоматическое обучение с помощью ML.NET CL в PowerShell](./media/mlnet-cli/sample-cli-prediction-execution.png)<span data-ttu-id="dcdbc-212">)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-212">)</span></span>

    # <a name="macos-bash"></a>[<span data-ttu-id="dcdbc-213">macOS Bash</span><span class="sxs-lookup"><span data-stu-id="dcdbc-213">macOS Bash</span></span>](#tab/macosbash)

    <span data-ttu-id="dcdbc-214">Запустите консольное приложение из командной строки, введя следующие команды:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-214">Run the console app from the command-prompt by typing the following commands:</span></span>

    ```dotnetcli
    cd SampleBinaryClassification
    cd SampleBinaryClassification.ConsoleApp

    dotnet run
    ```

    ![Автоматическое обучение с помощью ML.NET CL в PowerShell](./media/mlnet-cli/sample-cli-prediction-execution-bash.png)<span data-ttu-id="dcdbc-216">)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-216">)</span></span>

    ---

1. <span data-ttu-id="dcdbc-217">Попробуйте изменить пример жестко закодированных данных на другие предложения с различной тональностью и посмотрите, как модель прогнозирует положительную или отрицательную тональность.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-217">Try changing the hard-coded sample data to other sentences with different sentiment and see how the model predicts positive or negative sentiment.</span></span>

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a><span data-ttu-id="dcdbc-218">Внедрение приложений для конечных пользователей с прогнозами модели машинного обучения</span><span class="sxs-lookup"><span data-stu-id="dcdbc-218">Infuse your end-user applications with ML model predictions</span></span>

<span data-ttu-id="dcdbc-219">Запускать модель в приложении конечного пользователя и делать прогнозы можно с помощью аналогичного кода для оценки модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-219">You can use similar 'ML model scoring code' to run the model in your end-user application and make predictions.</span></span>

<span data-ttu-id="dcdbc-220">Например, этот код можно переместить прямо в классическое приложение Windows, такое как **WPF** и **WinForms**, и запустить модель так же, как в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-220">For instance, you could directly move that code to any Windows desktop application such as **WPF** and **WinForms** and run the model in the same way than it was done in the console app.</span></span>

<span data-ttu-id="dcdbc-221">Однако способ реализации этих строк кода для запуска модели машинного обучения необходимо оптимизировать (то есть кэшировать и один раз загрузить ZIP-файл модели) и использовать одноэлементные модели, а не создавать их при каждом запросе, особенно в том случае, если приложение (веб-приложение или распределенная служба) должно быть масштабируемым, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-221">However, the way you implement those lines of code to run an ML model should be optimized (that is, cache the model .zip file and load it once) and have singleton objects instead of creating them on every request, especially if your application needs to be scalable such as a web application or distributed service, as explained in the following section.</span></span>

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a><span data-ttu-id="dcdbc-222">Запуск моделей ML.NET в масштабируемых веб-приложениях и службах ASP.NET Core (многопоточных приложениях)</span><span class="sxs-lookup"><span data-stu-id="dcdbc-222">Running ML.NET models in scalable ASP.NET Core web apps and services (multi-threaded apps)</span></span>

<span data-ttu-id="dcdbc-223">Процесс создания объекта модели (объекта `ITransformer`, загруженного из ZIP-файла модели) и объекта `PredictionEngine` должен быть оптимизирован, особенно при запуске в масштабируемых веб-приложениях и распределенных службах.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-223">The creation of the model object (`ITransformer` loaded from a model's .zip file) and the `PredictionEngine` object should be optimized especially when running on scalable web apps and distributed services.</span></span> <span data-ttu-id="dcdbc-224">Оптимизация первого объекта модели (`ITransformer`) не вызывает трудностей.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-224">For the first case, the model object (`ITransformer`) the optimization is straightforward.</span></span> <span data-ttu-id="dcdbc-225">Так как объект `ITransformer` является потокобезопасным, его можно кэшировать как одноэлементный или статический, чтобы загружать модель всего один раз.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-225">Since the `ITransformer` object is thread-safe, you can cache the object as a singleton or static object so you load the model once.</span></span>

<span data-ttu-id="dcdbc-226">Для второго объекта `PredictionEngine` сделать это не так просто, поскольку объект `PredictionEngine` не является потокобезопасным и вы не можете создать его экземпляр в виде одноэлементного или статического объекта в приложении ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-226">For the second object, the `PredictionEngine` object, it is not so easy because the `PredictionEngine` object is not thread-safe, therefore you cannot instantiate this object as singleton or static object in an ASP.NET Core app.</span></span> <span data-ttu-id="dcdbc-227">Проблема потокобезопасности и масштабируемости подробно рассматривается в этой [публикации блога](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-227">This thread-safe and scalability problem is deeply discussed in this [Blog Post](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>

<span data-ttu-id="dcdbc-228">Но сейчас все стало намного проще.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-228">However, things got a lot easier for you than what's explained in that blog post.</span></span> <span data-ttu-id="dcdbc-229">Мы разработали упрощенный подход и создали отличный **пакет интеграции .NET Core** для использования в приложениях и службах ASP.NET Core. Его нужно зарегистрировать в службах внедрения зависимостей приложения и затем использовать напрямую из кода.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-229">We worked on a simpler approach for you and have created a nice **'.NET Core Integration Package'** that you can  easily use in your ASP.NET Core apps and services by registering it in the application DI services (Dependency Injection services) and then directly use it from your code.</span></span> <span data-ttu-id="dcdbc-230">См. инструкции в следующих руководствах и примерах:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-230">Check the following tutorial and example for doing that:</span></span>

- [<span data-ttu-id="dcdbc-231">Учебник. Запуск моделей ML.NET в масштабируемых веб-приложениях и веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcdbc-231">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="dcdbc-232">Пример. Масштабируемая модель ML.NET в веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcdbc-232">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a><span data-ttu-id="dcdbc-233">Изучение созданного кода C#, который использовался для модели высшего качества</span><span class="sxs-lookup"><span data-stu-id="dcdbc-233">Explore the generated C# code that was used to train the "best quality" model</span></span>

<span data-ttu-id="dcdbc-234">Для получения более глубоких знаний изучите созданный код C#, который использовался для обучения модели средством CLI.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-234">For more advanced learning purposes, you can also explore the generated C# code that was used by the CLI tool to train the generated model.</span></span>

<span data-ttu-id="dcdbc-235">Сейчас этот обучающий код модели создается в пользовательском классе с именем `ModelBuilder` и доступен для изучения.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-235">That 'training model code' is currently generated in the custom class generated named `ModelBuilder` so you can investigate that training code.</span></span>

<span data-ttu-id="dcdbc-236">Что еще более важно, можно сравнить созданный для этого конкретного сценария (модель анализа тональности) обучающий код с кодом, приведенным в следующем учебнике.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-236">More importantly, for this particular scenario (Sentiment Analysis model) you can also compare that generated training code with the code explained in the following tutorial:</span></span>

- <span data-ttu-id="dcdbc-237">Сравните: [Учебник. Использование ML.NET для анализа тональности методом двоичной классификации](sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-237">Compare: [Tutorial: Use ML.NET in a sentiment analysis binary classification scenario](sentiment-analysis.md).</span></span>

<span data-ttu-id="dcdbc-238">Будет интересно сравнить выбранный алгоритм и конфигурацию конвейера в этом руководстве с кодом, созданным с помощью средства CLI.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-238">It is interesting to compare the chosen algorithm and pipeline configuration in the tutorial with the code generated by the CLI tool.</span></span> <span data-ttu-id="dcdbc-239">В зависимости от продолжительности поиска оптимальных моделей вы можете выбрать особый алгоритм с собственными гиперпараметрами и конфигурацией конвейера.</span><span class="sxs-lookup"><span data-stu-id="dcdbc-239">Depending on how much time you spend iterating and searching for better models, the chosen algorithm might be different along with its particular hyper-parameters and pipeline configuration.</span></span>

<span data-ttu-id="dcdbc-240">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="dcdbc-240">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="dcdbc-241">подготовить данные для выбранной задачи машинного обучения (устраняемой проблемы);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-241">Prepare your data for the selected ML task (problem to solve)</span></span>
> - <span data-ttu-id="dcdbc-242">запустить команду mlnet auto-train в средстве CLI;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-242">Run the 'mlnet auto-train' command in the CLI tool</span></span>
> - <span data-ttu-id="dcdbc-243">просмотреть результаты показателей качества;</span><span class="sxs-lookup"><span data-stu-id="dcdbc-243">Review the quality metric results</span></span>
> - <span data-ttu-id="dcdbc-244">понять созданный код C# код для запуска модели (код, используемый в приложении конечных пользователей);</span><span class="sxs-lookup"><span data-stu-id="dcdbc-244">Understand the generated C# code to run the model (Code to use in your end-user app)</span></span>
> - <span data-ttu-id="dcdbc-245">изучить созданный код C#, который использовался для модели высшего качества (в целях обучения).</span><span class="sxs-lookup"><span data-stu-id="dcdbc-245">Explore the generated C# code that was used to train the "best quality" model (Learning purposes)</span></span>

## <a name="see-also"></a><span data-ttu-id="dcdbc-246">См. также</span><span class="sxs-lookup"><span data-stu-id="dcdbc-246">See also</span></span>

- [<span data-ttu-id="dcdbc-247">Автоматизация обучения модели с помощью интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="dcdbc-247">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="dcdbc-248">Учебник. Запуск моделей ML.NET в масштабируемых веб-приложениях и веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcdbc-248">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="dcdbc-249">Пример. Масштабируемая модель ML.NET в веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcdbc-249">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [<span data-ttu-id="dcdbc-250">Справочное руководство по команде auto-train в ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="dcdbc-250">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="dcdbc-251">Данные телеметрии в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="dcdbc-251">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
