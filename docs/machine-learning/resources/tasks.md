---
title: Задачи машинного обучения
description: Изучите возможности задач машинного обучения и связанных задач, поддерживаемых в ML.NET.
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: ed6361fdcbca11c100ee5cae4ca76e152ddfba11
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063543"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="17112-103">Задачи машинного обучения в ML.NET</span><span class="sxs-lookup"><span data-stu-id="17112-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="17112-104">Создавая модель машинного обучения, сначала следует определить цели, которых вы намерены достичь для имеющихся данных.</span><span class="sxs-lookup"><span data-stu-id="17112-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="17112-105">Это позволит вам правильно выбрать задачу машинного обучения для конкретной ситуации.</span><span class="sxs-lookup"><span data-stu-id="17112-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="17112-106">В следующем списке описываются разные задачи машинного обучения, которые вы можете выбрать, и распространенные варианты их использования.</span><span class="sxs-lookup"><span data-stu-id="17112-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="17112-107">Определив задачу для своего сценария, выберите наилучший алгоритм для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="17112-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="17112-108">Далее перечислены доступные алгоритмы для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="17112-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="17112-109">Двоичная классификация</span><span class="sxs-lookup"><span data-stu-id="17112-109">Binary classification</span></span>

<span data-ttu-id="17112-110">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение элементов данных по двум классам (категориям).</span><span class="sxs-lookup"><span data-stu-id="17112-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="17112-111">На вход алгоритма классификации подается набор примеров с метками, каждая из которых представляет собой целое число 0 или 1.</span><span class="sxs-lookup"><span data-stu-id="17112-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="17112-112">Результатом работы алгоритма двоичной классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки.</span><span class="sxs-lookup"><span data-stu-id="17112-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="17112-113">Вот несколько примеров для сценария двоичной классификации:</span><span class="sxs-lookup"><span data-stu-id="17112-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="17112-114">[Распределение комментариев Twitter по тональности](../tutorials/sentiment-analysis.md) — позитивные или негативные.</span><span class="sxs-lookup"><span data-stu-id="17112-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="17112-115">Диагностика пациента на наличие определенной болезни.</span><span class="sxs-lookup"><span data-stu-id="17112-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="17112-116">Принятие решений о присвоении отметки "спам" сообщению электронной почты.</span><span class="sxs-lookup"><span data-stu-id="17112-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="17112-117">Определение, содержит ли фотография собаку или фрукты.</span><span class="sxs-lookup"><span data-stu-id="17112-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="17112-118">Дополнительные сведения см. в [статье о двоичной классификации](https://en.wikipedia.org/wiki/Binary_classification) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="17112-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="17112-119">Алгоритмы обучения двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="17112-119">Binary classification trainers</span></span>

<span data-ttu-id="17112-120">Вы можете обучить модель двоичной классификации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer> 
* <xref:Microsoft.ML.Trainers.PriorTrainer> 
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="17112-121">Входные и выходные данные двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="17112-121">Binary classification inputs and outputs</span></span>

<span data-ttu-id="17112-122">Для получения наилучших результатов обучения двоичной классификации обучающие данные должны быть сбалансированы (т. е. число положительных и отрицательных обучающих данных должно быть одинаковым).</span><span class="sxs-lookup"><span data-stu-id="17112-122">For best results with binary classification, the training data should be balanced (i.e. equal numbers of positive and negative training data).</span></span> <span data-ttu-id="17112-123">Отсутствующие значения необходимо обработать до обучения.</span><span class="sxs-lookup"><span data-stu-id="17112-123">Missing and values should be handled before training.</span></span>

<span data-ttu-id="17112-124">Входные данные столбца меток должны иметь тип <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="17112-124">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="17112-125">Входные данные столбца функций должны быть вектором <xref:System.Single> фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="17112-125">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="17112-126">Эти алгоритмы обучения выводят приведенные ниже столбцы.</span><span class="sxs-lookup"><span data-stu-id="17112-126">These trainers outputs the following columns:</span></span>

| <span data-ttu-id="17112-127">Имя выходного столбца</span><span class="sxs-lookup"><span data-stu-id="17112-127">Output Column Name</span></span> | <span data-ttu-id="17112-128">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="17112-128">Column Type</span></span> | <span data-ttu-id="17112-129">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-129">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="17112-130">Необработанная оценка, рассчитанная моделью.</span><span class="sxs-lookup"><span data-stu-id="17112-130">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="17112-131">Прогнозируемая метка, зависящая от знака оценки.</span><span class="sxs-lookup"><span data-stu-id="17112-131">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="17112-132">Отрицательная оценка соответствует значению `false`, а положительная — значению `true`.</span><span class="sxs-lookup"><span data-stu-id="17112-132">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="17112-133">Многоклассовая классификация</span><span class="sxs-lookup"><span data-stu-id="17112-133">Multiclass classification</span></span>

<span data-ttu-id="17112-134">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение экземпляров данных по нескольким классам (категориям).</span><span class="sxs-lookup"><span data-stu-id="17112-134">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="17112-135">На вход алгоритма классификации подается набор примеров с метками.</span><span class="sxs-lookup"><span data-stu-id="17112-135">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="17112-136">Каждая метка обычно запускается как текст.</span><span class="sxs-lookup"><span data-stu-id="17112-136">Each label normally starts as text.</span></span> <span data-ttu-id="17112-137">Затем она запускается через TermTransform, который преобразует ее в тип ключа (числовой).</span><span class="sxs-lookup"><span data-stu-id="17112-137">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="17112-138">Результатом работы алгоритма классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки.</span><span class="sxs-lookup"><span data-stu-id="17112-138">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="17112-139">Вот несколько примеров для сценария многоклассовой классификации:</span><span class="sxs-lookup"><span data-stu-id="17112-139">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="17112-140">определение породы собаки, например "сибирский хаски", "золотистый ретривер", "пудель" и т. д;</span><span class="sxs-lookup"><span data-stu-id="17112-140">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="17112-141">распределение отзывов о фильме по категориям "позитивный", "нейтральный" или "негативный";</span><span class="sxs-lookup"><span data-stu-id="17112-141">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="17112-142">выбор категорий для отзывов о гостиницах, например "местоположение", "цена", "чистота" и т. д.</span><span class="sxs-lookup"><span data-stu-id="17112-142">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="17112-143">Дополнительные сведения см. в [статье о многоклассовой классификации](https://en.wikipedia.org/wiki/Multiclass_classification) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="17112-143">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="17112-144">В рамках стратегии one-vs.-rest обновляется любой [алгоритм обучения двоичной классификации](#binary-classification) для работы с многоклассовыми наборами данных.</span><span class="sxs-lookup"><span data-stu-id="17112-144">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="17112-145">Дополнительные сведения см. в статье (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="17112-145">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="17112-146">Алгоритмы обучения многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="17112-146">Multiclass classification trainers</span></span>

<span data-ttu-id="17112-147">Вы можете обучить модель многоклассовой классификации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-147">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer> 

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="17112-148">Входные и выходные данные многоклассовой классификации</span><span class="sxs-lookup"><span data-stu-id="17112-148">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="17112-149">Входные данные столбца меток должны иметь тип [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="17112-149">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="17112-150">Столбец функций должен быть вектором <xref:System.Single> фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="17112-150">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="17112-151">Этот алгоритм обучения выводит приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="17112-151">This trainer outputs the following:</span></span>

| <span data-ttu-id="17112-152">Имя выходных данных</span><span class="sxs-lookup"><span data-stu-id="17112-152">Output Name</span></span> | <span data-ttu-id="17112-153">Тип</span><span class="sxs-lookup"><span data-stu-id="17112-153">Type</span></span> | <span data-ttu-id="17112-154">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-154">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="17112-155">Вектор <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="17112-155">Vector of <xref:System.Single></span></span> | <span data-ttu-id="17112-156">Оценки всех классов.</span><span class="sxs-lookup"><span data-stu-id="17112-156">The scores of all classes.</span></span> <span data-ttu-id="17112-157">Более высокое значение означает большую вероятность попадания в связанный класс.</span><span class="sxs-lookup"><span data-stu-id="17112-157">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="17112-158">Если i-й элемент имеет самое большое значение, индекс прогнозируемой метки будет равен i.</span><span class="sxs-lookup"><span data-stu-id="17112-158">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="17112-159">Обратите внимание, что индекс i отсчитывается от нуля.</span><span class="sxs-lookup"><span data-stu-id="17112-159">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="17112-160">Тип [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="17112-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="17112-161">Индекс прогнозируемой метки.</span><span class="sxs-lookup"><span data-stu-id="17112-161">The predicted label's index.</span></span> <span data-ttu-id="17112-162">Если его значение равно i, фактическая метка будет i-й категорией во входном типе метки с ключевым значением.</span><span class="sxs-lookup"><span data-stu-id="17112-162">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="17112-163">Регрессия</span><span class="sxs-lookup"><span data-stu-id="17112-163">Regression</span></span>

<span data-ttu-id="17112-164">[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует значение метки по набору связанных компонентов.</span><span class="sxs-lookup"><span data-stu-id="17112-164">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="17112-165">Метка здесь может принимать любое значение, а не просто выбирается из конечного набора значений, как в задачах классификации.</span><span class="sxs-lookup"><span data-stu-id="17112-165">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="17112-166">Алгоритмы регрессии моделируют зависимость меток от связанных компонентов, чтобы определить закономерности изменения меток при разных значениях компонентов.</span><span class="sxs-lookup"><span data-stu-id="17112-166">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="17112-167">На вход алгоритма регрессии подается набор примеров с метками известных значений.</span><span class="sxs-lookup"><span data-stu-id="17112-167">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="17112-168">Результатом работы алгоритма регрессии является функция, которая умеет прогнозировать значения метки для любого нового набора входных компонентов.</span><span class="sxs-lookup"><span data-stu-id="17112-168">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="17112-169">Вот несколько примеров для сценария регрессии:</span><span class="sxs-lookup"><span data-stu-id="17112-169">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="17112-170">прогнозирование цен на дома по таким атрибутам, как количество комнат, расположение и размер;</span><span class="sxs-lookup"><span data-stu-id="17112-170">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="17112-171">прогнозирование будущей цены акций на основе исторических данных и текущих тенденций рынка;</span><span class="sxs-lookup"><span data-stu-id="17112-171">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="17112-172">прогнозирование продаж товара в зависимости от рекламного бюджета.</span><span class="sxs-lookup"><span data-stu-id="17112-172">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="17112-173">Алгоритмы обучения регрессии</span><span class="sxs-lookup"><span data-stu-id="17112-173">Regression trainers</span></span>

<span data-ttu-id="17112-174">Вы можете обучить модель регрессии, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-174">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="17112-175">Входные и выходные данные регрессии</span><span class="sxs-lookup"><span data-stu-id="17112-175">Regression inputs and outputs</span></span>

<span data-ttu-id="17112-176">Входные данные столбца меток должны иметь тип <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="17112-176">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="17112-177">Алгоритмы обучения для этой задачи выводят приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="17112-177">The trainers for this task output the following:</span></span>

| <span data-ttu-id="17112-178">Имя выходных данных</span><span class="sxs-lookup"><span data-stu-id="17112-178">Output Name</span></span> | <span data-ttu-id="17112-179">Тип</span><span class="sxs-lookup"><span data-stu-id="17112-179">Type</span></span> | <span data-ttu-id="17112-180">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-180">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="17112-181">Необработанное оценка, спрогнозированная моделью.</span><span class="sxs-lookup"><span data-stu-id="17112-181">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="17112-182">Кластеризация</span><span class="sxs-lookup"><span data-stu-id="17112-182">Clustering</span></span>

<span data-ttu-id="17112-183">[Задача неконтролируемого машинного обучения](glossary.md#unsupervised-machine-learning), которая группирует отдельные экземпляры данных в кластеры со сходными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="17112-183">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="17112-184">Кластеризацию можно также использовать для определения в наборе данных связей, которые невозможно логически отследить просмотром или наблюдением данных.</span><span class="sxs-lookup"><span data-stu-id="17112-184">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="17112-185">Входные и выходные данные для алгоритма кластеризации зависят от выбранного метода.</span><span class="sxs-lookup"><span data-stu-id="17112-185">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="17112-186">Вы можете выбрать подход на основе распространения, центроида, возможности подключения или плотности.</span><span class="sxs-lookup"><span data-stu-id="17112-186">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="17112-187">ML.NET в настоящее время поддерживает только кластеризацию методом К-средних на основе центроида.</span><span class="sxs-lookup"><span data-stu-id="17112-187">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="17112-188">Примеры сценариев для использования кластеризации:</span><span class="sxs-lookup"><span data-stu-id="17112-188">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="17112-189">распределение посетителей гостиниц на сегменты, исходя из привычек и характеристик выбора гостиниц;</span><span class="sxs-lookup"><span data-stu-id="17112-189">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="17112-190">определение сегментов и демографических характеристик для клиентов, чтобы создавать целевые рекламные кампании;</span><span class="sxs-lookup"><span data-stu-id="17112-190">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="17112-191">определение категорий запасов по параметрам производства.</span><span class="sxs-lookup"><span data-stu-id="17112-191">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="17112-192">Алгоритм обучения кластеризации</span><span class="sxs-lookup"><span data-stu-id="17112-192">Clustering trainer</span></span>

<span data-ttu-id="17112-193">Вы можете обучить модель кластеризации, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-193">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer> 

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="17112-194">Входные и выходные данные кластеризации</span><span class="sxs-lookup"><span data-stu-id="17112-194">Clustering inputs and outputs</span></span>

<span data-ttu-id="17112-195">Входные данные функций должны иметь тип <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="17112-195">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="17112-196">Метки не требуются.</span><span class="sxs-lookup"><span data-stu-id="17112-196">No labels are needed.</span></span>

<span data-ttu-id="17112-197">Этот алгоритм обучения выводит приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="17112-197">This trainer outputs the following:</span></span>

| <span data-ttu-id="17112-198">Имя выходных данных</span><span class="sxs-lookup"><span data-stu-id="17112-198">Output Name</span></span> | <span data-ttu-id="17112-199">Тип</span><span class="sxs-lookup"><span data-stu-id="17112-199">Type</span></span> | <span data-ttu-id="17112-200">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-200">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="17112-201">Вектор <xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="17112-201">vector of <xref:System.Single></span></span> | <span data-ttu-id="17112-202">Расстояния от указанной точки данных до центроидов всех кластеров.</span><span class="sxs-lookup"><span data-stu-id="17112-202">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="17112-203">Тип [key](xref:Microsoft.ML.Data.KeyDataViewType)</span><span class="sxs-lookup"><span data-stu-id="17112-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="17112-204">Индекс ближайшего кластера, спрогнозированный моделью.</span><span class="sxs-lookup"><span data-stu-id="17112-204">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="17112-205">Обнаружение аномалий</span><span class="sxs-lookup"><span data-stu-id="17112-205">Anomaly detection</span></span>

<span data-ttu-id="17112-206">Эта задача создает модель обнаружения аномалий с помощью анализа главных компонентов (PCA).</span><span class="sxs-lookup"><span data-stu-id="17112-206">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="17112-207">Обнаружение аномалий на основе PCA позволяет создавать модели в сценариях, где легко получить данные для обучения из одного класса, такого как допустимые транзакции, однако получить достаточную выборку аномальных значений затруднительно.</span><span class="sxs-lookup"><span data-stu-id="17112-207">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="17112-208">Общепринятый метод в машинном обучении, PCA, часто используется в разведочном анализе данных, так как он раскрывает внутреннюю структуру данных и объясняет их вариативность.</span><span class="sxs-lookup"><span data-stu-id="17112-208">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="17112-209">PCA выполняется путем анализа данных с несколькими переменными.</span><span class="sxs-lookup"><span data-stu-id="17112-209">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="17112-210">Он выполняет поиск корреляции между переменными и определяет сочетание значений, которые лучше всего фиксируют различия результатов.</span><span class="sxs-lookup"><span data-stu-id="17112-210">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="17112-211">Эти объединенные значения компонентов используются для создания более компактных компонентов, называемых главными компонентами.</span><span class="sxs-lookup"><span data-stu-id="17112-211">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="17112-212">Обнаружение аномалий включает в себя ряд важных задач машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="17112-212">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="17112-213">Выявление потенциально мошеннических транзакций.</span><span class="sxs-lookup"><span data-stu-id="17112-213">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="17112-214">Изучение шаблонов, которые указывают, что произошли сетевые атаки.</span><span class="sxs-lookup"><span data-stu-id="17112-214">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="17112-215">Поиск аномальных кластеров пациентов.</span><span class="sxs-lookup"><span data-stu-id="17112-215">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="17112-216">Проверка значений, введенных в систему.</span><span class="sxs-lookup"><span data-stu-id="17112-216">Checking values entered into a system.</span></span>

<span data-ttu-id="17112-217">Так как аномалии по определению довольно-таки редкие события, со сборкой репрезентативной выборки данных, используемых для моделирования, могут быть трудности.</span><span class="sxs-lookup"><span data-stu-id="17112-217">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="17112-218">Алгоритмы, включенные в эту категорию, специально разработаны для решения основных проблем разработки и обучения моделей с использованием несбалансированных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="17112-218">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="17112-219">Алгоритм обучения обнаружению аномалий</span><span class="sxs-lookup"><span data-stu-id="17112-219">Anomaly detection trainer</span></span>

<span data-ttu-id="17112-220">Вы можете обучить модель обнаружения аномалий, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-220">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="17112-221">Входные и выходные данные обнаружения аномалий</span><span class="sxs-lookup"><span data-stu-id="17112-221">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="17112-222">Входные данные функций должны быть вектором <xref:System.Single> фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="17112-222">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="17112-223">Этот алгоритм обучения выводит приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="17112-223">This trainer outputs the following:</span></span>

| <span data-ttu-id="17112-224">Имя выходных данных</span><span class="sxs-lookup"><span data-stu-id="17112-224">Output Name</span></span> | <span data-ttu-id="17112-225">Тип</span><span class="sxs-lookup"><span data-stu-id="17112-225">Type</span></span> | <span data-ttu-id="17112-226">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-226">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="17112-227">Неотрицательная неограниченная оценка, вычисленная моделью обнаружения аномалий</span><span class="sxs-lookup"><span data-stu-id="17112-227">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="17112-228">Ранжирование</span><span class="sxs-lookup"><span data-stu-id="17112-228">Ranking</span></span>

<span data-ttu-id="17112-229">Задача ранжирования создает средство ранжирования на основе набора примеров с метками.</span><span class="sxs-lookup"><span data-stu-id="17112-229">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="17112-230">Этот набор примеров состоит из групп экземпляров, которые могут быть оценены с заданными критериями.</span><span class="sxs-lookup"><span data-stu-id="17112-230">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="17112-231">Метки ранжирования для каждого экземпляра — { 0, 1, 2, 3, 4 }.</span><span class="sxs-lookup"><span data-stu-id="17112-231">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="17112-232">Средство ранжирования обучается ранжировать новые группы экземпляров с неизвестными оценками для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="17112-232">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="17112-233">Алгоритмы обучения ранжированию ML.NET основаны на [ранжировании машинного обучения](https://en.wikipedia.org/wiki/Learning_to_rank).</span><span class="sxs-lookup"><span data-stu-id="17112-233">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="17112-234">Алгоритмы обучения ранжированию</span><span class="sxs-lookup"><span data-stu-id="17112-234">Ranking training algorithms</span></span>

<span data-ttu-id="17112-235">Вы можете обучить модель ранжирования, используя следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="17112-235">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer> 

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="17112-236">Входные и выходные данные ранжирования</span><span class="sxs-lookup"><span data-stu-id="17112-236">Ranking input and outputs</span></span>

<span data-ttu-id="17112-237">Входные данные метки должны иметь тип [key](xref:Microsoft.ML.Data.KeyDataViewType) или <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="17112-237">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="17112-238">Значение метки определяет релевантность, где более высокие значения означают более высокую степень релевантности.</span><span class="sxs-lookup"><span data-stu-id="17112-238">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="17112-239">Если метка имеет тип [key](xref:Microsoft.ML.Data.KeyDataViewType), индексом ключа будет значение релевантности, где наименьший индекс является минимально релевантным.</span><span class="sxs-lookup"><span data-stu-id="17112-239">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="17112-240">Если метка имеет тип <xref:System.Single>, более высокие значения означают более высокую степень релевантности.</span><span class="sxs-lookup"><span data-stu-id="17112-240">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="17112-241">Данные должны быть вектором <xref:System.Single> фиксированного размера, а входной столбец группы строк должен иметь тип [key](xref:Microsoft.ML.Data.KeyDataViewType).</span><span class="sxs-lookup"><span data-stu-id="17112-241">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="17112-242">Этот алгоритм обучения выводит приведенные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="17112-242">This trainer outputs the following:</span></span>

| <span data-ttu-id="17112-243">Имя выходных данных</span><span class="sxs-lookup"><span data-stu-id="17112-243">Output Name</span></span> | <span data-ttu-id="17112-244">Тип</span><span class="sxs-lookup"><span data-stu-id="17112-244">Type</span></span> | <span data-ttu-id="17112-245">Описание</span><span class="sxs-lookup"><span data-stu-id="17112-245">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="17112-246">Неограниченная оценка, вычисленная моделью для определения прогноза</span><span class="sxs-lookup"><span data-stu-id="17112-246">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="17112-247">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="17112-247">Recommendation</span></span>

<span data-ttu-id="17112-248">Задача рекомендации позволяет создать список рекомендуемых продуктов или служб.</span><span class="sxs-lookup"><span data-stu-id="17112-248">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="17112-249">ML.NET использует [факторизацию матрицы (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), алгоритм [совместной фильтрации](https://en.wikipedia.org/wiki/Collaborative_filtering) для рекомендаций при наличии исторических данных о рейтинге продуктов в вашем каталоге.</span><span class="sxs-lookup"><span data-stu-id="17112-249">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="17112-250">Например, у вас есть исторические данные о рейтинге фильмов для ваших пользователей, и вы хотите рекомендовать другие фильмы, которые они, вероятно, просмотрят следующими.</span><span class="sxs-lookup"><span data-stu-id="17112-250">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="17112-251">Алгоритмы обучения рекомендациям</span><span class="sxs-lookup"><span data-stu-id="17112-251">Recommendation training algorithms</span></span>

<span data-ttu-id="17112-252">Вы можете обучить модель рекомендаций, используя следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="17112-252">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
