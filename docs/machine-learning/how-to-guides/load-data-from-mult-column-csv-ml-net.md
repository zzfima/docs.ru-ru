---
title: Загрузка данных с множеством столбцов из CSV-файла для обработки с помощью машинного обучения — ML.NET
description: Узнайте, как загружать данные со множеством столбцов из CSV-файла для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b295653d1bd3a955c2e6da929dc8f2d4d0a4c14d
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091972"
---
# <a name="load-data-with-many-columns-from-a-csv-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="90dee-103">Загрузка данных с множеством столбцов из CSV-файла для обработки с помощью машинного обучения — ML.NET</span><span class="sxs-lookup"><span data-stu-id="90dee-103">Load data with many columns from a CSV file for machine learning processing - ML.NET</span></span>

<span data-ttu-id="90dee-104">Данные из текстовых файлов загружаются с помощью `TextLoader`.</span><span class="sxs-lookup"><span data-stu-id="90dee-104">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="90dee-105">Вам нужно указать столбцы данных, их типы и расположение в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="90dee-105">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="90dee-106">Если входной файл содержит много столбцов одного типа, которые всегда используются вместе, они должны считываться как *вектор-столбец*.</span><span class="sxs-lookup"><span data-stu-id="90dee-106">When the input file contains many columns of the same type and always used together, read them as a *vector column*.</span></span> <span data-ttu-id="90dee-107">Такая стратегия позволяет создать схему с очищенными данными без затрат производительности, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="90dee-107">This strategy results in a clean data schema and avoids unnecessary performance costs, as shown in the following example:</span></span>

<span data-ttu-id="90dee-108">[Пример файла](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span><span class="sxs-lookup"><span data-stu-id="90dee-108">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span></span>

```console
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
0.28;1.05;-0.24;0.30;-0.99;0.19;0.32;-0.95;-1.19;-0.63;0.75;443.51
```

<span data-ttu-id="90dee-109">Чтение этого файла с помощью `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="90dee-109">Reading this file using `TextLoader`:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
    // We read the first 10 values as a single float vector.
        new TextLoader.Column("FeatureVector",DataKind.R4,0,9),
        // Separately, read the target variable.
        new TextLoader.Column("Target",DataKind.R4,10)
    },
    // Default separator is tab, but we need a semicolon.
    separatorChar: ';',
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```    