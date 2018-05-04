---
title: Добавление новой таблицы данных в набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 3554790bb65310031b00ca5fb320aa4c111e1e11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="adding-a-datatable-to-a-dataset"></a>Добавление новой таблицы данных в набор данных
ADO.NET позволяет создавать объекты <xref:System.Data.DataTable> и добавлять их к существующему <xref:System.Data.DataSet>. Можно задать данные ограничения для <xref:System.Data.DataTable>, используя свойства <xref:System.Data.DataTable.PrimaryKey%2A> и <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать объект <xref:System.Data.DataSet>, добавить новый объект <xref:System.Data.DataTable> к <xref:System.Data.DataSet>, а затем добавить к таблице три объекта <xref:System.Data.DataColumn>. В конце код задает один столбец в качестве столбца первичного ключа.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Учет регистра  
 В <xref:System.Data.DataSet> могут существовать две или несколько таблиц или связей, имеющие одинаковые имена, которые, тем не менее, состоят из символов с разными регистрами. В таких случаях ссылки по имени на таблицы и связи задаются с учетом регистра. Например если <xref:System.Data.DataSet> **набора данных** содержит таблицы **Table1** и **table1**, необходимо предоставить ссылки, **Table1** по имени **dataSet.Tables["Table1"]**, и **table1** как **dataSet.Tables["table1"]**. Попытка сослаться на любую из таблиц как **dataSet.Tables["TABLE1"]** создается исключение.  
  
 Это правило учета регистра не применяется, если только одна таблица или связь имеет какое-то определенное имя. Например, если <xref:System.Data.DataSet> имеет только **Table1**, можно ссылаться с использованием **dataSet.Tables["TABLE1"]**.  
  
> [!NOTE]
>  Указанное правило применяется без учета значения свойства <xref:System.Data.DataSet.CaseSensitive%2A> объекта <xref:System.Data.DataSet>. Свойство <xref:System.Data.DataSet.CaseSensitive%2A> применяется к данным в <xref:System.Data.DataSet> и затрагивает сортировку, поиск, фильтрацию, предписание ограничений и т. д.  
  
## <a name="namespace-support"></a>Поддержка пространства имен  
 В версиях ADO.NET, выпущенных до версии 2.0, две таблицы не могли иметь одинаковое имя, даже если находились в разных пространствах имен. Это ограничение было снято в ADO.NET 2.0. Набор данных <xref:System.Data.DataSet> может содержать две таблицы, имеющие одинаковое значение свойства <xref:System.Data.DataTable.TableName%2A>, но различные значения свойства <xref:System.Data.DataTable.Namespace%2A>.  
  
## <a name="see-also"></a>См. также  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
