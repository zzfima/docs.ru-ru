---
title: Задачи машинного обучения. Использование ML.NET
description: Изучите возможности задач машинного обучения и связанных задач, поддерживаемых в ML.NET.
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613165"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="361b3-103">Задачи машинного обучения в ML.NET</span><span class="sxs-lookup"><span data-stu-id="361b3-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="361b3-104">Создавая модель машинного обучения, сначала следует определить цели, которых вы намерены достичь для имеющихся данных.</span><span class="sxs-lookup"><span data-stu-id="361b3-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="361b3-105">Это позволит вам правильно выбрать задачу машинного обучения для конкретной ситуации.</span><span class="sxs-lookup"><span data-stu-id="361b3-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="361b3-106">В следующем списке описываются разные задачи машинного обучения, которые вы можете выбрать, и распространенные варианты их использования.</span><span class="sxs-lookup"><span data-stu-id="361b3-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="361b3-107">Определив задачу для своего сценария, выберите наилучший алгоритм для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="361b3-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="361b3-108">Далее перечислены доступные алгоритмы для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="361b3-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="361b3-109">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="361b3-109">Binary classification</span></span>

<span data-ttu-id="361b3-110">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение элементов данных по двум классам (категориям).</span><span class="sxs-lookup"><span data-stu-id="361b3-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="361b3-111">На вход алгоритма классификации подается набор примеров с метками, каждая из которых представляет собой целое число 0 или 1.</span><span class="sxs-lookup"><span data-stu-id="361b3-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="361b3-112">Результатом работы алгоритма двоичной классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки.</span><span class="sxs-lookup"><span data-stu-id="361b3-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="361b3-113">Вот несколько примеров для сценария двоичной классификации:</span><span class="sxs-lookup"><span data-stu-id="361b3-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="361b3-114">[Распределение комментариев Twitter по тональности](../tutorials/sentiment-analysis.md) — позитивные или негативные.</span><span class="sxs-lookup"><span data-stu-id="361b3-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="361b3-115">Диагностика пациента на наличие определенной болезни.</span><span class="sxs-lookup"><span data-stu-id="361b3-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="361b3-116">Принятие решений о присвоении отметки "спам" сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="361b3-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="361b3-117">Определение, содержит ли фотография собаку или фрукты.</span><span class="sxs-lookup"><span data-stu-id="361b3-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="361b3-118">Дополнительные сведения см. в [статье о двоичной классификации](https://en.wikipedia.org/wiki/Binary_classification) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="361b3-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="361b3-119">Алгоритмы обучения двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="361b3-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="361b3-120">Вы можете обучить модель двоичной классификации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="361b3-121">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="361b3-121">Multiclass classification</span></span>

<span data-ttu-id="361b3-122">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение экземпляров данных по нескольким классам (категориям).</span><span class="sxs-lookup"><span data-stu-id="361b3-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="361b3-123">На вход алгоритма классификации подается набор примеров с метками.</span><span class="sxs-lookup"><span data-stu-id="361b3-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="361b3-124">Каждая метка обычно запускается как текст.</span><span class="sxs-lookup"><span data-stu-id="361b3-124">Each label normally starts as text.</span></span> <span data-ttu-id="361b3-125">Затем она запускается через TermTransform, который преобразует ее в тип ключа (числовой).</span><span class="sxs-lookup"><span data-stu-id="361b3-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="361b3-126">Результатом работы алгоритма классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки.</span><span class="sxs-lookup"><span data-stu-id="361b3-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="361b3-127">Вот несколько примеров для сценария многоклассовой классификации:</span><span class="sxs-lookup"><span data-stu-id="361b3-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="361b3-128">определение породы собаки, например "сибирский хаски", "золотистый ретривер", "пудель" и т. д;</span><span class="sxs-lookup"><span data-stu-id="361b3-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="361b3-129">распределение отзывов о фильме по категориям "позитивный", "нейтральный" или "негативный";</span><span class="sxs-lookup"><span data-stu-id="361b3-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="361b3-130">выбор категорий для отзывов о гостиницах, например "местоположение", "цена", "чистота" и т. д.</span><span class="sxs-lookup"><span data-stu-id="361b3-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="361b3-131">Дополнительные сведения см. в [статье о многоклассовой классификации](https://en.wikipedia.org/wiki/Multiclass_classification) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="361b3-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="361b3-132">В рамках стратегии one-vs.-rest обновляется любой [алгоритм обучения двоичной классификации](#binary-classification) для работы с многоклассовыми наборами данных.</span><span class="sxs-lookup"><span data-stu-id="361b3-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="361b3-133">Дополнительные сведения см. в статье (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="361b3-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="361b3-134">Алгоритмы обучения многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="361b3-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="361b3-135">Вы можете обучить модель многоклассовой классификации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="361b3-136">Регрессия</span><span class="sxs-lookup"><span data-stu-id="361b3-136">Regression</span></span>

<span data-ttu-id="361b3-137">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует значение метки по набору связанных компонентов.</span><span class="sxs-lookup"><span data-stu-id="361b3-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="361b3-138">Метка здесь может принимать любое значение, а не просто выбирается из конечного набора значений, как в задачах классификации.</span><span class="sxs-lookup"><span data-stu-id="361b3-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="361b3-139">Алгоритмы регрессии моделируют зависимость меток от связанных компонентов, чтобы определить закономерности изменения меток при разных значениях компонентов.</span><span class="sxs-lookup"><span data-stu-id="361b3-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="361b3-140">На вход алгоритма регрессии подается набор примеров с метками известных значений.</span><span class="sxs-lookup"><span data-stu-id="361b3-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="361b3-141">Результатом работы алгоритма регрессии является функция, которая умеет прогнозировать значения метки для любого нового набора входных компонентов.</span><span class="sxs-lookup"><span data-stu-id="361b3-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="361b3-142">Вот несколько примеров для сценария регрессии:</span><span class="sxs-lookup"><span data-stu-id="361b3-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="361b3-143">прогнозирование цен на дома по таким атрибутам, как количество комнат, расположение и размер;</span><span class="sxs-lookup"><span data-stu-id="361b3-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="361b3-144">прогнозирование будущей цены акций на основе исторических данных и текущих тенденций рынка;</span><span class="sxs-lookup"><span data-stu-id="361b3-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="361b3-145">прогнозирование продаж товара в зависимости от рекламного бюджета.</span><span class="sxs-lookup"><span data-stu-id="361b3-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="361b3-146">Алгоритмы обучения регрессии</span><span class="sxs-lookup"><span data-stu-id="361b3-146">Regression training algorithms</span></span>

<span data-ttu-id="361b3-147">Вы можете обучить модель регрессии, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="361b3-148">Кластеризация</span><span class="sxs-lookup"><span data-stu-id="361b3-148">Clustering</span></span>

<span data-ttu-id="361b3-149">[Задача неконтролируемого машинного обучения](glossary.md#unsupervised-machine-learning), которая группирует отдельные экземпляры данных в кластеры со сходными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="361b3-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="361b3-150">Кластеризацию можно также использовать для определения в наборе данных связей, которые невозможно логически отследить просмотром или наблюдением данных.</span><span class="sxs-lookup"><span data-stu-id="361b3-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="361b3-151">Входные и выходные данные для алгоритма кластеризации зависят от выбранного метода.</span><span class="sxs-lookup"><span data-stu-id="361b3-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="361b3-152">Вы можете выбрать подход на основе распространения, центроида, возможности подключения или плотности.</span><span class="sxs-lookup"><span data-stu-id="361b3-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="361b3-153">ML.NET в настоящее время поддерживает только кластеризацию методом К-средних на основе центроида.</span><span class="sxs-lookup"><span data-stu-id="361b3-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="361b3-154">Примеры сценариев для использования кластеризации:</span><span class="sxs-lookup"><span data-stu-id="361b3-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="361b3-155">распределение посетителей гостиниц на сегменты, исходя из привычек и характеристик выбора гостиниц;</span><span class="sxs-lookup"><span data-stu-id="361b3-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="361b3-156">определение сегментов и демографических характеристик для клиентов, чтобы создавать целевые рекламные кампании;</span><span class="sxs-lookup"><span data-stu-id="361b3-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="361b3-157">определение категорий запасов по параметрам производства.</span><span class="sxs-lookup"><span data-stu-id="361b3-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="361b3-158">Алгоритмы обучения кластеризации</span><span class="sxs-lookup"><span data-stu-id="361b3-158">Clustering training algorithms</span></span>

<span data-ttu-id="361b3-159">Вы можете обучить модель кластеризации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="361b3-160">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="361b3-160">Anomaly detection</span></span>

<span data-ttu-id="361b3-161">Эта задача создает модель обнаружения аномалий с помощью анализа главных компонентов (PCA).</span><span class="sxs-lookup"><span data-stu-id="361b3-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="361b3-162">Обнаружение аномалий на основе PCA позволяет создавать модели в сценариях, где легко получить данные для обучения из одного класса, такого как допустимые транзакции, однако получить достаточную выборку аномальных значений затруднительно.</span><span class="sxs-lookup"><span data-stu-id="361b3-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="361b3-163">Общепринятый метод в машинном обучении, PCA, часто используется в разведочном анализе данных, так как он раскрывает внутреннюю структуру данных и объясняет их вариативность.</span><span class="sxs-lookup"><span data-stu-id="361b3-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="361b3-164">PCA выполняется путем анализа данных с несколькими переменными.</span><span class="sxs-lookup"><span data-stu-id="361b3-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="361b3-165">Он выполняет поиск корреляции между переменными и определяет сочетание значений, которые лучше всего фиксируют различия результатов.</span><span class="sxs-lookup"><span data-stu-id="361b3-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="361b3-166">Эти объединенные значения компонентов используются для создания более компактных компонентов, называемых главными компонентами.</span><span class="sxs-lookup"><span data-stu-id="361b3-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="361b3-167">Обнаружение аномалий включает в себя ряд важных задач машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="361b3-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="361b3-168">Выявление потенциально мошеннических транзакций.</span><span class="sxs-lookup"><span data-stu-id="361b3-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="361b3-169">Изучение шаблонов, которые указывают, что произошли сетевые атаки.</span><span class="sxs-lookup"><span data-stu-id="361b3-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="361b3-170">Поиск аномальных кластеров пациентов.</span><span class="sxs-lookup"><span data-stu-id="361b3-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="361b3-171">Проверка значений, введенных в систему.</span><span class="sxs-lookup"><span data-stu-id="361b3-171">Checking values entered into a system.</span></span>

<span data-ttu-id="361b3-172">Так как аномалии по определению довольно-таки редкие события, со сборкой репрезентативной выборки данных, используемых для моделирования, могут быть трудности.</span><span class="sxs-lookup"><span data-stu-id="361b3-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="361b3-173">Алгоритмы, включенные в эту категорию, специально разработаны для решения основных проблем разработки и обучения моделей с использованием несбалансированных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="361b3-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="361b3-174">Алгоритмы обучения обнаружению аномалий</span><span class="sxs-lookup"><span data-stu-id="361b3-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="361b3-175">Вы можете обучить модель обнаружения аномалий, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="361b3-176">Ранжирование</span><span class="sxs-lookup"><span data-stu-id="361b3-176">Ranking</span></span>

<span data-ttu-id="361b3-177">Задача ранжирования создает средство ранжирования на основе набора примеров с метками.</span><span class="sxs-lookup"><span data-stu-id="361b3-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="361b3-178">Этот набор примеров состоит из групп экземпляров, которые могут быть оценены с заданными критериями.</span><span class="sxs-lookup"><span data-stu-id="361b3-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="361b3-179">Метки ранжирования для каждого экземпляра — { 0, 1, 2, 3, 4 }.</span><span class="sxs-lookup"><span data-stu-id="361b3-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="361b3-180">Средство ранжирования обучается ранжировать новые группы экземпляров с неизвестными оценками для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="361b3-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="361b3-181">Алгоритмы обучения ранжированию ML.NET основаны на [ранжировании машинного обучения](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="361b3-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="361b3-182">Алгоритмы обучения ранжированию</span><span class="sxs-lookup"><span data-stu-id="361b3-182">Ranking training algorithms</span></span>

<span data-ttu-id="361b3-183">Вы можете обучить модель ранжирования, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="361b3-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="361b3-184">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="361b3-184">Recommendation</span></span>

<span data-ttu-id="361b3-185">Задача рекомендации позволяет создать список рекомендуемых продуктов или служб.</span><span class="sxs-lookup"><span data-stu-id="361b3-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="361b3-186">ML.NET использует [факторизацию матрицы (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), алгоритм [совместной фильтрации](https://en.wikipedia.org/wiki/Collaborative_filtering) для рекомендаций при наличии исторических данных о рейтинге продуктов в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="361b3-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="361b3-187">Например, у вас есть исторические данные о рейтинге фильмов для ваших пользователей, и вы хотите рекомендовать другие фильмы, которые они, вероятно, просмотрят следующими.</span><span class="sxs-lookup"><span data-stu-id="361b3-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="361b3-188">Алгоритмы обучения рекомендациям</span><span class="sxs-lookup"><span data-stu-id="361b3-188">Recommendation training algorithms</span></span>

<span data-ttu-id="361b3-189">Вы можете обучить модель рекомендаций, используя следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="361b3-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
