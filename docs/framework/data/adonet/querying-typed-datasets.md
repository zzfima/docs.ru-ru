---
title: "Запросы к типизированным наборам данных"
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd78b4f47d7f48d7b4cbacdf53140758a05b7869
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="querying-typed-datasets"></a>Запросы к типизированным наборам данных
Если схема объекта <xref:System.Data.DataSet> известна во время разработки приложения, при создании запроса <xref:System.Data.DataSet> рекомендуется использовать типизированный объект [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Типизированный <xref:System.Data.DataSet> — это класс, производный от <xref:System.Data.DataSet>. Поэтому он наследует все методы, события и свойства класса <xref:System.Data.DataSet>. Кроме того, типизированный <xref:System.Data.DataSet> предоставляет строго типизированные методы, события и свойства. Это означает, что доступ к таблицам и столбцам можно получить по имени, не используя методы на основе коллекций. Это упрощает запросы и повышает их читаемость. Дополнительные сведения см. в разделе [типизированных наборов данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]также поддерживает запросы к типизированным объектам <xref:System.Data.DataSet>. С типизированным <xref:System.Data.DataSet>, нет необходимости использовать универсальный <xref:System.Data.DataRowExtensions.Field%2A> метода или <xref:System.Data.DataRowExtensions.SetField%2A> метод для доступа к данным столбца.  Имена свойств доступны во время компиляции, так как сведения о типе включаются в <xref:System.Data.DataSet>. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]предоставляет доступ к значениям столбцов правильного типа, поэтому ошибки несоответствия типов выявляются при компиляции, а не во время выполнения.  
  
 Прежде чем направлять запросы к типизированному объекту <xref:System.Data.DataSet>, необходимо создать класс с помощью конструктора DataSet в среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  Дополнительные сведения см. в разделе, посвященном [созданию и настройке наборов данных](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  
  
## <a name="example"></a>Пример  
 В следующем примере показан запрос к типизированному объекту <xref:System.Data.DataSet>:  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## <a name="see-also"></a>См. также  
 [Запросы к наборам данных](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Запросы между таблицами](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [Запросы к одной таблице](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
