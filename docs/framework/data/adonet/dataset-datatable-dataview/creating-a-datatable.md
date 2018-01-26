---
title: "Создание таблицы данных"
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 94fa5507d71fef557baadc6ee8979efeee4acf40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable"></a>Создание таблицы данных
Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.  
  
 Можно создать **DataTable** объекта, используя соответствующую **DataTable** конструктор. Его можно добавить к **DataSet** с помощью **добавить** метод, чтобы добавить его в **DataTable** объекта **таблиц** коллекции.  
  
 Можно также создать **DataTable** объекты в пределах **DataSet** с помощью **заполнения** или **FillSchema** методы  **DataAdapter** объекта, или из стандартных или выводимого схемы XML с помощью **ReadXml**, **ReadXmlSchema**, или **InferXmlSchema** методы **набора данных**. Обратите внимание, что после добавления **DataTable** членом **таблиц** набор из одного элемента **набора данных**, его нельзя добавить в коллекцию таблиц какого любые другие **Набора данных**.  
  
 При первом создании **DataTable**, не имеет схемы (то есть структуру). Чтобы определить схему таблицы, необходимо создать и добавить <xref:System.Data.DataColumn> объектов **столбцы** таблицы. Можно также определить столбец первичного ключа для таблицы и создайте и добавьте **ограничение** объектов **ограничения** таблицы. После определения схемы для **DataTable**, можно добавлять строки данных в таблицу, добавив **DataRow** объектов **строк** таблицы.  
  
 Не требуется задать значение для <xref:System.Data.DataTable.TableName%2A> свойства при создании **DataTable**; можно указать свойства в другое время, или оставить его пустым. Тем не менее, при добавлении таблицы без **TableName** значение **DataSet**, будет присвоено имя по умолчанию — таблице*N*, начиная с «Table» для Table0.  
  
> [!NOTE]
>  Мы рекомендуем избегать» таблицы*N*«соглашение об именовании, при указании **TableName** значение, поскольку указывается имя может конфликтовать с существующим именем таблицы по умолчанию в **набора данных** . Если указанное имя уже существует, вызывается исключение.  
  
 В следующем примере создается экземпляр **DataTable** объекта и присваивает ему имя «Customers».  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 В следующем примере создается экземпляр **DataTable** путем добавления его в **таблиц** коллекцию **набора данных**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
