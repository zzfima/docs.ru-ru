---
title: Справочник по командам интерфейса командной строки (CLI) ML.NET
description: Обзор, примеры и справочник по командам auto-train в программе командной строки ML.NET.
ms.date: 12/18/2019
ms.custom: mlnet-tooling
ms.openlocfilehash: bb161c596a76134876ee2bf0a6229bc551e0dad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848929"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="f2e1c-103">Справочник по командам интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="f2e1c-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="f2e1c-104">Команда `auto-train` — это основная команда, предоставляемая программой командной строки ML.NET.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="f2e1c-105">Она позволяет создать модель ML.NET хорошего качества, используя автоматизированное машинное обучение (AutoML), а также пример кода на C# для выполнения и оценки модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="f2e1c-106">Кроме того, код C# для обучения модели создается для изучения алгоритма и параметров модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="f2e1c-107">Этот раздел относится к ML.NET CLI и ML.NET AutoML, находящимся в данный момент в предварительной версии; материалы могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="f2e1c-108">Обзор</span><span class="sxs-lookup"><span data-stu-id="f2e1c-108">Overview</span></span>

<span data-ttu-id="f2e1c-109">Пример использования:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="f2e1c-110">Команда `mlnet auto-train` создает следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="f2e1c-111">готовый к использованию ZIP-файл сериализованной модели ("модели высшего качества");</span><span class="sxs-lookup"><span data-stu-id="f2e1c-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="f2e1c-112">код C# для выполнения или оценки созданной модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="f2e1c-113">код на C# с кодом обучения, используемый для создания этой модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="f2e1c-114">Первые два ресурса можно использовать непосредственно в приложениях конечных пользователей (веб-приложениях и службах ASP.NET Core, классических приложениях и т. д.) для прогнозирования с помощью созданной модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="f2e1c-115">Третий актив, код обучения, показывает, какой код API ML.NET использовало средство CLI для обучения созданной модели, поэтому можно определить конкретный алгоритм обучения и параметры модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="f2e1c-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="f2e1c-116">Examples</span></span>

<span data-ttu-id="f2e1c-117">Самый простой пример команды CLI для задачи бинарной классификации (ядро AutoML выведет большую часть параметров из предоставленных данных):</span><span class="sxs-lookup"><span data-stu-id="f2e1c-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="f2e1c-118">Другой простой пример команды интерфейса командной строки для решения задачи регрессии:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="f2e1c-119">Создание и обучение модели бинарной классификации с набором данных для обучения, проверочным набором данных и дальнейшей настройкой явных аргументов:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="f2e1c-120">Параметры команды</span><span class="sxs-lookup"><span data-stu-id="f2e1c-120">Command options</span></span>

<span data-ttu-id="f2e1c-121">`mlnet auto-train` обучает несколько моделей на основе предоставленного набора данных и наконец выбирает лучшую модель, сохраняет ее как сериализуемый ZIP-файл, а также создает связанный код на C# для оценки и обучения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="f2e1c-122">Недопустимые входные параметры приводят к тому, что средство CLI выдает список допустимых входных данных и сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="f2e1c-123">Задача</span><span class="sxs-lookup"><span data-stu-id="f2e1c-123">Task</span></span>

<span data-ttu-id="f2e1c-124">`--task | --mltask | -T` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="f2e1c-125">Одна строка, описывающая задачу машинного обучения для решения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="f2e1c-126">Например, это может быть любая из следующих задач (программа командной строки со временем будет поддерживать все задачи, поддерживаемые в AutoML):</span><span class="sxs-lookup"><span data-stu-id="f2e1c-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="f2e1c-127">`regression` — выберите, если модель машинного обучения будет использоваться для прогнозирования числовых значений.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="f2e1c-128">`binary-classification` — выберите, если результат модели машинного обучения имеет два возможных категориальных логических значения (0 или 1).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="f2e1c-129">`multiclass-classification` — выберите, если результат модели машинного обучения имеет несколько возможных категориальных значений.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="f2e1c-130">В этом аргументе должна указываться только одна задача машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="f2e1c-131">Набор данных</span><span class="sxs-lookup"><span data-stu-id="f2e1c-131">Dataset</span></span>

<span data-ttu-id="f2e1c-132">`--dataset | -d` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="f2e1c-133">Этот аргумент содержит путь к файлу в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="f2e1c-134">*А. Файл полного набора данных:* Если используется этот параметр и пользователь не задает `--test-dataset` и `--validation-dataset`, внутри для проверки модели используется кросс-валидация с K-сверткой или автоматизированное разделение данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="f2e1c-135">В этом случае пользователю будет достаточно указать путь к файлу набора данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="f2e1c-136">*Б. Файл набора данных для обучения:* Если пользователь также предоставляет наборы данных для валидации модели (с помощью `--test-dataset` и при необходимости `--validation-dataset`), то аргумент `--dataset` указывает лишь "набор данных для обучения".</span><span class="sxs-lookup"><span data-stu-id="f2e1c-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="f2e1c-137">Например при использовании подхода 80–20 % для валидации качества модели и получения показателей точности "набор данных для обучения" будет содержать 80 % данных, а на "проверочный набор данных" придется 20 % данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="f2e1c-138">Проверочный набор данных</span><span class="sxs-lookup"><span data-stu-id="f2e1c-138">Test dataset</span></span>

