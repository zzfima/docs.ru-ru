---
title: Добавление отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: d0f481979ead7af775d462a2624ec43080e2c5a9
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706243"
---
# <a name="adding-datarelations"></a>Добавление отношений DataRelation
В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.  
  
 Аргументы, необходимые для создания **DataRelation** : имя **DataRelation** создается и массив из одного или нескольких <xref:System.Data.DataColumn> ссылки на столбцы, которые служат в качестве родительской и дочерней столбцы в связи. После создания **DataRelation**, его можно использовать для перехода между таблицами и для получения значений.  
  
 Добавление **DataRelation** для <xref:System.Data.DataSet> добавляет по умолчанию <xref:System.Data.UniqueConstraint> с родительской таблицей и <xref:System.Data.ForeignKeyConstraint> к дочерней таблице. Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [ограничения таблиц данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 В следующем примере кода создается **DataRelation** с использованием двух <xref:System.Data.DataTable> объекты в <xref:System.Data.DataSet>. Каждый <xref:System.Data.DataTable> содержит столбец с именем **CustID**, который используется в качестве связи между двумя <xref:System.Data.DataTable> объектов. В примере добавляется один **DataRelation** для **отношений** коллекцию <xref:System.Data.DataSet>. В примере первый аргумент указывает имя **DataRelation** создания. Второй аргумент задает родительский **DataColumn** и третий аргумент задает дочерний элемент **DataColumn**.  
  
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
  
 Объект **DataRelation** также имеет **Nested** свойство, если значение **true**, делает строки из дочерней таблицы вложенными в связанную строку родительской таблицы При записи в виде XML-элементов с помощью <xref:System.Data.DataSet.WriteXml%2A> . Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>См. также  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
