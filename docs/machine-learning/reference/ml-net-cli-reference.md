---
title: Команда auto-train в программе командной строки ML.NET
description: Обзор, примеры и справочник по командам auto-train в программе командной строки ML.NET.
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: ce5994f392c492e80676b9e65ce54fe010cf03ab
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722601"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="16078-103">Команда auto-train в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="16078-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="16078-104">Этот раздел относится к ML.NET CLI и ML.NET AutoML, находящимся в данный момент в предварительной версии; материалы могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="16078-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="16078-105">Команда `auto-train` — это основная команда, предоставляемая программой командной строки ML.NET.</span><span class="sxs-lookup"><span data-stu-id="16078-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="16078-106">Она позволяет создать модель ML.NET хорошего качества (сериализованную модель в ZIP-файле) и пример кода на C# для выполнения и оценки модели.</span><span class="sxs-lookup"><span data-stu-id="16078-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="16078-107">Кроме того, создается код на C#, чтобы создать и обучить эту модель, позволяющий выяснить, какой алгоритм и параметры система обучения использует для создания этой "наилучшей модели".</span><span class="sxs-lookup"><span data-stu-id="16078-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="16078-108">Вы можете создать эти ресурсы из собственных наборов данных без самостоятельного написания кода, что также повышает производительность вашего труда, даже если вы уже знакомы с ML.NET.</span><span class="sxs-lookup"><span data-stu-id="16078-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="16078-109">Сейчас ML.NET CLI поддерживает следующие задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="16078-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="16078-110">Будущее: Другие задачи машинного обучения, такие как</span><span class="sxs-lookup"><span data-stu-id="16078-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="16078-111">Пример использования в командной строке:</span><span class="sxs-lookup"><span data-stu-id="16078-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="16078-112">Команда `mlnet auto-train` создает следующие ресурсы:</span><span class="sxs-lookup"><span data-stu-id="16078-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="16078-113">готовый к использованию ZIP-файл сериализованной модели ("модели высшего качества");</span><span class="sxs-lookup"><span data-stu-id="16078-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="16078-114">код C# для запуска или оценки созданной модели (для прогнозирования в приложениях пользователей);</span><span class="sxs-lookup"><span data-stu-id="16078-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="16078-115">код на C# с кодом обучения, используемый для создания этой модели (в целях обучения).</span><span class="sxs-lookup"><span data-stu-id="16078-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="16078-116">Первые два ресурса можно использовать непосредственно в приложениях конечных пользователей (веб-приложениях и службах ASP.NET Core, классических приложениях и т. д.) для прогнозирования с помощью созданной модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="16078-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="16078-117">Третий ресурс, код обучения, рассказывает о том, какой код ML.NET API использовался интерфейсом командной строки для обучения в формируемой модели, поэтому можно выяснить, какой конкретный алгоритм обучения и гиперпараметры были выбраны программой командной строки и подсистемой ML.NET AutoML.</span><span class="sxs-lookup"><span data-stu-id="16078-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-paramenters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="16078-118">Команда auto-train использует ядро AutoML</span><span class="sxs-lookup"><span data-stu-id="16078-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="16078-119">Интерфейс командной строки использует ядро ML.NET AutoML (пакет NuGet) для интеллектуального поиска оптимальной модели, как показано на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="16078-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="16078-120">![изображение](./media/ml-net-automl-working-diagram.png "Ядро AutoML, работающее в программе командной строки ML.NET")</span><span class="sxs-lookup"><span data-stu-id="16078-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="16078-121">При запуске программы командной строки ML.NET с командой auto-train вы увидите, что она проходит множество итераций с сочетаниями различных алгоритмов и конфигураций.</span><span class="sxs-lookup"><span data-stu-id="16078-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="16078-122">Справочник по команде auto-train</span><span class="sxs-lookup"><span data-stu-id="16078-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="16078-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="16078-123">Examples</span></span>

<span data-ttu-id="16078-124">Самый простой пример команды CLI для задачи бинарной классификации (ядро AutoML должно вывести большую часть параметров из предоставленных данных):</span><span class="sxs-lookup"><span data-stu-id="16078-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="16078-125">Другой простой пример команды интерфейса командной строки для решения задачи регрессии:</span><span class="sxs-lookup"><span data-stu-id="16078-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="16078-126">Создание и обучение модели бинарной классификации с набором данных для обучения, проверочным набором данных и дальнейшей настройкой явных аргументов:</span><span class="sxs-lookup"><span data-stu-id="16078-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="16078-127">name</span><span class="sxs-lookup"><span data-stu-id="16078-127">Name</span></span>