<span data-ttu-id="f2e1c-139">`--test-dataset | -t` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="f2e1c-140">Путь к файлу набора данных теста, например при использовании подхода 80–20 % при выполнении регулярных валидаций для получения показателей точности.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="f2e1c-141">При использовании `--test-dataset` параметр `--dataset` также является обязательным.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="f2e1c-142">Аргумент `--test-dataset` является необязательным, если только не используется --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="f2e1c-143">В этом случае пользователь должен использовать три аргумента.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="f2e1c-144">Набор данных для проверки</span><span class="sxs-lookup"><span data-stu-id="f2e1c-144">Validation dataset</span></span>

<span data-ttu-id="f2e1c-145">`--validation-dataset | -v` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="f2e1c-146">Путь к файлу валидационного набора данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="f2e1c-147">В любом случае валидационный набор данных является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="f2e1c-148">При использовании `validation dataset` должно быть следующее поведение:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="f2e1c-149">Аргументы `test-dataset` и `--dataset` также являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="f2e1c-150">Набор данных `validation-dataset` используется для оценки ошибки прогноза для выбора модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="f2e1c-151">`test-dataset` используется для оценки ошибки обобщения конечной выбранной модели.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="f2e1c-152">В идеале проверочный набор должен храниться в "хранилище" и добавляться только в конце анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="f2e1c-153">Обычно при использовании `validation dataset` с `test dataset` этап валидации состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="f2e1c-154">В первой части вы просто смотрите на модели и выбираете наиболее эффективный подход с использованием проверочных данных (=валидация).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="f2e1c-155">Затем можно оценить точность выбранного подхода (= проверка).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="f2e1c-156">Таким образом, разделение данных может быть задано как 80-10-10 или 75-15-10.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="f2e1c-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-157">For example:</span></span>

- <span data-ttu-id="f2e1c-158">Файл `training-dataset` должен содержать 75 % данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="f2e1c-159">Файл `validation-dataset` должен содержать 15 % данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="f2e1c-160">Файл `test-dataset` должен содержать 10 % данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="f2e1c-161">В любом случае эти проценты выбираются с помощью интерфейса командной строки, который будет предоставлять уже разделенные файлы.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="f2e1c-162">Надпись "имя столбца"</span><span class="sxs-lookup"><span data-stu-id="f2e1c-162">Label column name</span></span>

<span data-ttu-id="f2e1c-163">`--label-column-name | -n` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="f2e1c-164">С помощью этого аргумента можно указать определенную цель и целевой столбец (переменную, которую необходимо прогнозировать), используя имя столбца в заголовке набора данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="f2e1c-165">Этот аргумент используется только для контролируемых задач машинного обучения, таких как *задачи классификации*.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="f2e1c-166">Он не может использоваться для задач машинного обучения без учителя, например *кластеризации*.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="f2e1c-167">Надпись "индекс столбца"</span><span class="sxs-lookup"><span data-stu-id="f2e1c-167">Label column index</span></span>

<span data-ttu-id="f2e1c-168">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="f2e1c-169">С помощью этого аргумента можно задать определенную цель и целевой столбца (переменную, которую требуется спрогнозировать) с помощью числового индекса столбца в файле набора данных (значения индексов столбцов начинаются с 1).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="f2e1c-170">*Примечание.* Если пользователь также задал `--label-column-name`, используется `--label-column-name`.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="f2e1c-171">Этот аргумент используется только для контролируемых задач машинного обучения, таких как *задачи классификации*.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="f2e1c-172">Он не может использоваться для задач машинного обучения без учителя, например *кластеризации*.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="f2e1c-173">Игнорировать столбцы</span><span class="sxs-lookup"><span data-stu-id="f2e1c-173">Ignore columns</span></span>

<span data-ttu-id="f2e1c-174">`--ignore-columns | -I` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="f2e1c-175">С помощью этого аргумента можно игнорировать существующие столбцы в файле набора данных; они не загружаются и не используются процессами обучения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="f2e1c-176">Укажите имена столбцов, которые требуется игнорировать.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="f2e1c-177">Используйте ", " (запятая с пробелом) или " " (пробел) для разделения нескольких имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="f2e1c-178">Можно использовать кавычки для имен столбцов, содержащих пробелы (например, "Вход в систему").</span><span class="sxs-lookup"><span data-stu-id="f2e1c-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="f2e1c-179">Пример.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="f2e1c-180">Имеет заголовок</span><span class="sxs-lookup"><span data-stu-id="f2e1c-180">Has header</span></span>

