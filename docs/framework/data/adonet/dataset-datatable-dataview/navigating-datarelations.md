---
title: Навигация по отношениям DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: f4dfccad23bf5d15f5cbd0a33e76a136417e13ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607268"
---
# <a name="navigating-datarelations"></a>Навигация по отношениям DataRelation
Одно из основных назначений объекта <xref:System.Data.DataRelation> состоит в обеспечении переходов от одного объекта <xref:System.Data.DataTable> к другому в пределах <xref:System.Data.DataSet>. Это позволяет получить все связанные <xref:System.Data.DataRow> объектов в одном **DataTable** при указании единственного **DataRow** из связанной **DataTable**. Например, после установки **DataRelation** между таблицей заказчиков и таблицей заказов, можно получить все строки заказов для конкретного клиента строки с помощью **GetChildRows**.  
  
 В следующем примере кода создается **DataRelation** между **клиентов** таблицы и **заказы** таблицы **набора данных** и возвращает все заказы для каждого клиента.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Следующий пример основан на предыдущем примере; в нем четыре таблицы связываются друг с другом и происходит переход по этим связям. Как показано в предыдущем примере **CustomerID** относится **клиентов** таблицы **заказы** таблицы. Для каждого клиента в **клиентов** таблицы, все дочерние строки в **заказы** определяются таблицы, для возврата числа заказов конкретного заказчика и их **OrderID** значения.  
  
 Расширенный пример возвращает значения из **OrderDetails** и **продуктов** таблиц. **Заказы** таблица связана с **OrderDetails** таблицу с помощью **OrderID** чтобы определить, для каждого клиентского заказа, какие товары и количества были заказаны. Так как **OrderDetails** таблицы содержит только **ProductID** каждого заказанного продукта, **OrderDetails** связана с **продуктов** с помощью **ProductID** для возвращения **ProductName**. В этой связи **продуктов** таблицы является родительским и **Order Details** таблицы является дочерним элементом. В результате во время итерации внутри **OrderDetails** таблицы, **GetParentRow** вызывается для получения связанного **ProductName** значение.  
  
 Обратите внимание, что при **DataRelation** создается для **клиентов** и **заказы** таблицы, значение не указано для **createConstraints**флаг (по умолчанию используется **true**). Это предполагает, что все строки в **заказы** таблица имеет **CustomerID** значение, которое существует в родительском объекте **клиентов** таблицы. Если **CustomerID** существует в **заказы** таблицу, которая не существует в **клиентов** таблицы, <xref:System.Data.ForeignKeyConstraint> приводит к возникновению исключения, исключение.  
  
 Когда дочерний столбец может содержать значения, которые не содержит родительский столбец, задайте **createConstraints** флаг **false** при добавлении **DataRelation**. В примере **createConstraints** флаг имеет значение **false** для **DataRelation** между **заказы** таблицы и  **OrderDetails** таблицы. Это позволяет приложению вернуть все записи из **OrderDetails** таблицы и только подмножество записей из **заказы** таблицы без формирования исключения во время выполнения. В этом расширенном образце вывод формируется в следующем формате.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 В следующем примере кода представляет собой расширенный образец где значения из **OrderDetails** и **продуктов** возвращаются таблицы с набором записей в **заказы**таблицы.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
