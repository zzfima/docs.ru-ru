---
title: Загрузка обучающих данных для построителя моделей
description: Сведения о том, как загружать данные для обучения из базы данных SQL Server или из файла для использования в одном из сценариев построителя моделей с помощью ML.NET.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: 23de2d06090f4c1eaa2c79178ba4c346698d45e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849163"
---
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="2c54f-103">Загрузка данных для обучения в построитель моделей</span><span class="sxs-lookup"><span data-stu-id="2c54f-103">Load training data into Model Builder</span></span>

<span data-ttu-id="2c54f-104">Сведения о том, как загружать наборы данных для обучения из файла или базы данных SQL Server для использования в одном из сценариев построителя моделей с помощью ML.NET.</span><span class="sxs-lookup"><span data-stu-id="2c54f-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="2c54f-105">В сценариях построителя моделей в качестве данных для обучения можно использовать базы данных SQL Server, файлы изображений и форматы CSV или TSV.</span><span class="sxs-lookup"><span data-stu-id="2c54f-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="2c54f-106">Ограничения наборов данных для обучения в построителе моделей</span><span class="sxs-lookup"><span data-stu-id="2c54f-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="2c54f-107">Построитель моделей ограничивает объем и тип данных, которые можно использовать для обучения моделей.</span><span class="sxs-lookup"><span data-stu-id="2c54f-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="2c54f-108">Данные из SQL Server: 100 000 строк</span><span class="sxs-lookup"><span data-stu-id="2c54f-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="2c54f-109">CSV- и TSV-файлы: нет ограничений размера</span><span class="sxs-lookup"><span data-stu-id="2c54f-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="2c54f-110">Изображения: только PNG и JPG.</span><span class="sxs-lookup"><span data-stu-id="2c54f-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="2c54f-111">Сценарии построителя моделей</span><span class="sxs-lookup"><span data-stu-id="2c54f-111">Model Builder scenarios</span></span>

<span data-ttu-id="2c54f-112">Построитель моделей позволяет создавать модели для следующих сценариев машинного обучения:</span><span class="sxs-lookup"><span data-stu-id="2c54f-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="2c54f-113">Анализ тональности (двоичная классификация): распределение текстовых данных по двум категориям.</span><span class="sxs-lookup"><span data-stu-id="2c54f-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="2c54f-114">Классификация проблем (многоклассовая классификация): распределение текстовых данных на три или более категории.</span><span class="sxs-lookup"><span data-stu-id="2c54f-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="2c54f-115">Прогнозирование цен (регрессия): прогнозирование числового значения.</span><span class="sxs-lookup"><span data-stu-id="2c54f-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="2c54f-116">Классификация изображений (глубокое обучение): классификация изображений на основе характеристик.</span><span class="sxs-lookup"><span data-stu-id="2c54f-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="2c54f-117">Пользовательский сценарий: вы можете создавать пользовательские сценарии для своих данных, используя регрессию, классификацию и другие задачи.</span><span class="sxs-lookup"><span data-stu-id="2c54f-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="2c54f-118">В этой статье рассматриваются сценарии классификации и регрессии по текстовым или числовым данным, а также сценарии классификации изображений.</span><span class="sxs-lookup"><span data-stu-id="2c54f-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="2c54f-119">Загрузка текстовых или числовых данных из файла</span><span class="sxs-lookup"><span data-stu-id="2c54f-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="2c54f-120">В построитель моделей можно загружать текстовые или числовые данные из файла.</span><span class="sxs-lookup"><span data-stu-id="2c54f-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="2c54f-121">Он принимает текстовые форматы, в которых значения разделяются запятыми (CSV) или табуляциями (TSV).</span><span class="sxs-lookup"><span data-stu-id="2c54f-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="2c54f-122">На этапе добавления данных в построителе моделей выберите в раскрывающемся списке источник данных **Файл**.</span><span class="sxs-lookup"><span data-stu-id="2c54f-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="2c54f-123">Нажмите кнопку рядом с текстовым полем **Выберите файл**, найдите и выберите в проводнике нужный файл данных.</span><span class="sxs-lookup"><span data-stu-id="2c54f-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="2c54f-124">Выберите категорию в раскрывающемся списке **Столбец для прогнозирования** (метка).</span><span class="sxs-lookup"><span data-stu-id="2c54f-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="2c54f-125">В раскрывающемся списке **Входные столбцы** (признаки) обязательно отметьте все нужные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="2c54f-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="2c54f-126">На этом настройка файла источника данных для передачи в построитель моделей завершается.</span><span class="sxs-lookup"><span data-stu-id="2c54f-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="2c54f-127">Щелкните ссылку **Обучение**, чтобы перейти к следующему шагу в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="2c54f-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="2c54f-128">Загрузка данных из базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c54f-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="2c54f-129">Построитель моделей поддерживает загрузку данных из локальных и удаленных баз данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c54f-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="2c54f-130">Чтобы загрузить данные из базы данных SQL Server в построитель моделей, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="2c54f-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="2c54f-131">На этапе добавления данных в построителе моделей выберите в раскрывающемся списке источник данных **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c54f-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="2c54f-132">Нажмите кнопку рядом с текстовым полем **Connect to SQL Server database** (Подключение к базе данных SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2c54f-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="2c54f-133">В диалоговом окне **Choose Data** (Выбор данных) выберите **Файл базы данных Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2c54f-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="2c54f-134">Снимите флажок **Всегда использовать этот вариант** и щелкните **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="2c54f-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="2c54f-135">В диалоговом окне **Свойства подключения** щелкните **Обзор** и выберите скачанный MDF-файл.</span><span class="sxs-lookup"><span data-stu-id="2c54f-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="2c54f-136">Нажмите кнопку **ОК**</span><span class="sxs-lookup"><span data-stu-id="2c54f-136">Select **OK**</span></span>
1. <span data-ttu-id="2c54f-137">Выберите имя набора данных из раскрывающегося списка **Имя таблицы**.</span><span class="sxs-lookup"><span data-stu-id="2c54f-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="2c54f-138">В раскрывающемся списке **Столбец для прогнозирования** (метка) выберите категорию данных, для которой вы намерены создать прогноз.</span><span class="sxs-lookup"><span data-stu-id="2c54f-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="2c54f-139">В раскрывающемся списке **Входные столбцы** (признаки) обязательно отметьте все нужные столбцы.</span><span class="sxs-lookup"><span data-stu-id="2c54f-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="2c54f-140">На этом настройка файла источника данных для передачи в построитель моделей завершается.</span><span class="sxs-lookup"><span data-stu-id="2c54f-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="2c54f-141">Щелкните ссылку **Обучение**, чтобы перейти к следующему шагу в построителе моделей.</span><span class="sxs-lookup"><span data-stu-id="2c54f-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="2c54f-142">Настройка файлов данных с изображениями</span><span class="sxs-lookup"><span data-stu-id="2c54f-142">Set up image data files</span></span>

