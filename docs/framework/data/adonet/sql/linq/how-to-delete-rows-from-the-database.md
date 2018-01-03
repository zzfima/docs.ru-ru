---
title: "Практическое руководство. Удаление строк из базы данных"
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
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ac81e4e18c578f11a5c6f36203e15b5363c54e71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-delete-rows-from-the-database"></a>Практическое руководство. Удаление строк из базы данных
Можно удалить строки в базе данных путем удаления соответствующего [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты из их коллекции, связанной с таблицей. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Преобразует изменения в соответствующие SQL `DELETE` команд.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любую из следующих задач.  
  
-   Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.  
  
-   Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.  
  
 В противном случае создается исключение. См. второй пример кода далее в этом разделе.  
  
> [!NOTE]
>  Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных. Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.  
  
 В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в разделе [как: подключение к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-delete-a-row-in-the-database"></a>Удаление строки в базе данных  
  
1.  Отправьте в базу данных запрос на удаляемую строку.  
  
2.  Вызовите метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.  
  
3.  Отправьте изменение в базу данных.  
  
## <a name="example"></a>Пример  
 В первом примере кода в базу данных отправляется запрос на сведения о заказе "Order #11000", помечаются сведения для удаления, а изменения отправляются в базу данных.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a>Пример  
 Целью второго примера является удаление заказа (с номером 10250). Код сначала проверяет таблицу `OrderDetails` на наличие в ней дочерних элементов удаляемого заказа. Если в таблице есть дочерние элементы заказа, сначала они, а затем сам заказ помечаются для удаления. <xref:System.Data.Linq.DataContext> располагает фактические действия по удалению в надлежащей последовательности, чтобы команды удаления, отправляемые в базу данных, подчинялись ее ограничениям.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
