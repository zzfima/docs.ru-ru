---
title: "Объединение содержимого DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5e9309a-3ebb-4a9c-9d78-21c4e2bafc5b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Объединение содержимого DataSet
Метод <xref:System.Data.DataSet.Merge%2A> можно использовать для объединения содержимого массива <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или <xref:System.Data.DataRow> с существующим `DataSet`.  Несколько факторов и параметров влияют на то, как новые данные объединяются с существующим `DataSet`.  
  
## Первичные ключи  
 Если таблица, получающая в результате объединения новые данные и схему, имеет первичный ключ, новые строки входных данных сравниваются с существующими строками, имеющими такие же значения первичного ключа <xref:System.Data.DataRowVersion>, что и во входных данных.  Если столбцы из входной схемы соответствуют столбцам существующей схемы, данные в существующих строках изменяются.  Столбцы, не соответствующие существующей схеме, либо пропускаются, либо добавляются на основании параметра <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A>.  Новые строки со значениями первичного ключа, которые не соответствуют существующим строкам, добавляются к существующей таблице.  
  
 Если входные или существующие строки имеют состояние <xref:System.Data.DataRowState>, значения их первичных ключей согласуются с использованием значения первичного ключа <xref:System.Data.DataRowVersion> строки `Added`, т. к. не существует версии строки `Original`.  
  
 Если входная таблица и существующая таблица содержат столбцы с одинаковым именем, но разных типов данных, возникает исключение и инициируется событие <xref:System.Data.DataSet.MergeFailed> объекта `DataSet`.  Если входная таблица и существующая таблица обе имеют определенные ключи, но первичные ключи относятся к разным столбцам, возникает исключение и инициируется событие `MergeFailed` объекта `DataSet`.  
  
 Если таблица, получающая новые данные в результате объединения, не имеет первичного ключа, новые строки входных данных не могут быть сопоставлены существующим строкам в таблице и вместо этого присоединяются к существующей таблице.  
  
## Имена таблиц и пространства имен  
 Объектам <xref:System.Data.DataTable> может быть, если необходимо, присвоено значение свойства <xref:System.Data.DataTable.Namespace%2A>.  Когда присваиваются значения <xref:System.Data.DataTable.Namespace%2A>, <xref:System.Data.DataSet> может содержать несколько объектов <xref:System.Data.DataTable> с одинаковым значением <xref:System.Data.DataTable.TableName%2A>.  Во время операции объединения и <xref:System.Data.DataTable.TableName%2A>, и <xref:System.Data.DataTable.Namespace%2A> используются для идентификации цели объединения.  Если <xref:System.Data.DataTable.Namespace%2A> не назначено, только <xref:System.Data.DataTable.TableName%2A> используется для идентификации цели объединения.  
  
> [!NOTE]
>  Это поведение в .NET Framework версии 2.0 изменяется.  В версии 1.1 пространства имен поддерживались, но во время операций объединения не учитывались.  По этой причине <xref:System.Data.DataSet>, который использует значения свойства <xref:System.Data.DataTable.Namespace%2A>, будет иметь разные характеристики в зависимости от того, какая версия .NET Framework выполняется.  Например, предположим, имеются два `DataSets`, содержащие `DataTables` с одинаковыми значениями свойства <xref:System.Data.DataTable.TableName%2A>, но с разными значениями свойства <xref:System.Data.DataTable.Namespace%2A>.  В .NET Framework версии 1.1 разные имена <xref:System.Data.DataTable.Namespace%2A> пропускаются, когда объединяются два объекта <xref:System.Data.DataSet>.  Однако, начиная с версии 2.0, слияние приводит к созданию в целевом объекте <xref:System.Data.DataSet> двух новых объектов `DataTables`.  Исходные таблицы `DataTables` объединением не затрагиваются.  
  
## Флаг PreserveChanges  
 Когда `DataSet`, `DataTable` или `DataRow` передается в метод `Merge`, можно включить необязательные параметры, указывающие, сохранять ли изменения в существующем объекте `DataSet` и как обрабатывать элементы новой схемы в исходных данных.  Первым из этих параметров после входных данных является логический флаг <xref:System.Data.LoadOption>, который задает, сохранять ли изменения в существующем `DataSet`.  Если флаг `PreserveChanges` установлен в `true`, входные значения не переопределяют существующие значения в версии `Current` текущей строки.  Если флаг `PreserveChanges` установлен в `false`, входные значения переопределяют существующие значения в версии `Current` текущей строки.  Если флаг `PreserveChanges` не задан, по умолчанию он устанавливается в `false`.  Дополнительные сведения о версиях строк см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Если `PreserveChanges` имеет значение `true`, данные из существующей строки сохраняются в версии <xref:System.Data.DataRowVersion> текущей строки, в то время как данные из версии <xref:System.Data.DataRowVersion> существующей строки переопределяются данными из версии `Original` входной строки.  <xref:System.Data.DataRow.RowState%2A> существующей строки установлен в <xref:System.Data.DataRowState>.  Применяются следующие исключения:  
  