<span data-ttu-id="2c54f-143">Построитель моделей ожидает получить данные изображений в формате файлов JPG или PNG, упорядоченных в папки с именами категорий классификации.</span><span class="sxs-lookup"><span data-stu-id="2c54f-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="2c54f-144">Чтобы загрузить изображения в построитель моделей, укажите путь к одному каталогу верхнего уровня:</span><span class="sxs-lookup"><span data-stu-id="2c54f-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="2c54f-145">Этот каталог верхнего уровня должен содержать по одной вложенной папке для каждой из прогнозируемых категорий.</span><span class="sxs-lookup"><span data-stu-id="2c54f-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="2c54f-146">Каждая вложенная папка содержит файлы изображений, относящиеся к соответствующей категории.</span><span class="sxs-lookup"><span data-stu-id="2c54f-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="2c54f-147">В представленной ниже структуре папок на верхнем уровне расположен каталог *flower_photos*.</span><span class="sxs-lookup"><span data-stu-id="2c54f-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="2c54f-148">В нем есть пять подкаталогов, которые соответствуют категориям для прогнозирования: daisy, dandelion, roses, sunflowers и tulips.</span><span class="sxs-lookup"><span data-stu-id="2c54f-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="2c54f-149">Каждый из этих подкаталогов содержит изображения соответствующей категории.</span><span class="sxs-lookup"><span data-stu-id="2c54f-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a><span data-ttu-id="2c54f-150">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="2c54f-150">Next steps</span></span>

<span data-ttu-id="2c54f-151">В этих руководствах вы найдете процедуры, позволяющие создать приложения машинного обучения с помощью построителя моделей:</span><span class="sxs-lookup"><span data-stu-id="2c54f-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="2c54f-152">Прогнозирование цен с помощью регрессии</span><span class="sxs-lookup"><span data-stu-id="2c54f-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="2c54f-153">Анализ тональности в веб-приложении с использованием двоичной классификации</span><span class="sxs-lookup"><span data-stu-id="2c54f-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="2c54f-154">Если вы обучаете модель с помощью кода, узнайте, как [загружать данные с помощью API-интерфейса ML.NET](load-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="2c54f-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>
