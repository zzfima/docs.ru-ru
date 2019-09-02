---
title: Слияние содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e9309a-3ebb-4a9c-9d78-21c4e2bafc5b
ms.openlocfilehash: e5a8040a803fbc9b098fc1b56e0f5d837c4cdb94
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203361"
---
# <a name="merging-dataset-contents"></a>Слияние содержимого набора данных

Метод <xref:System.Data.DataSet.Merge%2A> можно использовать для объединения содержимого массива <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или <xref:System.Data.DataRow> с существующим `DataSet`. Несколько факторов и параметров влияют на то, как новые данные объединяются с существующим `DataSet`.

## <a name="primary-keys"></a>Первичные ключи

Если таблица, получающая в результате слияния новые данные и схему, имеет первичный ключ, новые строки входных данных сравниваются с существующими строками, имеющими такие же значения первичного ключа <xref:System.Data.DataRowVersion.Original>, что и во входных данных. Если столбцы из входной схемы соответствуют столбцам существующей схемы, данные в существующих строках изменяются. Столбцы, не соответствующие существующей схеме, либо пропускаются, либо добавляются на основании параметра <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A>. Новые строки со значениями первичного ключа, которые не соответствуют существующим строкам, добавляются к существующей таблице.

Если входные или существующие строки имеют состояние <xref:System.Data.DataRowState.Added>, значения их первичных ключей согласуются с использованием значения первичного ключа <xref:System.Data.DataRowVersion.Current> строки `Added`, т. к. не существует версии строки `Original`.

Если входная таблица и существующая таблица содержат столбцы с одинаковым именем, но разных типов данных, возникает исключение и инициируется событие <xref:System.Data.DataSet.MergeFailed> объекта `DataSet`. Если входная таблица и существующая таблица обе имеют определенные ключи, но первичные ключи относятся к разным столбцам, возникает исключение и инициируется событие `MergeFailed` объекта `DataSet`.

Если таблица, получающая новые данные в результате объединения, не имеет первичного ключа, новые строки входных данных не могут быть сопоставлены существующим строкам в таблице и вместо этого присоединяются к существующей таблице.

## <a name="table-names-and-namespaces"></a>Имена таблиц и пространства имен

Объектам <xref:System.Data.DataTable> может быть, если необходимо, присвоено значение свойства <xref:System.Data.DataTable.Namespace%2A>. Когда присваиваются значения <xref:System.Data.DataTable.Namespace%2A>, <xref:System.Data.DataSet> может содержать несколько объектов <xref:System.Data.DataTable> с одинаковым значением <xref:System.Data.DataTable.TableName%2A>. Во время операции слияния и <xref:System.Data.DataTable.TableName%2A>, и <xref:System.Data.DataTable.Namespace%2A> используются для идентификации цели слияния. Если <xref:System.Data.DataTable.Namespace%2A> не назначено, только <xref:System.Data.DataTable.TableName%2A> используется для идентификации цели слияния.

> [!NOTE]
> Это поведение в .NET Framework версии 2.0 изменяется. В версии 1.1 пространства имен поддерживались, но во время операций слияния не учитывались. По этой причине <xref:System.Data.DataSet>, который использует значения свойства <xref:System.Data.DataTable.Namespace%2A>, будет иметь разные характеристики в зависимости от того, какая версия .NET Framework выполняется. Например, предположим, имеются два `DataSets`, содержащие `DataTables` с одинаковыми значениями свойства <xref:System.Data.DataTable.TableName%2A>, но с разными значениями свойства <xref:System.Data.DataTable.Namespace%2A>. В .NET Framework версии 1.1 разные имена <xref:System.Data.DataTable.Namespace%2A> пропускаются, когда объединяются два объекта <xref:System.Data.DataSet>. Однако, начиная с версии 2.0, слияние приводит к созданию в целевом объекте `DataTables` двух новых объектов <xref:System.Data.DataSet>. Исходные таблицы `DataTables` объединением не затрагиваются.

## <a name="preservechanges"></a>Флаг PreserveChanges

Когда `DataSet`, `DataTable` или `DataRow` передается в метод `Merge`, можно включить необязательные параметры, указывающие, сохранять ли изменения в существующем объекте `DataSet` и как обрабатывать элементы новой схемы в исходных данных. Первым из этих параметров после входных данных является логический флаг <xref:System.Data.LoadOption.PreserveChanges>, который задает, сохранять ли изменения в существующем `DataSet`. Если флаг `PreserveChanges` установлен в `true`, входные значения не переопределяют существующие значения в версии `Current` текущей строки. Если флаг `PreserveChanges` установлен в `false`, входные значения переопределяют существующие значения в версии `Current` текущей строки. Если флаг `PreserveChanges` не задан, по умолчанию он устанавливается в `false`. Дополнительные сведения о версиях строк см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).

