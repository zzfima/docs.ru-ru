---
title: Автоматизация обучения модели с помощью ML.NET CLI
description: Сведения о том, как использовать средство ML.NET CLI для автоматического обучения оптимальной модели из командной строки.
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: 33383582140d9df4290a0bbf30659301af837d1d
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065897"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="7f4c3-103">Автоматизация обучения модели с помощью ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="7f4c3-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="7f4c3-104">ML.NET CLI упрощает задачу изучения ML.NET для разработчиков .NET.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-104">The ML.NET CLI "democratizes" ML.NET for .NET developers when learning ML.NET.</span></span>

<span data-ttu-id="7f4c3-105">Чтобы использовать ML.NET API сам по себе (без ML.NET AutoML CLI), вам нужно выбрать алгоритм обучения (реализация алгоритма машинного обучения для конкретной задачи) и набор преобразований данных (конструирование признаков), применяемые к вашим данным.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="7f4c3-106">Оптимальный конвейер индивидуален для каждого набора данных, а выбор оптимального алгоритма из всех возможных вариантов только усложняет задачу.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="7f4c3-107">Кроме того, каждый алгоритм имеет набор настраиваемых гиперпараметров.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="7f4c3-108">Таким образом, вы можете потратить недели (а иногда и месяцы) на оптимизацию модели машинного обучения, пытаясь найти лучшие сочетания конструирования признаков, алгоритмов обучения и гиперпараметров.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="7f4c3-109">Этот процесс можно автоматизировать с помощью средства ML.NET CLI, которое реализует интеллектуальную подсистему ML.NET AutoML.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-109">This process can be automated with the ML.NET CLI, which implements the ML.NET AutoML intelligent engine.</span></span> 

> [!NOTE]
> <span data-ttu-id="7f4c3-110">В этом разделе описано, как использовать средства ML.NET **CLI** и ML.NET **AutoML**, которые сейчас находятся на этапе предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span> 

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="7f4c3-111">Что такое интерфейс командной строки ML.NET CLI?</span><span class="sxs-lookup"><span data-stu-id="7f4c3-111">What is the ML.NET Command-line Interface (CLI)?</span></span>

<span data-ttu-id="7f4c3-112">Вы можете запустить ML.NET CLI в любой командной строке (Windows, Mac или Linux), чтобы создать качественные модели и исходный код ML.NET на основе наборов данных для обучения.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-112">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on your training dataset.</span></span>

<span data-ttu-id="7f4c3-113">Как показано на рисунке ниже, можно легко создать высококачественную модель ML.NET (ZIP-файл сериализованной модели), а также пример кода C# для запуска и оценки этой модели.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-113">As shown in the figure below, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="7f4c3-114">Кроме того, создается код C# для создания и обучения этой модели, поэтому вы можете исследовать алгоритм и параметры, используемые для созданной "оптимальной модели", и выполнять итерацию по ним.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-114">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span> 