<span data-ttu-id="f2e1c-181">`--has-header | -h` (логическое значение)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="f2e1c-182">Укажите, содержат ли файлы набора данных строку заголовка.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="f2e1c-183">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="f2e1c-184">По умолчанию значение равно `true`, если этот аргумент не задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="f2e1c-185">Чтобы использовать аргумент `--label-column-name`, необходимо указать заголовок в файле набора данных и задать `--has-header` как `true` (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="f2e1c-186">Максимальное время исследования</span><span class="sxs-lookup"><span data-stu-id="f2e1c-186">Max exploration time</span></span>

<span data-ttu-id="f2e1c-187">`--max-exploration-time | -x` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="f2e1c-188">По умолчанию максимальное время исследования составляет 30 минут.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="f2e1c-189">Этот аргумент задает максимальное время (в секундах) для процесса изучения различных учителей и конфигураций.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="f2e1c-190">Заданное время может быть превышено, если указанное время слишком мало (скажем, 2 секунды) для одной итерации.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="f2e1c-191">В этом случае фактическое время — это время, необходимое для создания одной модели конфигурации в одной итерации.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="f2e1c-192">Требуемое время для итераций зависит от размера набора данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="f2e1c-193">Кэш</span><span class="sxs-lookup"><span data-stu-id="f2e1c-193">Cache</span></span>

<span data-ttu-id="f2e1c-194">`--cache | -c` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="f2e1c-195">При использовании кэширования весь обучающий набор данных будет загружен в память.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="f2e1c-196">Для малых и средних наборов данных с помощью кэша можно существенно улучшить производительность обучения; это означает, что время обучения может быть короче, чем в ситуации, если кэш не используется.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="f2e1c-197">Тем не менее на большие наборы данных загрузка всех данных в память может повлиять отрицательно, так как может возникнуть нехватка памяти.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="f2e1c-198">В случае обучения с большими файлами набора данных без использования кэша ML.NET будет потоком передавать блоки данных с диска при необходимости загрузить дополнительные данные во время обучения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="f2e1c-199">Можно указать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-199">You can specify the following values:</span></span>

<span data-ttu-id="f2e1c-200">`on`. принудительно включает кэш при обучении;</span><span class="sxs-lookup"><span data-stu-id="f2e1c-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="f2e1c-201">`off`. принудительно отключает кэш при обучении;</span><span class="sxs-lookup"><span data-stu-id="f2e1c-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="f2e1c-202">`auto`. кэш будет использоваться в зависимости от эвристики AutoML.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="f2e1c-203">Как правило, для небольших и средних наборов данных будет использоваться кэш; большие наборы данных не будут использовать кэш, если вы укажете `auto`.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="f2e1c-204">Если вы не укажете параметр `--cache`, то для кэша `auto` будет использована конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="f2e1c-205">name</span><span class="sxs-lookup"><span data-stu-id="f2e1c-205">Name</span></span>

<span data-ttu-id="f2e1c-206">`--name | -N` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-206">`--name | -N` (string)</span></span>

<span data-ttu-id="f2e1c-207">Имя для создаваемых выходных проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-207">The name for the created output project or solution.</span></span> <span data-ttu-id="f2e1c-208">Если имя не задано, используется имя `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="f2e1c-209">Файл модели ML.NET (ZIP-файл) получит то же имя.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="f2e1c-210">Путь для создаваемых файлов</span><span class="sxs-lookup"><span data-stu-id="f2e1c-210">Output path</span></span>

<span data-ttu-id="f2e1c-211">`--output-path | -o` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="f2e1c-212">Корневое расположение или папка для размещения созданных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="f2e1c-213">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="f2e1c-214">Уровень детализации</span><span class="sxs-lookup"><span data-stu-id="f2e1c-214">Verbosity</span></span>

<span data-ttu-id="f2e1c-215">`--verbosity | -V` (строка)</span><span class="sxs-lookup"><span data-stu-id="f2e1c-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="f2e1c-216">Задает уровень детализации стандартных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="f2e1c-217">Допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="f2e1c-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="f2e1c-218">`m[inimal]` (по умолчанию);</span><span class="sxs-lookup"><span data-stu-id="f2e1c-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="f2e1c-219">`diag[nostic]` (уровень ведения журнала).</span><span class="sxs-lookup"><span data-stu-id="f2e1c-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="f2e1c-220">По умолчанию программа командной строки должна отображать минимальные выходные данные во время работы, например отметить, что она работает и (по возможности) сколько времени уйдет на завершение работы.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="f2e1c-221">Справка</span><span class="sxs-lookup"><span data-stu-id="f2e1c-221">Help</span></span>

`-h|--help`

<span data-ttu-id="f2e1c-222">Выводит справку для команды с описанием каждого аргумента.</span><span class="sxs-lookup"><span data-stu-id="f2e1c-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2e1c-223">См. также</span><span class="sxs-lookup"><span data-stu-id="f2e1c-223">See also</span></span>

- [<span data-ttu-id="f2e1c-224">Установка интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="f2e1c-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="f2e1c-225">Общие сведения о ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="f2e1c-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="f2e1c-226">Учебник. Анализ тональности с помощью интерфейса командной строки (CLI) ML.NET</span><span class="sxs-lookup"><span data-stu-id="f2e1c-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="f2e1c-227">Данные телеметрии в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="f2e1c-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
