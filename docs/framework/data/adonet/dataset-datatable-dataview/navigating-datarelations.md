---
title: Навигация по отношениям DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: c46007fb86a76405fd99d6e943779238d6885aa8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="navigating-datarelations"></a>Навигация по отношениям DataRelation
Одно из основных назначений объекта <xref:System.Data.DataRelation> состоит в обеспечении переходов от одного объекта <xref:System.Data.DataTable> к другому в пределах <xref:System.Data.DataSet>. Это позволяет получить все связанные <xref:System.Data.DataRow> объектов в одном **DataTable** при указании единственного **DataRow** из связанного **DataTable**. Например, после установления связи **DataRelation** между таблицей заказчиков и таблицей заказов, можно получить все строки заказа для конкретного клиента строки с помощью **GetChildRows**.  
  
 В следующем примере кода создается **DataRelation** между **клиентов** таблицы и **заказов** таблицу **набора данных** и возвращает все заказы для каждого клиента.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Следующий пример основан на предыдущем примере; в нем четыре таблицы связываются друг с другом и происходит переход по этим связям. Как в предыдущем примере **CustomerID** относится **клиентов** таблицы, к **заказов** таблицы. Для каждого клиента в **клиентов** всех дочерних строк в таблице **заказов** определить таблицу для возврата числа заказов конкретного заказчика и их **OrderID** значения.  
  
 В расширенном примере также возврат значений из **OrderDetails** и **продуктов** таблиц. **Заказов** таблица связана с **OrderDetails** таблицу с помощью **OrderID** для определения, для каждого заказа, какие продукты и количества заказанных. Поскольку **OrderDetails** таблица содержит только **ProductID** из заказанного продукта, **OrderDetails** связана с **продуктов** с помощью **ProductID** для возврата **ProductName**. В этом отношении **продуктов** таблицы является родительским и **Order Details** таблицы является дочерним элементом. Таким образом, во время итерации по **OrderDetails** таблицы, **GetParentRow** вызывается для получения связанного **ProductName** значение.  
  
 Обратите внимание, что при **DataRelation** создается для **клиентов** и **заказов** таблицы, не указано значение для **createConstraints**флаг (значение по умолчанию — **true**). Это предполагает, что все строки в **заказов** таблица имеет **CustomerID** значение, которое существует в родительском объекте **клиентов** таблицы. Если **CustomerID** существует в **заказов** таблицу, которая не существует в **клиентов** таблицы, <xref:System.Data.ForeignKeyConstraint> приводит к созданию исключения.  
  
 Если дочерний столбец может содержать значения, которые не содержат родительский столбец, задайте **createConstraints** флаг **false** при добавлении **DataRelation**. В примере **createConstraints** флаг имеет значение **false** для **DataRelation** между **заказов** таблицы и  **OrderDetails** таблицы. Это позволяет приложению вернуть все записи из **OrderDetails** таблицы и только подмножество записей из **заказов** таблице без создания исключения во время выполнения. В этом расширенном образце вывод формируется в следующем формате.  
  
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
  
 В следующем примере кода представляет собой расширенный образец где значения из **OrderDetails** и **продуктов** возвращаются таблицы с набором записей в **заказов**возвращаемой таблицы.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
