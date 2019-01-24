---
title: Задачи машинного обучения. Использование ML.NET
description: Изучите возможности задач машинного обучения и связанных задач, поддерживаемых в ML.NET.
ms.custom: seodec18
ms.date: 01/15/2019
author: jralexander
ms.openlocfilehash: 02b454d18eca36c94c27ae15665af5df2ec87905
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415706"
---
# <a name="machine-learning-tasks-in-mlnet"></a>Задачи машинного обучения в ML.NET

Создавая модель машинного обучения, сначала следует определить цели, которых вы намерены достичь для имеющихся данных. Это позволит вам правильно выбрать задачу машинного обучения для конкретной ситуации. В следующем списке описываются разные задачи машинного обучения, которые вы можете выбрать, и распространенные варианты их использования.

> [!NOTE]
> ML.NET сейчас находится на этапе предварительной версии. Это означает, что пока поддерживаются не все задачи машинного обучения. Чтобы сообщить о проблеме с определенной задачей, создайте заявку [в репозитории dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).

## <a name="binary-classification"></a>Двоичная классификация

[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение элементов данных по двум классам (категориям). На вход алгоритма классификации подается набор примеров с метками, каждая из которых представляет собой целое число 0 или 1. Результатом работы алгоритма двоичной классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки. Вот несколько примеров для сценария двоичной классификации:

* [Распределение комментариев Twitter по тональности](../tutorials/sentiment-analysis.md) — позитивные или негативные.
* Диагностика пациента на наличие определенной болезни.
* Принятие решений о присвоении отметки "спам" сообщению электронной почты.
* Определение, содержит ли фотография собаку или фрукты.

Дополнительные сведения см. в [статье о двоичной классификации](https://en.wikipedia.org/wiki/Binary_classification) в Википедии.

Рекомендуемые алгоритмы обучения для двоичной классификации:

* AveragedPerceptronTrainer;
* StochasticGradientDescentClassificationTrainer;
* LightGbmBinaryTrainer;
* FastTreeBinaryClassificationTrainer;
* SymSgdClassificationTrainer.

### <a name="binary-classification-learners"></a>Алгоритмы обучения для двоичной классификации

Для задач двоичной классификации доступны следующие алгоритмы обучения:

* [AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.Online.AveragedPerceptronTrainer);
* [BinaryClassificationGamTrainer](xref:Microsoft.ML.Trainers.FastTree.BinaryClassificationGamTrainer);
* [FastForestClassification](xref:Microsoft.ML.Trainers.FastTree.FastForestClassification);
* [FastTreeBinaryClassificationTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer);
* [FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.FactorizationMachine.FieldAwareFactorizationMachineTrainer);
* [LightGbmBinaryTrainer](xref:Microsoft.ML.LightGBM.LightGbmBinaryTrainer);
* [LinearSvmTrainer](xref:Microsoft.ML.Trainers.Online.LinearSvmTrainer)
* [LogisticRegression](xref:Microsoft.ML.Learners.LogisticRegression);
* [PriorTrainer](xref:Microsoft.ML.Trainers.PriorTrainer);
* [RandomTrainer](xref:Microsoft.ML.Trainers.RandomTrainer);
* [StochasticGradientDescentClassificationTrainer](xref:Microsoft.ML.Trainers.StochasticGradientDescentClassificationTrainer);
* [SymSgdClassificationTrainer](xref:Microsoft.ML.Trainers.SymSgd.SymSgdClassificationTrainer).

## <a name="multiclass-classification"></a>Многоклассовая классификация

[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует распределение экземпляров данных по нескольким классам (категориям). На вход алгоритма классификации подается набор примеров с метками. Каждая метка обычно запускается как текст. Затем она запускается через TermTransform, который преобразует ее в тип ключа (числовой). Результатом работы алгоритма классификации является классификатор, который умеет прогнозировать класс для новых экземпляров без метки. Вот несколько примеров для сценария многоклассовой классификации:

* определение породы собаки, например "сибирский хаски", "золотистый ретривер", "пудель" и т. д;
* распределение отзывов о фильме по категориям "позитивный", "нейтральный" или "негативный";
* выбор категорий для отзывов о гостиницах, например "местоположение", "цена", "чистота" и т. д.

Дополнительные сведения см. в [статье о многоклассовой классификации](https://en.wikipedia.org/wiki/Multiclass_classification) в Википедии.

Рекомендуемые алгоритмы обучения для многоклассовой классификации:

* OVA-AveragedPerceptronTrainer;
* SdcaMultiClassTrainer;
* LightGbmMulticlassTrainer;
* OVA-FastTreeBinaryClassificationTrainer.

>[!NOTE]
>OVA и PKPD обновляют любой [алгоритм обучения двоичной классификации](#binary-classification) для работы с многоклассовыми наборами данных. Дополнительные сведения см. в статье (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) в Википедии.

### <a name="multiclass-classification-learners"></a>Алгоритмы обучения для многоклассовой классификации

Для задач многоклассовой классификации доступны следующие алгоритмы обучения:

* [LightGbmMulticlassTrainer](xref:Microsoft.ML.LightGBM.LightGbmMulticlassTrainer);
* [MetaMulticlassTrainer<TTransformer,TModel>](xref:Microsoft.ML.Learners.MetaMulticlassTrainer%602);
* [MultiClassNaiveBayesTrainer](xref:Microsoft.ML.Trainers.MultiClassNaiveBayesTrainer);
* [Ova](xref:Microsoft.ML.Trainers.Ova);
* [Pkpd](xref:Microsoft.ML.Trainers.Pkpd);
* [SdcaMultiClassTrainer](xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer).

## <a name="regression"></a>Возвращение

[Задача контролируемого машинного обучения](glossary.md#supervised-machine-learning), которая прогнозирует значение метки по набору связанных компонентов. Метка здесь может принимать любое значение, а не просто выбирается из конечного набора значений, как в задачах классификации. Алгоритмы регрессии моделируют зависимость меток от связанных компонентов, чтобы определить закономерности изменения меток при разных значениях компонентов. На вход алгоритма регрессии подается набор примеров с метками известных значений. Результатом работы алгоритма регрессии является функция, которая умеет прогнозировать значения метки для любого нового набора входных компонентов. Вот несколько примеров для сценария регрессии:

* прогнозирование цен на дома по таким атрибутам, как количество комнат, расположение и размер;
* прогнозирование будущей цены акций на основе исторических данных и текущих тенденций рынка;
* прогнозирование продаж товара в зависимости от рекламного бюджета.

Рекомендуемые регрессионные алгоритмы обучения:

* FastTreeTweedieTrainer; 
* LightGbmRegressorTrainer; 
* SdcaRegressionTrainer; 
* FastTreeRegressionTrainer.

### <a name="regression-learners"></a>Регрессионные алгоритмы обучения

Для задач регрессии доступны следующие алгоритмы обучения:

* [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer);
* [FastTreeTweedieTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer);
* [LightGbmRegressorTrainer](xref:Microsoft.ML.LightGBM.LightGbmRegressorTrainer);
* [OlsLinearRegressionTrainer](xref:Microsoft.ML.Trainers.HalLearners.OlsLinearRegressionTrainer);
* [OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.Online.OnlineGradientDescentTrainer);
* [PoissonRegression](xref:Microsoft.ML.Trainers.PoissonRegression);
* [RegressionGamTrainer](xref:Microsoft.ML.Trainers.FastTree.RegressionGamTrainer);
* [SdcaRegressionTrainer](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer);
* [FastTree.SingleTrainer](xref:Microsoft.ML.Trainers.FastTree.SingleTrainer);
* [LightGBM.SingleTrainer](xref:Microsoft.ML.LightGBM.SingleTrainer).

## <a name="clustering"></a>Кластеризация

[Задача неконтролируемого машинного обучения](glossary.md#unsupervised-machine-learning), которая группирует отдельные экземпляры данных в кластеры со сходными характеристиками. Кластеризацию можно также использовать для определения в наборе данных связей, которые невозможно логически отследить просмотром или наблюдением данных. Входные и выходные данные для алгоритма кластеризации зависят от выбранного метода. Вы можете выбрать подход на основе распространения, центроида, возможности подключения или плотности. ML.NET в настоящее время поддерживает только кластеризацию методом К-средних на основе центроида. Примеры сценариев для использования кластеризации:

* распределение посетителей гостиниц на сегменты, исходя из привычек и характеристик выбора гостиниц;
* определение сегментов и демографических характеристик для клиентов, чтобы создавать целевые рекламные кампании;
* определение категорий запасов по параметрам производства.

### <a name="clustering-learners"></a>Алгоритмы обучения для кластеризации

Для задач кластеризации доступен следующий алгоритм обучения:

* [KMeansPlusPlusTrainer](xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer).

## <a name="anomaly-detection"></a>Обнаружение аномалий

Эта задача создает модель обнаружения аномалий с помощью анализа главных компонентов (PCA). Обнаружение аномалий на основе PCA позволяет создавать модели в сценариях, где легко получить данные для обучения из одного класса, такого как допустимые транзакции, однако получить достаточную выборку аномальных значений затруднительно.

Общепринятый метод в машинном обучении, PCA, часто используется в разведочном анализе данных, так как он раскрывает внутреннюю структуру данных и объясняет их вариативность. PCA выполняется путем анализа данных с несколькими переменными. Он выполняет поиск корреляции между переменными и определяет сочетание значений, которые лучше всего фиксируют различия результатов. Эти объединенные значения компонентов используются для создания более компактных компонентов, называемых главными компонентами.

Обнаружение аномалий включает в себя ряд важных задач машинного обучения:

* Выявление потенциально мошеннических транзакций.
* Изучение шаблонов, которые указывают, что произошли сетевые атаки.
* Поиск аномальных кластеров пациентов.
* Проверка значений, введенных в систему.

Так как аномалии по определению довольно-таки редкие события, со сборкой репрезентативной выборки данных, используемых для моделирования, могут быть трудности. Алгоритмы, включенные в эту категорию, специально разработаны для решения основных проблем разработки и обучения моделей с использованием несбалансированных наборов данных.

### <a name="anomaly-detection-learners"></a>Алгоритмы обучения для обнаружения аномалий

Для задач обнаружения аномалий доступен следующий алгоритм обучения:

* [RandomizedPcaTrainer](xref:Microsoft.ML.Trainers.PCA.RandomizedPcaTrainer).

## <a name="ranking"></a>Ранжирование

Задача ранжирования создает средство ранжирования на основе набора примеров с метками. Этот набор примеров состоит из групп экземпляров, которые могут быть оценены с заданными критериями. Метки ранжирования для каждого экземпляра — { 0, 1, 2, 3, 4 }.  Средство ранжирования обучается ранжировать новые группы экземпляров с неизвестными оценками для каждого экземпляра. Алгоритмы обучения ранжированию ML.NET основаны на [ранжировании машинного обучения](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-learners"></a>Алгоритмы обучения для ранжирования

Для задач ранжирования доступны следующие алгоритмы обучения:

* [FastTreeRankingTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer);
* [LightGbmRankingTrainer](xref:Microsoft.ML.LightGBM.LightGbmRankingTrainer).

## <a name="recommendation"></a>Рекомендация

Задача рекомендации позволяет создать список рекомендуемых продуктов или служб. ML.NET использует [факторизацию матрицы (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), алгоритм [совместной фильтрации](https://en.wikipedia.org/wiki/Collaborative_filtering) для рекомендаций при наличии исторических данных о рейтинге продуктов в вашем каталоге. Например, у вас есть исторические данные о рейтинге фильмов для ваших пользователей, и вы хотите рекомендовать другие фильмы, которые они, вероятно, просмотрят следующими.

### <a name="recommendation-learners"></a>Алгоритмы обучения для задач рекомендации

Для задач рекомендации доступны следующие алгоритмы обучения:

* [MatrixFactorizationTrainer](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer);
* [MatrixFactorizationPredictionTransformer](xref:Microsoft.ML.Trainers.Recommender.MatrixFactorizationPredictionTransformer).
