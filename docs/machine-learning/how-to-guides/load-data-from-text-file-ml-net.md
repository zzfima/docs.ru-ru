---
title: Загрузка данных из текстовых файлов для обработки с помощью машинного обучения — ML.NET
description: Узнайте, как загружать данные из текстового файла для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 7b1e8d3fb6047059c14ec3db8450364a84497219
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156562"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="4698a-103">Загрузка данных из текстовых файлов для обработки с помощью машинного обучения — ML.NET</span><span class="sxs-lookup"><span data-stu-id="4698a-103">Load data from a text file for machine learning processing - ML.NET</span></span>

<span data-ttu-id="4698a-104">Данные из текстовых файлов загружаются с помощью `TextLoader`.</span><span class="sxs-lookup"><span data-stu-id="4698a-104">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="4698a-105">Вам нужно указать столбцы данных, их типы и расположение в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="4698a-105">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="4698a-106">Обратите внимание, что вполне приемлемо считывать отдельные столбцы из файла или один и тот же столбец несколько раз.</span><span class="sxs-lookup"><span data-stu-id="4698a-106">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="4698a-107">[Пример файла](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="4698a-107">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

<span data-ttu-id="4698a-108">Загрузка данных из текстового файла:</span><span class="sxs-lookup"><span data-stu-id="4698a-108">To load the data from a text file:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();
TextLoader textLoader;

// Create the reader: define the data columns and where to find them in the text file.
textLoader = mlContext.Data.TextReader(new TextLoader.Arguments()
{
    Separator = ",",
    HasHeader = true,
    Column = new[]
                {
                    new TextLoader.Column("VendorId", DataKind.Text, 0),
                    new TextLoader.Column("RateCode", DataKind.Text, 1),
                    new TextLoader.Column("PassengerCount", DataKind.R4, 2),
                    new TextLoader.Column("TripTime", DataKind.R4, 3),
                    new TextLoader.Column("TripDistance", DataKind.R4, 4),
                    new TextLoader.Column("PaymentType", DataKind.Text, 5),
                    new TextLoader.Column("FareAmount", DataKind.R4, 6)
                }
}
);

// Now read the file (remember though, readers are lazy, so the reading will happen when the data is accessed).
var data = textLoader.Read(dataPath);
```