Если `PreserveChanges` имеет значение `true`, данные из существующей строки сохраняются в версии <xref:System.Data.DataRowVersion.Current> текущей строки, в то время как данные из версии <xref:System.Data.DataRowVersion.Original> существующей строки переопределяются данными из версии `Original` входной строки. <xref:System.Data.DataRow.RowState%2A> существующей строки установлен в <xref:System.Data.DataRowState.Modified>. Применяются следующие исключения:

- Если существующая строка имеет версию `RowState``Deleted`, это `RowState` остается `Deleted` и не устанавливается в `Modified`. В этом случае данные из входной строки будут сохраняться в версии `Original` существующей строки, переопределяя версию `Original` существующей строки (если только входная строка не имеет `RowState`, равное `Added`).

- Если входная строка имеет состояние `RowState`, равное `Added`, данные из версии `Original` существующей строки не переопределяются данными из входной строки, т. к. входная строка не имеет версии `Original`.

Если `PreserveChanges` равно `false`, версии строк `Current` и `Original` в существующей строке переопределяются данными из входной строки, а состояние `RowState` существующей строки устанавливается в состояние `RowState` входной строки. Применяются следующие исключения:

- Если входная строка имеет значение `RowState`, равное `Unchanged`, а существующая строка имеет значение `RowState`, равное `Modified`, `Deleted` или `Added`, состояние `RowState` существующей строки устанавливается в `Modified`.

- Если входная строка имеет состояние `RowState`, равное `Added`, а существующая строка имеет состояние `RowState`, равное `Unchanged`, `Modified` или `Deleted`, состояние `RowState` существующей строки устанавливается в `Modified`. Также данные из версии `Original` существующей строки не переопределяются данными из входной строки, т. к. входная строка не имеет версии `Original`.

## <a name="missingschemaaction"></a>Параметр MissingSchemaAction

Можно использовать необязательный параметр <xref:System.Data.MissingSchemaAction> метода `Merge` для задания того, как `Merge` будет обрабатывать элементы схемы во входных данных, не являющихся частью существующего объекта `DataSet`.

В следующей таблице описываются параметры для `MissingSchemaAction`.

|Параметр MissingSchemaAction|Описание|
|--------------------------------|-----------------|
|<xref:System.Data.MissingSchemaAction.Add>|Добавление новых данных схемы в объект `DataSet` и заполнение новых столбцов входными значениями. Это значение по умолчанию.|
|<xref:System.Data.MissingSchemaAction.AddWithKey>|Добавление новых данных схемы и первичного ключа в объект `DataSet` и заполнение новых столбцов входными значениями.|
|<xref:System.Data.MissingSchemaAction.Error>|Инициация исключения, если встречаются несовпадающие данные схемы.|
|<xref:System.Data.MissingSchemaAction.Ignore>|Пропуск новых данных схемы.|

## <a name="constraints"></a>Ограничения

При выполнении метода `Merge` ограничения не проверяются, пока все новые данные не будут добавлены в существующий объект `DataSet`. После добавления данных ограничения принудительно применяются на текущих значениях в объекте `DataSet`. Необходимо быть уверенным в том, что код обрабатывает все исключения, которые могут инициироваться из-за нарушений ограничений.

Рассмотрим случай, когда существующая строка в `DataSet` является строкой `Unchanged` со значением первичного ключа, равным 1. Во время выполнения операции слияния с входной строкой `Modified` со значением первичного ключа `Original`, равным 2, и значением первичного ключа `Current`, равным 1, существующая строка и входная строка не считаются совпадающими, так как различаются значения первичных ключей `Original`. Однако после завершения объединения и проверки ограничений появится исключение, т. к. значения первичного ключа `Current` нарушают ограничение уникальности для столбца первичного ключа.

> [!NOTE]
> Если строки вставляются в таблицу базы данных, содержащую столбец, автоматически увеличивающий свое значение, например столбец идентификаторов, то возвращаемое вставкой значение столбца идентификаторов может не совпадать со значением в объекте `DataSet`, в результате чего возвращаемые строки не объединяются, а присоединяются. Дополнительные сведения см. в разделе [Получение значений Identity или](../retrieving-identity-or-autonumber-values.md)автонумерации.

В следующем примере кода два `DataSet` объекта с разными схемами объединяются в одну `DataSet` с объединенными схемами двух входящих `DataSet` объектов.

[!code-csharp[DataWorks DataSet.Merge#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.Merge#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/VB/source.vb#1)]

В следующем примере кода берется существующий объект `DataSet` с обновлениями и эти обновления передаются в `DataAdapter`, чтобы выполнить обработку в источнике данных. Затем результаты объединяются в исходный объект `DataSet`. После отклонения изменений, в результате которых возникла ошибка, объединенные изменения фиксируются при помощи `AcceptChanges`.

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#1)]

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#2)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#2)]

## <a name="see-also"></a>См. также

- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Состояния и версии строк](row-states-and-row-versions.md)
- [Объекты DataAdapter и DataReader](../dataadapters-and-datareaders.md)
- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Извлечение идентификации или значений автонумерации](../retrieving-identity-or-autonumber-values.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
