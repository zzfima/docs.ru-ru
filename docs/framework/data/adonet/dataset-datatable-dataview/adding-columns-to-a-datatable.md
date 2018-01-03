---
title: "Добавление столбцов в таблицу данных"
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
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 423b9ed389a5a3750c8e9b0339e0887d6b650741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adding-columns-to-a-datatable"></a>Добавление столбцов в таблицу данных
Объект <xref:System.Data.DataTable> содержит коллекцию <xref:System.Data.DataColumn> объекты, упоминаемые **столбцы** свойство таблицы. Эта коллекция столбцов наряду с ограничениями определяет схему, или структуру, таблицы.  
  
 Вы создаете **DataColumn** объектов в пределах таблицы с помощью **DataColumn** конструктор, или путем вызова **добавить** метод **столбцы**свойство таблицы, которое является <xref:System.Data.DataColumnCollection>. **Добавить** принимает необязательные **ColumnName**, **DataType**, и **выражение** аргументы и создает новый  **DataColumn** как член коллекции. Он также принимает существующий **DataColumn** и добавляет его в коллекцию и возвращает ссылку на добавленный **DataColumn** по запросу. Поскольку **DataTable** объекты не относятся к любому источнику данных, типы .NET Framework используются при задании типа данных **DataColumn**.  
  
 В следующем примере добавляется четыре столбца, чтобы **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 В примере обратите внимание, что свойства **CustID** задаются запрещено **DBNull** значения и значениям ограничений быть уникальными. Тем не менее если определить **CustID** столбец как столбец первичного ключа таблицы, **AllowDBNull** свойство будет автоматически присвоено **false** и **Unique** свойство будет автоматически присвоено **true**. Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Если для столбца не указано имя столбца, столбца присваивается имя по умолчанию столбца*N,* начиная с «Column1», когда он добавляется в **DataColumnCollection**. Мы рекомендуем избегать именования «столбец*N*» при задании имени столбца, так как предоставляемое имя может конфликтовать с существующим именем столбца по умолчанию в **DataColumnCollection**. Если указанное имя уже существует, вызывается исключение.  
  
 Если элемент <xref:System.Xml.Linq.XElement> используется в качестве <xref:System.Data.DataColumn.DataType%2A> объекта <xref:System.Data.DataColumn> в <xref:System.Data.DataTable>, то XML-сериализация не будет работать при считывании данных. Например, если документ <xref:System.Xml.XmlDocument> записывается методом `DataTable.WriteXml`, то во время сериализации в XML-код создается дополнительный родительский узел в элементе <xref:System.Xml.Linq.XElement>. Чтобы избежать этой проблемы, используйте тип <xref:System.Data.SqlTypes.SqlXml> вместо <xref:System.Xml.Linq.XElement>. Методы `ReadXml` и `WriteXml` правильно работают с <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
