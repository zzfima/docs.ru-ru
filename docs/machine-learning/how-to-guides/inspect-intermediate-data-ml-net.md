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
# <a name="inspect-intermediate-data-during-processing"></a>Проверка промежуточных данных при обработке

Сведения о проверке промежуточных данных при загрузке, обработке и обучении модели в ML.NET. Промежуточные данные — это выходные данные после каждого этапа конвейера машинного обучения.

Промежуточные данные, аналогичные представленным ниже, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView), в ML.NET можно проверить разными способами.

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

## <a name="convert-idataview-to-ienumerable"></a>Преобразование IDataView в IEnumerable

Одним из самых быстрых способов проверки [`IDataView`](xref:Microsoft.ML.IDataView) является преобразование в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601). Чтобы преобразовать [`IDataView`](xref:Microsoft.ML.IDataView) в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), используйте метод [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).

Для оптимизации производительности установите для параметра `reuseRowObject` значение `true`. Это приведет к отложенному заполнению одного объекта данными из текущей строки при оценке вместо создания объекта для каждой строки в наборе данных.

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

## <a name="accessing-specific-indices-with-ienumerable"></a>Доступ к определенным индексам с помощью IEnumerable

Если вам нужно обратиться лишь к части данных или конкретным индексам, используйте [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) и задайте для параметра `reuseRowObject` значение `false`, чтобы создавать объект для каждой из запрошенных срок в наборе данных. После этого преобразуйте [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) в массив или список.

> [!WARNING]
> Преобразование результата [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) в массив или список загрузит все запрошенные строки [`IDataView`](xref:Microsoft.ML.IDataView) в память, что может негативно повлиять на производительность.

После создания коллекции можно выполнить операции с данными. Приведенный ниже фрагмент кода принимает первые три строки в наборе данных и вычисляет среднюю текущую стоимость.

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

## <a name="inspect-values-in-a-single-column"></a>Проверка значений в одном столбце

В любой момент в процессе создания модели можно обратиться к значениям в отдельном столбце [`IDataView`](xref:Microsoft.ML.IDataView) с использованием метода [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*). Метод [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) возвращает все значения в отдельном столбце как [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a>Проверка значений IDataView по одной строке за раз

[`IDataView`](xref:Microsoft.ML.IDataView) вычисляется в отложенном режиме. Для выполнения итераций по строкам [`IDataView`](xref:Microsoft.ML.IDataView) без преобразования в [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), как показано в предыдущих разделах этого документа, создайте [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor), используя метод [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) и передав [DataViewSchema](xref:Microsoft.ML.DataViewSchema) интерфейса [`IDataView`](xref:Microsoft.ML.IDataView) в качестве параметра. Затем для выполнения итерации по строкам используйте метод курсора [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) вместе с делегатами [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601), чтобы извлечь соответствующие значения из каждого столбца.

> [!IMPORTANT]
> Для повышения производительности векторы в ML.NET используют [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) вместо собственных типов коллекции (то есть `Vector`,`float[]`).

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

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a>Просмотр результата предварительной обработки или обучения с использованием подмножества данных

> [!WARNING]
> Не используйте `Preview` в рабочем коде, потому что он предназначен для отладки и может снизить производительность.

Процесс создания модели является экспериментальным и итеративным. Чтобы просмотреть данные после предварительной обработки или обучения модели машинного обучения на подмножестве данных, используйте метод [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*), возвращающий [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview). Результат представляет собой объект со свойствами `ColumnView` и `RowView`, которые являются [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) и содержат значения в определенном столбце или строке. Укажите число строк, к которым применяется преобразование, с помощью параметра `maxRows`.

![Объект предварительного просмотра отладчика данных](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

Результат проверки [`IDataView`](xref:Microsoft.ML.IDataView) будет похож на приведенный ниже.

![Представление строки предварительного просмотра отладчика данных](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