-   Если существующая строка имеет версию `RowState` `Deleted`, это `RowState` остается `Deleted` и не устанавливается в `Modified`.  В этом случае данные из входной строки будут сохраняться в версии `Original` существующей строки, переопределяя версию `Original` существующей строки \(если только входная строка не имеет `RowState`, равное `Added`\).  
  
-   Если входная строка имеет состояние `RowState`, равное `Added`, данные из версии `Original` существующей строки не переопределяются данными из входной строки, т. к. входная строка не имеет версии `Original`.  
  
 Если `PreserveChanges` равно `false`, версии строк `Current` и `Original` в существующей строке переопределяются данными из входной строки, а состояние `RowState` существующей строки устанавливается в состояние `RowState` входной строки.  Применяются следующие исключения:  
  
-   Если входная строка имеет значение `RowState`, равное `Unchanged`, а существующая строка имеет значение `RowState`, равное `Modified`, `Deleted` или `Added`, состояние `RowState` существующей строки устанавливается в `Modified`.  
  
-   Если входная строка имеет состояние `RowState`, равное `Added`, а существующая строка имеет состояние `RowState`, равное `Unchanged`, `Modified` или `Deleted`, состояние `RowState` существующей строки устанавливается в `Modified`.  Также данные из версии `Original` существующей строки не переопределяются данными из входной строки, т. к. входная строка не имеет версии `Original`.  
  
## Параметр MissingSchemaAction  
 Можно использовать необязательный параметр <xref:System.Data.MissingSchemaAction> метода `Merge` для задания того, как `Merge` будет обрабатывать элементы схемы во входных данных, не являющихся частью существующего объекта `DataSet`.  
  
 В следующей таблице описываются параметры для `MissingSchemaAction`.  
  
|Параметр MissingSchemaAction|Описание|  
|----------------------------------|--------------|  
|<xref:System.Data.MissingSchemaAction>|Добавление новых данных схемы в объект `DataSet` и заполнение новых столбцов входными значениями.  Это значение по умолчанию.|  
|<xref:System.Data.MissingSchemaAction>|Добавление новых данных схемы и первичного ключа в объект `DataSet` и заполнение новых столбцов входными значениями.|  
|<xref:System.Data.MissingSchemaAction>|Инициация исключения, если встречаются несовпадающие данные схемы.|  
|<xref:System.Data.MissingSchemaAction>|Пропуск новых данных схемы.|  
  
## Ограничения  
 При выполнении метода `Merge` ограничения не проверяются, пока все новые данные не будут добавлены в существующий объект `DataSet`.  После добавления данных ограничения принудительно применяются на текущих значениях в объекте `DataSet`.  Необходимо быть уверенным в том, что код обрабатывает все исключения, которые могут инициироваться из\-за нарушений ограничений.  
  
 Рассмотрим случай, когда существующая строка в `DataSet` является строкой `Unchanged` со значением первичного ключа, равным 1.  Во время выполнения операции слияния с входной строкой `Modified` со значением первичного ключа `Original`, равным 2, и значением первичного ключа `Current`, равным 1, существующая строка и входная строка не считаются совпадающими, так как различаются значения первичных ключей `Original`.  Однако после завершения объединения и проверки ограничений появится исключение, т. к. значения первичного ключа `Current` нарушают ограничение уникальности для столбца первичного ключа.  
  
> [!NOTE]
>  Если строки вставляются в таблицу базы данных, содержащую столбец, автоматически увеличивающий свое значение, например столбец идентификаторов, то возвращаемое вставкой значение столбца идентификаторов может не совпадать со значением в объекте `DataSet`, в результате чего возвращаемые строки не объединяются, а присоединяются.  Для получения дополнительной информации см. [Получение значений идентификаторов или автонумерации](../../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).  
  
 В следующем примере кода два объекта `DataSet` с разными схемами объединяются в один объект `DataSet` с объединенными схемами двух входных объектов `DataSet`.  
  
 [!code-csharp[DataWorks DataSet.Merge#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/CS/source.cs#1)]
 [!code-vb[DataWorks DataSet.Merge#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/VB/source.vb#1)]  
  
 В следующем примере кода берется существующий объект `DataSet` с обновлениями и эти обновления передаются в `DataAdapter`, чтобы выполнить обработку в источнике данных.  Затем результаты объединяются в исходный объект `DataSet`.  После отклонения изменений, в результате которых возникла ошибка, объединенные изменения фиксируются при помощи `AcceptChanges`.  
  
 [!code-csharp[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#1)]
 [!code-vb[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#1)]  
  
 [!code-csharp[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#2)]
 [!code-vb[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#2)]  
  
## См. также  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)   
 [Объекты DataAdapter и DataReader](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Получение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Получение значений идентификаторов или автонумерации](../../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)