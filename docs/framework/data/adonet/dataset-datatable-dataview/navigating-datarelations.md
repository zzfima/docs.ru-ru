---
title: Навигация по отношениям DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 73523297454be37716acedad13498954ef9a89a0
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040349"
---
# <a name="navigating-datarelations"></a>Навигация по отношениям DataRelation
Одно из основных назначений объекта <xref:System.Data.DataRelation> состоит в обеспечении переходов от одного объекта <xref:System.Data.DataTable> к другому в пределах <xref:System.Data.DataSet>. Это позволяет извлекать все связанные объекты <xref:System.Data.DataRow> в одном **объекте DataTable** при наличии одного объекта **DataRow** из связанной **таблицы**данных. Например, после установления **отношения DataRelation** между таблицей Customers и таблицей заказов можно получить все строки заказа для конкретной строки клиента с помощью **GetChildRows**.  
  
 В следующем примере кода создается **отношение DataRelation** между таблицей **Customers** и таблицей **Orders** **набора данных** и возвращаются все заказы для каждого клиента.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Следующий пример основан на предыдущем примере; в нем четыре таблицы связываются друг с другом и происходит переход по этим связям. Как и в предыдущем примере, **CustomerID** связывает таблицу **Customers** с таблицей **Orders** . Для каждого клиента в таблице **Customers** все дочерние строки в таблице **Orders** определяются, чтобы получить количество заказов конкретного клиента и их значения **OrderID** .  
  
 Развернутый пример также возвращает значения из таблиц **OrderDetails** и **Products** . Таблица **Orders** связана с таблицей **OrderDetails** с помощью **OrderID** , чтобы определить, какие товары и количества были заказаны для каждого заказа клиента. Так как таблица **OrderDetails** содержит только **ProductID** заказанного товара, **OrderDetails** связан с **продуктами** , использующими **ProductID** для возврата значения **ProductName**. В этом отношении таблица **Products** является родительской, а таблица **Order Details** является дочерней. В результате при итерации по таблице **OrderDetails** вызывается **жетпарентров** для получения связанного значения **ProductName** .  
  
 Обратите внимание, что при создании **DataRelation** для таблиц **Customers** и **Orders** значение не указывается для флага **креатеконстраинтс** (значение по умолчанию — **true**). Предполагается, что все строки в таблице **Orders** имеют значение **CustomerID** , которое существует в родительской таблице **Customers** . Если **идентификатор клиента** существует в таблице **Orders** , которая не существует в таблице **Customers** , <xref:System.Data.ForeignKeyConstraint> вызывает исключение.  
  
 Если дочерний столбец может содержать значения, которые не содержит родительский столбец, установите для флага **креатеконстраинтс** **значение false** при добавлении **DataRelation**. В этом примере флаг **креатеконстраинтс** имеет значение **false** для **DataRelation** между таблицей **Orders** и **OrderDetails** . Это позволяет приложению возвращать все записи из таблицы **OrderDetails** и только подмножество записей из таблицы **Orders** без создания исключения времени выполнения. В этом расширенном образце вывод формируется в следующем формате.  
  
```output  
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
  
 Следующий пример кода является расширенным примером, в котором возвращаются значения из таблиц **OrderDetails** и **Products** , при этом возвращается только подмножество записей в таблице **Orders** .  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
