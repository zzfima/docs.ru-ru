---
title: Загрузка данных с множеством столбцов из CSV-файла для обработки с помощью машинного обучения — ML.NET
description: Узнайте, как загружать данные со множеством столбцов из CSV-файла для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: e33fdf1d71b02545e3ea284cc317f5d244c3fc13
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675957"
---
# <a name="load-data-with-many-columns-from-a-csv-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="7f449-103">Загрузка данных с множеством столбцов из CSV-файла для обработки с помощью машинного обучения — ML.NET</span><span class="sxs-lookup"><span data-stu-id="7f449-103">Load data with many columns from a CSV file for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="7f449-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="7f449-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="7f449-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="7f449-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="7f449-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="7f449-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="7f449-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="7f449-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="7f449-108">Данные из текстовых файлов загружаются с помощью `TextLoader`.</span><span class="sxs-lookup"><span data-stu-id="7f449-108">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="7f449-109">Вам нужно указать столбцы данных, их типы и расположение в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="7f449-109">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="7f449-110">Если входной файл содержит много столбцов одного типа, которые всегда используются вместе, они должны считываться как *вектор-столбец*.</span><span class="sxs-lookup"><span data-stu-id="7f449-110">When the input file contains many columns of the same type and always used together, read them as a *vector column*.</span></span> <span data-ttu-id="7f449-111">Такая стратегия позволяет создать схему с очищенными данными без затрат производительности, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7f449-111">This strategy results in a clean data schema and avoids unnecessary performance costs, as shown in the following example:</span></span>

<span data-ttu-id="7f449-112">[Пример файла](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span><span class="sxs-lookup"><span data-stu-id="7f449-112">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv):</span></span>

```console
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
0.28;1.05;-0.24;0.30;-0.99;0.19;0.32;-0.95;-1.19;-0.63;0.75;443.51
```

<span data-ttu-id="7f449-113">Чтение этого файла с помощью `TextLoader`:</span><span class="sxs-lookup"><span data-stu-id="7f449-113">Reading this file using `TextLoader`:</span></span>

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