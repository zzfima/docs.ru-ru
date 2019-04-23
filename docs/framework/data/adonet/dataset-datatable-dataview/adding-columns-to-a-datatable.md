---
title: Добавление столбцов в таблицу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 2e7008f6693d7d76520a7ff6ae9172e28e4990c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207010"
---
# <a name="adding-columns-to-a-datatable"></a>Добавление столбцов в таблицу данных
Объект <xref:System.Data.DataTable> содержит коллекцию <xref:System.Data.DataColumn> объекты, упоминаемые **столбцы** свойство таблицы. Эта коллекция столбцов наряду с ограничениями определяет схему, или структуру, таблицы.  
  
 Создании **DataColumn** объектов в пределах таблицы с помощью **DataColumn** конструктор, или путем вызова **добавить** метод **столбцы**свойство таблицы, который является <xref:System.Data.DataColumnCollection>. **Добавить** метод принимает необязательные **ColumnName**, **DataType**, и **выражение** аргументов и создает новый  **DataColumn** членом коллекции. Он также принимает существующий **DataColumn** объект и добавляет его в коллекцию и возвращает ссылку на добавленный **DataColumn** при запросе. Так как **DataTable** объекты не относятся к любому источнику данных, типы .NET Framework используются при указании типа данных **DataColumn**.  
  
 В следующем примере добавляются четыре столбца, **DataTable**.  
  
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
  
 Обратите внимание, что в примере свойства **CustID** столбца присваивается допускает **DBNull** значения и для ограничения значений должны быть уникальными. Тем не менее если вы определяете **CustID** столбец как столбец первичного ключа таблицы, **AllowDBNull** будет автоматически установлено **false** и **Unique** будет автоматически установлено **true**. Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Если для столбца не указано имя столбца, столбца присваивается предусмотренное по умолчанию имя столбца*N,* начиная с «Column1», когда он добавляется в **DataColumnCollection**. Мы рекомендуем избегать именования «столбец*N*"когда вводится имя столбца, так как имя может конфликтовать с существующим именем столбца по умолчанию в **DataColumnCollection**. Если указанное имя уже существует, вызывается исключение.  
  
 Если элемент <xref:System.Xml.Linq.XElement> используется в качестве <xref:System.Data.DataColumn.DataType%2A> объекта <xref:System.Data.DataColumn> в <xref:System.Data.DataTable>, то XML-сериализация не будет работать при считывании данных. Например, если документ <xref:System.Xml.XmlDocument> записывается методом `DataTable.WriteXml`, то во время сериализации в XML-код создается дополнительный родительский узел в элементе <xref:System.Xml.Linq.XElement>. Чтобы избежать этой проблемы, используйте тип <xref:System.Data.SqlTypes.SqlXml> вместо <xref:System.Xml.Linq.XElement>. Методы `ReadXml` и `WriteXml` правильно работают с <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
