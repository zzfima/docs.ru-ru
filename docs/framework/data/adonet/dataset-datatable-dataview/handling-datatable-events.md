---
title: "Обработка событий таблиц данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62f404a5-13ea-4b93-a29f-55b74a16c9d3
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f7ab9d1043fdd1d4d78ec09390f227f297e471c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="handling-datatable-events"></a>Обработка событий таблиц данных
Объект <xref:System.Data.DataTable> предоставляет ряд событий, которые может обрабатывать приложение. В следующей таблице приводится описание событий `DataTable`.  
  
|Событие|Описание|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.Initialized>|Происходит после вызова метода <xref:System.Data.DataTable.EndInit%2A> объекта `DataTable`. Главным образом это событие предназначено для поддержки сценариев во время разработки.|  
|<xref:System.Data.DataTable.ColumnChanged>|Происходит после успешного изменения значения в объекте <xref:System.Data.DataColumn>.|  
|<xref:System.Data.DataTable.ColumnChanging>|Происходит при подаче значения для объекта `DataColumn`.|  
|<xref:System.Data.DataTable.RowChanged>|Происходит после успешного изменения значения `DataColumn` или состояния <xref:System.Data.DataRow.RowState%2A> объекта <xref:System.Data.DataRow> в объекте `DataTable`.|  
|<xref:System.Data.DataTable.RowChanging>|Происходит при подаче изменения для значения `DataColumn` или состояния `RowState` объекта `DataRow` в объекте `DataTable`.|  
|<xref:System.Data.DataTable.RowDeleted>|Происходит после того, как объект `DataRow` в объекте `DataTable` был отмечен, как `Deleted`.|  
|<xref:System.Data.DataTable.RowDeleting>|Происходит перед тем, как объект `DataRow` в объекте `DataTable` будет отмечен как `Deleted`.|  
|<xref:System.Data.DataTable.TableCleared>|Происходит после того, как вызов метода <xref:System.Data.DataTable.Clear%2A> объекта `DataTable` успешно очистил каждый объект `DataRow`.|  
|<xref:System.Data.DataTable.TableClearing>|Происходит после вызова метода `Clear`, но до начала операции `Clear`.|  
|<xref:System.Data.DataTable.TableNewRow>|Происходит после создания нового объекта `DataRow` путем вызова метода `NewRow` объекта `DataTable`.|  
|<xref:System.ComponentModel.MarshalByValueComponent.Disposed>|Происходит, когда объект `DataTable` удаляется `Disposed`. Наследуется от <xref:System.ComponentModel.MarshalByValueComponent>.|  
  
> [!NOTE]
>  Большинство операций, которые добавляют или удаляют строки, не вызывают событий `ColumnChanged` и `ColumnChanging`. Однако метод `ReadXml` вызывает события `ColumnChanged` и `ColumnChanging`, если только свойству `XmlReadMode` не задано значение `DiffGram` или значение `Auto`, когда читаемый XML-документ является `DiffGram`.  
  
> [!WARNING]
>  Изменение данных в объекте `DataSet`, из которого было вызвано событие `RowChanged`, может привести к повреждению данных. При подобном повреждении данных исключение вызвано не будет.  
  
## <a name="additional-related-events"></a>Дополнительные связанные события  
 Свойство <xref:System.Data.DataTable.Constraints%2A> содержит экземпляр <xref:System.Data.ConstraintCollection>. Класс <xref:System.Data.ConstraintCollection> представляет событие <xref:System.Data.ConstraintCollection.CollectionChanged>. Это событие возникает при добавлении, изменении или удалении ограничения из коллекции `ConstraintCollection`.  
  
 Свойство <xref:System.Data.DataTable.Columns%2A> содержит экземпляр <xref:System.Data.DataColumnCollection>. Класс `DataColumnCollection` представляет событие <xref:System.Data.DataColumnCollection.CollectionChanged>. Это событие возникает при добавлении, изменении или удалении из коллекции `DataColumn` объекта `DataColumnCollection`. Среди изменений, которые могут вызвать возникновение этого события, - изменения имени, типа, выражения или порядкового номера столбца.  
  
 Свойство <xref:System.Data.DataSet.Tables%2A> объекта <xref:System.Data.DataSet> содержит экземпляр <xref:System.Data.DataTableCollection>. Класс `DataTableCollection` вызывает события `CollectionChanged` и `CollectionChanging`. Эти события возникают при добавлении или удалении из коллекции `DataTable` объекта `DataSet`.  
  
 Внесение изменений в объекты `DataRows` также могут вызвать события для ассоциированного объекта <xref:System.Data.DataView>. Класс `DataView` вызывает событие <xref:System.Data.DataView.ListChanged>, которое возникает при изменении значения `DataColumn` или при изменении композиции или порядка сортировки представления. Класс <xref:System.Data.DataRowView> вызывает событие <xref:System.Data.DataRowView.PropertyChanged>, которое возникает при изменении значения ассоциированного объекта `DataColumn`.  
  
## <a name="sequence-of-operations"></a>Последовательность операций  
 При добавлении, изменении или удалении объекта `DataRow` надо выполнить следующую последовательность операций.  
  
1.  Создайте предложенную запись и внесите любые изменения.  
  
2.  Проверьте ограничения для столбцов, не входящих в выражения.  
  
3.  Вызовите событие `RowChanging` или `RowDeleting`, в зависимости от ситуации.  
  
4.  Сделайте предложенную запись текущей.  
  
5.  Обновите все ассоциированные индексы.  
  
6.  Вызовите события `ListChanged` для ассоциированных объектов `DataView`, а также события `PropertyChanged` для ассоциированных объектов `DataRowView`.  
  
7.  Оцените все столбцы выражения, но отложите проверку любых ограничений для этих столбцов.  
  
8.  Вызовите события `ListChanged` для ассоциированных объектов `DataView`, а также события `PropertyChanged` для ассоциированных объектов `DataRowView`, затронутых оценками столбцов выражения.  
  
9. Вызовите событие `RowChanged` или `RowDeleted`, в зависимости от ситуации.  
  
10. Проверьте ограничения на столбцы выражения.  
  
> [!NOTE]
>  Внесение изменений в столбцы выражений никогда не вызывает события `DataTable`. Внесение изменений в столбцы выражений вызывает только события `DataView` и `DataRowView`. Столбцы выражения могут иметь зависимости от нескольких других столбцов, их оценка во время одной операции `DataRow` может производиться несколько раз. События вызываются при вычислении каждого выражения, а при работе со столбцами выражений одна операция `DataRow` может вызвать несколько событий `ListChanged` и `PropertyChanged`, возможно, с несколькими событиями для одного столбца выражений.  
  
> [!WARNING]
>  Не вызывайте исключение <xref:System.NullReferenceException> в обработчике события `RowChanged`. Если исключение <xref:System.NullReferenceException> вызывается в пределах события `RowChanged` объекта `DataTable`, объект `DataTable` будет поврежден.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется, как создавать обработчики событий для событий `RowChanged`, `RowChanging`, `RowDeleted`, `RowDeleting`, `ColumnChanged`, `ColumnChanging`, `TableNewRow`, `TableCleared` и `TableClearing`. Каждый обработчик события при возникновении события отображает выводимые данные в консольном окне.  
  
 [!code-csharp[DataWorks DataTable.Events#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.Events/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.Events#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.Events/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Обработка событий DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 [Обработка событий наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