<span data-ttu-id="7f4c3-115">![изображение](media/automate-training-with-cli/cli-high-level-process.png "Ядро AutoML, работающее в программе командной строки ML.NET")</span><span class="sxs-lookup"><span data-stu-id="7f4c3-115">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="7f4c3-116">Вы можете создать эти ресурсы из собственных наборов данных без самостоятельного написания кода, что также повышает производительность вашего труда, даже если вы уже знакомы с ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-116">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="7f4c3-117">Сейчас ML.NET CLI поддерживает следующие задачи машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="7f4c3-117">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification` 
- `regression`
- <span data-ttu-id="7f4c3-118">Планы на будущее: другие задачи машинного обучения, например `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span><span class="sxs-lookup"><span data-stu-id="7f4c3-118">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="7f4c3-119">Пример использования:</span><span class="sxs-lookup"><span data-stu-id="7f4c3-119">Example of usage:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![изображение](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="7f4c3-121">Его можно схожим образом запустить в *Windows PowerShell*, \*macOS/Linux bash или *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-121">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="7f4c3-122">Однако функция табличного автозавершения (предложения параметров) не будет работать в *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-122">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="7f4c3-123">Созданные выходные ресурсы</span><span class="sxs-lookup"><span data-stu-id="7f4c3-123">Output assets generated</span></span>

<span data-ttu-id="7f4c3-124">Команда `auto-train` CLI создает следующие ресурсы в выходной папке:</span><span class="sxs-lookup"><span data-stu-id="7f4c3-124">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="7f4c3-125">Готовый к использованию ZIP-файл сериализованной модели ("оптимальной модели") для выполнения прогнозов.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-125">A serialized model .zip ("best model") ready to use for running predictions.</span></span> 
- <span data-ttu-id="7f4c3-126">Решение C#, включающее в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="7f4c3-126">C# solution with:</span></span>
    - <span data-ttu-id="7f4c3-127">код C# для запуска или оценки созданной модели (для прогнозирования в приложениях пользователей);</span><span class="sxs-lookup"><span data-stu-id="7f4c3-127">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="7f4c3-128">обучающий код C#, используемый для создания этой модели (в учебных целях или для переобучения модели).</span><span class="sxs-lookup"><span data-stu-id="7f4c3-128">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="7f4c3-129">Файл журнала с информацией обо всех итерациях/проходах по нескольким оцениваемым алгоритмам, включая их подробную конфигурацию или конвейер.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-129">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="7f4c3-130">Первые два ресурса можно использовать непосредственно в приложениях конечных пользователей (веб-приложениях и службах ASP.NET Core, классических приложениях и т. д.) для прогнозирования с помощью созданной модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-130">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="7f4c3-131">Третий ресурс, обучающий код, показывает, какой код ML.NET API использовался средством CLI для обучения созданной модели, чтобы вы могли переобучить модель и определить, какой конкретный алгоритм обучения и гиперпараметры были выбраны средствами CLI и AutoML.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-131">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span> 

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="7f4c3-132">Общие сведения о качестве модели</span><span class="sxs-lookup"><span data-stu-id="7f4c3-132">Understanding the quality of the model</span></span>

<span data-ttu-id="7f4c3-133">При создании "оптимальной модели" с помощью средства CLI вы регистрируете метрики качества (такие как точность и достоверность аппроксимации), необходимые для требуемой задачи машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-133">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy, and R-Squared) as appropriate for the ML task you are targeting.</span></span>

<span data-ttu-id="7f4c3-134">Здесь приведены сводные данные об этих метриках, сгруппированных по задачам машинного обучения, чтобы вы могли определить качество автоматически созданной "оптимальной модели".</span><span class="sxs-lookup"><span data-stu-id="7f4c3-134">Here we summarize those metrics grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="7f4c3-135">Метрики для моделей двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="7f4c3-135">Metrics for Binary Classification models</span></span>

 <span data-ttu-id="7f4c3-136">Ниже приведен список метрик для задач машинного обучения по двоичной классификации для пяти ведущих моделей в CLI.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-136">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span> 

![изображение](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="7f4c3-138">Точность является популярной метрикой для проблем классификации, но она не всегда является лучшей метрикой для выбора оптимальной модели, как показано в ссылках ниже.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-138">Accuracy is a popular metric for classification problems, however accuracy is not always the best metric to select the best model from as explained in the references below.</span></span> <span data-ttu-id="7f4c3-139">Бывают случаи, когда нужно оценить качество модели с помощью дополнительных метрик.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-139">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="7f4c3-140">Чтобы изучить метрики, выводимые интерфейсом командной строки, см. раздел [Метрики для двоичной классификации](resources/metrics.md#metrics-for-binary-classification).</span><span class="sxs-lookup"><span data-stu-id="7f4c3-140">To explore and understand the metrics that are output by the CLI, see [Metrics for binary classification](resources/metrics.md#metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="7f4c3-141">Метрики для моделей многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="7f4c3-141">Metrics for Multi-class Classification models</span></span>

 <span data-ttu-id="7f4c3-142">Ниже приведен список метрик для задач машинного обучения по многоклассовой классификации для пяти ведущих моделей в CLI.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-142">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span> 

![изображение](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="7f4c3-144">Чтобы изучить метрики, выводимые интерфейсом командной строки, см. раздел [Метрики для многоклассовой классификации](resources/metrics.md#metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="7f4c3-144">To explore and understand the metrics that are output by the CLI, see [Metrics for multiclass classification](resources/metrics.md#metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-models"></a><span data-ttu-id="7f4c3-145">Метрики для моделей регрессии</span><span class="sxs-lookup"><span data-stu-id="7f4c3-145">Metrics for Regression models</span></span>

<span data-ttu-id="7f4c3-146">Модель регрессии хорошо соответствует данным, если различия между наблюдаемыми значениями и прогнозируемыми значениями модели являются незначительными и несистематическими.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="7f4c3-147">Регрессию можно оценить с помощью определенных метрик.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="7f4c3-148">Вы увидите схожий список метрик для пяти наиболее качественных моделей, обнаруженных CLI.</span><span class="sxs-lookup"><span data-stu-id="7f4c3-148">You will see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="7f4c3-149">Для данного конкретного случая, связанного с задачей машинного обучения по регрессии:</span><span class="sxs-lookup"><span data-stu-id="7f4c3-149">In this particular case related to a regression ML task:</span></span>

![изображение](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="7f4c3-151">Чтобы изучить метрики, выводимые интерфейсом командной строки, см. раздел [Метрики для регрессии](resources/metrics.md#metrics-for-regression).</span><span class="sxs-lookup"><span data-stu-id="7f4c3-151">To explore and understand the metrics that are output by the CLI, see [Metrics for regression](resources/metrics.md#metrics-for-regression).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f4c3-152">См. также</span><span class="sxs-lookup"><span data-stu-id="7f4c3-152">See also</span></span>

- [<span data-ttu-id="7f4c3-153">Установка интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="7f4c3-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="7f4c3-154">Учебник. Автоматическое создание бинарного классификатора с помощью интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="7f4c3-154">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](tutorials/mlnet-cli.md)
- [<span data-ttu-id="7f4c3-155">Справочник по командам интерфейса командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="7f4c3-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="7f4c3-156">Данные телеметрии в интерфейсе командной строки ML.NET</span><span class="sxs-lookup"><span data-stu-id="7f4c3-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
