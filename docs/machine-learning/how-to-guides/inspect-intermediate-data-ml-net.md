---
title: Проверка промежуточных данных при обработке ML.NET
description: Сведения о проверке промежуточных данных при конвейерной загрузке, обработке и обучении модели машинного обучения в ML.NET.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 11df1d5caaa7b7974360d863f85afbff18985e47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977092"
---
# <a name="inspect-intermediate-data-during-processing"></a><span data-ttu-id="3333b-103">Проверка промежуточных данных при обработке</span><span class="sxs-lookup"><span data-stu-id="3333b-103">Inspect intermediate data during processing</span></span>

<span data-ttu-id="3333b-104">Сведения о проверке промежуточных данных при загрузке, обработке и обучении модели в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="3333b-104">Learn how to inspect intermediate data during loading, processing, and model training steps in ML.NET.</span></span> <span data-ttu-id="3333b-105">Промежуточные данные — это выходные данные после каждого этапа конвейера машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="3333b-105">Intermediate data is the output of each stage in the machine learning pipeline.</span></span>

<span data-ttu-id="3333b-106">Промежуточные данные, аналогичные представленным ниже, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView), в ML.NET можно проверить разными способами.</span><span class="sxs-lookup"><span data-stu-id="3333b-106">Intermediate data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="3333b-107">Преобразование IDataView в IEnumerable</span><span class="sxs-lookup"><span data-stu-id="3333b-107">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="3333b-108">Одним из самых быстрых способов проверки [`IDataView`](xref:Microsoft.ML.IDataView) является преобразование в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="3333b-108">One of the quickest ways to inspect an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="3333b-109">Чтобы преобразовать [`IDataView`](xref:Microsoft.ML.IDataView) в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), используйте метод [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).</span><span class="sxs-lookup"><span data-stu-id="3333b-109">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

<span data-ttu-id="3333b-110">Для оптимизации производительности установите для параметра `reuseRowObject` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3333b-110">To optimize performance, set `reuseRowObject` to `true`.</span></span> <span data-ttu-id="3333b-111">Это приведет к отложенному заполнению одного объекта данными из текущей строки при оценке вместо создания объекта для каждой строки в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="3333b-111">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

## <a name="accessing-specific-indices-with-ienumerable"></a><span data-ttu-id="3333b-112">Доступ к определенным индексам с помощью IEnumerable</span><span class="sxs-lookup"><span data-stu-id="3333b-112">Accessing specific indices with IEnumerable</span></span>

<span data-ttu-id="3333b-113">Если вам нужно обратиться лишь к части данных или конкретным индексам, используйте [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) и задайте для параметра `reuseRowObject` значение `false`, чтобы создавать объект для каждой из запрошенных срок в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="3333b-113">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="3333b-114">После этого преобразуйте [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) в массив или список.</span><span class="sxs-lookup"><span data-stu-id="3333b-114">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="3333b-115">Преобразование результата [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) в массив или список загрузит все запрошенные строки [`IDataView`](xref:Microsoft.ML.IDataView) в память, что может негативно повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="3333b-115">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="3333b-116">После создания коллекции можно выполнить операции с данными.</span><span class="sxs-lookup"><span data-stu-id="3333b-116">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="3333b-117">Приведенный ниже фрагмент кода принимает первые три строки в наборе данных и вычисляет среднюю текущую стоимость.</span><span class="sxs-lookup"><span data-stu-id="3333b-117">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
```

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="3333b-118">Проверка значений в одном столбце</span><span class="sxs-lookup"><span data-stu-id="3333b-118">Inspect values in a single column</span></span>

<span data-ttu-id="3333b-119">В любой момент в процессе создания модели можно обратиться к значениям в отдельном столбце [`IDataView`](xref:Microsoft.ML.IDataView) с использованием метода [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="3333b-119">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="3333b-120">Метод [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) возвращает все значения в отдельном столбце как [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="3333b-120">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="3333b-121">Проверка значений IDataView по одной строке за раз</span><span class="sxs-lookup"><span data-stu-id="3333b-121">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="3333b-122">[`IDataView`](xref:Microsoft.ML.IDataView) вычисляется в отложенном режиме.</span><span class="sxs-lookup"><span data-stu-id="3333b-122">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="3333b-123">Для выполнения итераций по строкам [`IDataView`](xref:Microsoft.ML.IDataView) без преобразования в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), как показано в предыдущих разделах этого документа, создайте [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor), используя метод [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) и передав [DataViewSchema](xref:Microsoft.ML.DataViewSchema) интерфейса [`IDataView`](xref:Microsoft.ML.IDataView) в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="3333b-123">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="3333b-124">Затем для выполнения итерации по строкам используйте метод курсора [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) вместе с делегатами [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601), чтобы извлечь соответствующие значения из каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="3333b-124">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3333b-125">Для повышения производительности векторы в ML.NET используют [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) вместо собственных типов коллекции (то есть `Vector`,`float[]`).</span><span class="sxs-lookup"><span data-stu-id="3333b-125">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span>

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);

    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="3333b-126">Просмотр результата предварительной обработки или обучения с использованием подмножества данных</span><span class="sxs-lookup"><span data-stu-id="3333b-126">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="3333b-127">Не используйте `Preview` в рабочем коде, потому что он предназначен для отладки и может снизить производительность.</span><span class="sxs-lookup"><span data-stu-id="3333b-127">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="3333b-128">Процесс создания модели является экспериментальным и итеративным.</span><span class="sxs-lookup"><span data-stu-id="3333b-128">The model building process is experimental and iterative.</span></span> <span data-ttu-id="3333b-129">Чтобы просмотреть данные после предварительной обработки или обучения модели машинного обучения на подмножестве данных, используйте метод [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*), возвращающий [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span><span class="sxs-lookup"><span data-stu-id="3333b-129">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="3333b-130">Результат представляет собой объект со свойствами `ColumnView` и `RowView`, которые являются [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) и содержат значения в определенном столбце или строке.</span><span class="sxs-lookup"><span data-stu-id="3333b-130">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="3333b-131">Укажите число строк, к которым применяется преобразование, с помощью параметра `maxRows`.</span><span class="sxs-lookup"><span data-stu-id="3333b-131">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![Объект предварительного просмотра отладчика данных](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="3333b-133">Результат проверки [`IDataView`](xref:Microsoft.ML.IDataView) будет похож на приведенный ниже.</span><span class="sxs-lookup"><span data-stu-id="3333b-133">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![Представление строки предварительного просмотра отладчика данных](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
