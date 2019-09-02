---
title: Добавление отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: fde1e2ace09e31234d199876ae7f063e01e7a7e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203978"
---
# <a name="adding-datarelations"></a>Добавление отношений DataRelation
В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.  
  
 Аргументы, необходимые для создания **DataRelation** , — это имя создаваемого объекта **DataRelation** , а также массив из одной или нескольких <xref:System.Data.DataColumn> ссылок на столбцы, которые служат в качестве родительских и дочерних столбцов связи. После создания объекта **DataRelation**его можно использовать для перехода между таблицами и получения значений.  
  
 Добавление **DataRelation** <xref:System.Data.DataSet> в добавляет по умолчанию объект <xref:System.Data.UniqueConstraint> в родительскую таблицу и <xref:System.Data.ForeignKeyConstraint> в дочернюю таблицу. Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [ограничения DataTable](datatable-constraints.md).  
  
 В следующем примере кода создается **отношение DataRelation** с использованием двух <xref:System.Data.DataTable> объектов в. <xref:System.Data.DataSet> Каждый <xref:System.Data.DataTable> содержит столбец с именем **CustID**, который служит связью между двумя <xref:System.Data.DataTable> объектами. В примере добавляется единичное **отношение DataRelation** к <xref:System.Data.DataSet>коллекции отношений объекта. Первый аргумент в примере указывает имя создаваемого объекта **DataRelation** . Второй аргумент задает родительский **столбец** данных, а третий аргумент задает дочерний **столбец**данных.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 Объект **DataRelation** также имеет вложенное свойство, которое, если оно имеет значение **true**, приводит к тому, что строки из дочерней таблицы будут вложены в связанную строку из родительской таблицы при <xref:System.Data.DataSet.WriteXml%2A> записи в виде XML-элементов с помощью. Дополнительные сведения см. в статье [Использование XML в наборах данных](using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>См. также

- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