<span data-ttu-id="16078-128">`mlnet auto-train` — обучает несколько моделей (n итераций) на основе предоставленного набора данных и наконец выбирает лучшую модель, сохраняет ее как сериализуемый ZIP-файл, а также создает связанный код на C# для оценки и обучения.</span><span class="sxs-lookup"><span data-stu-id="16078-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="16078-129">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="16078-129">Synopsis</span></span>

```console
> mlnet auto-train

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

<span data-ttu-id="16078-130">Недопустимые входные параметры должны заставлять программу командной строки перечислять допустимые входные данные и выводить сообщение об ошибке, объясняющее, какой аргумент отсутствует, если это так.</span><span class="sxs-lookup"><span data-stu-id="16078-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="16078-131">Параметры</span><span class="sxs-lookup"><span data-stu-id="16078-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="16078-132">`--task | --mltask | -T` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="16078-133">Одна строка, описывающая задачу машинного обучения для решения.</span><span class="sxs-lookup"><span data-stu-id="16078-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="16078-134">Например, это может быть любая из следующих задач (программа командной строки со временем будет поддерживать все задачи, поддерживаемые в AutoML):</span><span class="sxs-lookup"><span data-stu-id="16078-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="16078-135">`regression` — выберите, если модель машинного обучения будет использоваться для прогнозирования числовых значений.</span><span class="sxs-lookup"><span data-stu-id="16078-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="16078-136">`binary-classification` — выберите, если результат модели машинного обучения имеет два возможных категориальных логических значения (0 или 1).</span><span class="sxs-lookup"><span data-stu-id="16078-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="16078-137">`multiclass-classification` — выберите, если результат модели машинного обучения имеет несколько возможных категориальных значений.</span><span class="sxs-lookup"><span data-stu-id="16078-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="16078-138">В будущих выпусках будут поддерживаться дополнительные задачи машинного обучения и сценарии, например `recommendations`, `clustering` и `ranking`.</span><span class="sxs-lookup"><span data-stu-id="16078-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="16078-139">В этом аргументе должна указываться только одна задача машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="16078-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="16078-140">`--dataset | -d` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="16078-141">Этот аргумент содержит путь к файлу в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="16078-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="16078-142">*А. Файл полного набора данных:* Если используется этот параметр и пользователь не задает `--test-dataset` и `--validation-dataset`, внутри для проверки модели используется кросс-валидация с K-сверткой или автоматизированное разделение данных.</span><span class="sxs-lookup"><span data-stu-id="16078-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="16078-143">В этом случае пользователю будет достаточно указать путь к файлу набора данных.</span><span class="sxs-lookup"><span data-stu-id="16078-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="16078-144">*Б. Файл набора данных для обучения:* Если пользователь также предоставляет наборы данных для валидации модели (с помощью `--test-dataset` и при необходимости `--validation-dataset`), то аргумент `--dataset` указывает лишь "набор данных для обучения".</span><span class="sxs-lookup"><span data-stu-id="16078-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="16078-145">Например при использовании подхода 80–20 % для валидации качества модели и получения показателей точности "набор данных для обучения" будет содержать 80 % данных, а на "проверочный набор данных" придется 20 % данных.</span><span class="sxs-lookup"><span data-stu-id="16078-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-146">`--test-dataset | -t` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="16078-147">Путь к файлу набора данных теста, например при использовании подхода 80–20 % при выполнении регулярных валидаций для получения показателей точности.</span><span class="sxs-lookup"><span data-stu-id="16078-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="16078-148">При использовании `--test-dataset` параметр `--dataset` также является обязательным.</span><span class="sxs-lookup"><span data-stu-id="16078-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="16078-149">Аргумент `--test-dataset` является необязательным, если только не используется --validation-dataset.</span><span class="sxs-lookup"><span data-stu-id="16078-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="16078-150">В этом случае пользователь должен использовать три аргумента.</span><span class="sxs-lookup"><span data-stu-id="16078-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-151">`--validation-dataset | -v` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="16078-152">Путь к файлу валидационного набора данных.</span><span class="sxs-lookup"><span data-stu-id="16078-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="16078-153">В любом случае валидационный набор данных является необязательным.</span><span class="sxs-lookup"><span data-stu-id="16078-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="16078-154">При использовании `validation dataset` должно быть следующее поведение:</span><span class="sxs-lookup"><span data-stu-id="16078-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="16078-155">Аргументы `test-dataset` и `--dataset` также являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="16078-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="16078-156">Набор данных `validation-dataset` используется для оценки ошибки прогноза для выбора модели.</span><span class="sxs-lookup"><span data-stu-id="16078-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="16078-157">`test-dataset` используется для оценки ошибки обобщения конечной выбранной модели.</span><span class="sxs-lookup"><span data-stu-id="16078-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="16078-158">В идеале проверочный набор должен храниться в "хранилище" и добавляться только в конце анализа данных.</span><span class="sxs-lookup"><span data-stu-id="16078-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="16078-159">Обычно при использовании `validation dataset` с `test dataset` этап валидации состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="16078-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="16078-160">В первой части вы просто смотрите на модели и выбираете наиболее эффективный подход с использованием проверочных данных (=валидация).</span><span class="sxs-lookup"><span data-stu-id="16078-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="16078-161">Затем можно оценить точность выбранного подхода (= проверка).</span><span class="sxs-lookup"><span data-stu-id="16078-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="16078-162">Таким образом, разделение данных может быть задано как 80-10-10 или 75-15-10.</span><span class="sxs-lookup"><span data-stu-id="16078-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="16078-163">Например:</span><span class="sxs-lookup"><span data-stu-id="16078-163">For example:</span></span>

- <span data-ttu-id="16078-164">Файл `training-dataset` должен содержать 75 % данных.</span><span class="sxs-lookup"><span data-stu-id="16078-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="16078-165">Файл `validation-dataset` должен содержать 15 % данных.</span><span class="sxs-lookup"><span data-stu-id="16078-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="16078-166">Файл `test-dataset` должен содержать 10 % данных.</span><span class="sxs-lookup"><span data-stu-id="16078-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="16078-167">В любом случае эти проценты выбираются с помощью интерфейса командной строки, который будет предоставлять уже разделенные файлы.</span><span class="sxs-lookup"><span data-stu-id="16078-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-168">`--label-column-name | -n` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="16078-169">С помощью этого аргумента можно указать определенную цель и целевой столбец (переменную, которую необходимо прогнозировать), используя имя столбца в заголовке набора данных.</span><span class="sxs-lookup"><span data-stu-id="16078-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="16078-170">Этот аргумент используется только для контролируемых задач машинного обучения, таких как *задачи классификации*.</span><span class="sxs-lookup"><span data-stu-id="16078-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="16078-171">Он не может использоваться для задач машинного обучения без учителя, например *кластеризации*.</span><span class="sxs-lookup"><span data-stu-id="16078-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-172">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="16078-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="16078-173">С помощью этого аргумента можно задать определенную цель и целевой столбца (переменную, которую требуется спрогнозировать) с помощью числового индекса столбца в файле набора данных (значения индексов столбцов начинаются с 1).</span><span class="sxs-lookup"><span data-stu-id="16078-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="16078-174">*Примечание.* Если пользователь также задал `--label-column-name`, используется `--label-column-name`.</span><span class="sxs-lookup"><span data-stu-id="16078-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="16078-175">Этот аргумент используется только для контролируемых задач машинного обучения, таких как *задачи классификации*.</span><span class="sxs-lookup"><span data-stu-id="16078-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="16078-176">Он не может использоваться для задач машинного обучения без учителя, например *кластеризации*.</span><span class="sxs-lookup"><span data-stu-id="16078-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-177">`--ignore-columns | -I` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="16078-178">С помощью этого аргумента можно игнорировать существующие столбцы в файле набора данных; они не загружаются и не используются процессами обучения.</span><span class="sxs-lookup"><span data-stu-id="16078-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="16078-179">Укажите имена столбцов, которые требуется игнорировать.</span><span class="sxs-lookup"><span data-stu-id="16078-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="16078-180">Используйте ", " (запятая с пробелом) или " " (пробел) для разделения нескольких имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="16078-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="16078-181">Можно использовать кавычки для имен столбцов, содержащих пробелы (например, "Вход в систему").</span><span class="sxs-lookup"><span data-stu-id="16078-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="16078-182">Пример</span><span class="sxs-lookup"><span data-stu-id="16078-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="16078-183">`--has-header | -h` (логическое значение)</span><span class="sxs-lookup"><span data-stu-id="16078-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="16078-184">Укажите, содержат ли файлы набора данных строку заголовка.</span><span class="sxs-lookup"><span data-stu-id="16078-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="16078-185">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="16078-185">Possible values are:</span></span>
- `true`
- `false`

<span data-ttu-id="16078-186">По умолчанию значение равно `true`, если этот аргумент не задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="16078-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="16078-187">Чтобы использовать аргумент `--label-column-name`, необходимо указать заголовок в файле набора данных и задать `--has-header` как `true` (используется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="16078-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-188">`--max-exploration-time | -x` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="16078-189">По умолчанию максимальное время исследования составляет 30 минут.</span><span class="sxs-lookup"><span data-stu-id="16078-189">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="16078-190">Этот аргумент задает максимальное время (в секундах) для процесса изучения различных учителей и конфигураций.</span><span class="sxs-lookup"><span data-stu-id="16078-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="16078-191">Заданное время может быть превышено, если указанное время слишком мало (скажем, 2 секунды) для одной итерации.</span><span class="sxs-lookup"><span data-stu-id="16078-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="16078-192">В этом случае фактическое время — это время, необходимое для создания одной модели конфигурации в одной итерации.</span><span class="sxs-lookup"><span data-stu-id="16078-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="16078-193">Требуемое время для итераций зависит от размера набора данных.</span><span class="sxs-lookup"><span data-stu-id="16078-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-194">`--cache | -c` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="16078-195">При использовании кэширования весь обучающий набор данных будет загружен в память.</span><span class="sxs-lookup"><span data-stu-id="16078-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="16078-196">Для малых и средних наборов данных с помощью кэша можно существенно улучшить производительность обучения; это означает, что время обучения может быть короче, чем в ситуации, если кэш не используется.</span><span class="sxs-lookup"><span data-stu-id="16078-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="16078-197">Тем не менее на большие наборы данных загрузка всех данных в память может повлиять отрицательно, так как может возникнуть нехватка памяти.</span><span class="sxs-lookup"><span data-stu-id="16078-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="16078-198">В случае обучения с большими файлами набора данных без использования кэша ML.NET будет потоком передавать блоки данных с диска при необходимости загрузить дополнительные данные во время обучения.</span><span class="sxs-lookup"><span data-stu-id="16078-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="16078-199">Можно указать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="16078-199">You can specify the following values:</span></span>

<span data-ttu-id="16078-200">`on`: принудительно включает кэш при обучении;</span><span class="sxs-lookup"><span data-stu-id="16078-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="16078-201">`off`: принудительно отключает кэш при обучении;</span><span class="sxs-lookup"><span data-stu-id="16078-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="16078-202">`auto`: кэш будет использоваться в зависимости от эвристики AutoML.</span><span class="sxs-lookup"><span data-stu-id="16078-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="16078-203">Как правило, для небольших и средних наборов данных будет использоваться кэш; большие наборы данных не будут использовать кэш, если вы укажете `auto`.</span><span class="sxs-lookup"><span data-stu-id="16078-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="16078-204">Если вы не укажете параметр `--cache`, то для кэша `auto` будет использована конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16078-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-205">`--name | -N` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-205">`--name | -N` (string)</span></span>

<span data-ttu-id="16078-206">Имя для создаваемых выходных проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="16078-206">The name for the created output project or solution.</span></span> <span data-ttu-id="16078-207">Если имя не задано, используется имя `sample-{mltask}`.</span><span class="sxs-lookup"><span data-stu-id="16078-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="16078-208">Файл модели ML.NET (ZIP-файл) получит то же имя.</span><span class="sxs-lookup"><span data-stu-id="16078-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-209">`--output-path | -o` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="16078-210">Корневое расположение или папка для размещения созданных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="16078-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="16078-211">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="16078-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="16078-212">`--verbosity | -V` (строка)</span><span class="sxs-lookup"><span data-stu-id="16078-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="16078-213">Задает уровень детализации стандартных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="16078-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="16078-214">Допустимыми значениями являются:</span><span class="sxs-lookup"><span data-stu-id="16078-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="16078-215">`m[inimal]` (по умолчанию);</span><span class="sxs-lookup"><span data-stu-id="16078-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="16078-216">`diag[nostic]` (уровень ведения журнала).</span><span class="sxs-lookup"><span data-stu-id="16078-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="16078-217">По умолчанию программа командной строки должна отображать минимальные выходные данные во время работы, например отметить, что она работает и (по возможности) сколько времени уйдет на завершение работы.</span><span class="sxs-lookup"><span data-stu-id="16078-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="16078-218">Выводит справку для команды с описанием каждого аргумента.</span><span class="sxs-lookup"><span data-stu-id="16078-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="16078-219">См. также</span><span class="sxs-lookup"><span data-stu-id="16078-219">See also</span></span>

- [<span data-ttu-id="16078-220">Установка интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="16078-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="16078-221">Автоматизация обучения модели с помощью интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="16078-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="16078-222">Учебник. Автоматическое создание бинарного классификатора с помощью интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="16078-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="16078-223">Данные телеметрии в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="16078-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
