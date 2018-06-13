---
title: Добавление отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 451ee0eee466efca86345ea7112e9b178a2c66e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756947"
---
# <a name="adding-datarelations"></a>Добавление отношений DataRelation
В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.  
  
 Аргументы, необходимые для создания **DataRelation** : имя **DataRelation** создается и массив из одного или нескольких <xref:System.Data.DataColumn> ссылки на столбцы, которые выступают в роли родительских и дочерних столбцы в связи. После создания **DataRelation**, его можно использовать для перехода между таблицами и для извлечения значений.  
  
 Добавление **DataRelation** для <xref:System.Data.DataSet> по умолчанию, добавляет <xref:System.Data.UniqueConstraint> с родительской таблицей и <xref:System.Data.ForeignKeyConstraint> к дочерней таблице. Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [ограничения таблиц данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 В следующем примере кода создается **DataRelation** с использованием двух <xref:System.Data.DataTable> объекты в <xref:System.Data.DataSet>. Каждый <xref:System.Data.DataTable> содержит столбец с именем **CustID**, который используется в качестве связи между двумя <xref:System.Data.DataTable> объектов. В этом примере добавляется один **DataRelation** для **отношений** коллекцию <xref:System.Data.DataSet>. В примере первый аргумент указывает имя **DataRelation** создается. Второй аргумент задает родительский **DataColumn** и третий аргумент задает дочерний **DataColumn**.  
  
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
  
 Объект **DataRelation** также имеет **Nested** свойства, если задано значение **true**, делает строки из дочерней таблицы вложенными в связанную строку родительской таблицы Если они написаны как элементы XML при помощи <xref:System.Data.DataSet.WriteXml%2A> . Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>См. также  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
