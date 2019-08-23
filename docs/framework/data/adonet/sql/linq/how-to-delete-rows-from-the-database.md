---
title: Практическое руководство. Как удалить строки из базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: bae67646d39ad716ed0974987ccbc76e5dd0e58a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940242"
---
# <a name="how-to-delete-rows-from-the-database"></a>Практическое руководство. Как удалить строки из базы данных
Можно удалить строки в базе данных, удалив соответствующие [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты из их коллекции, связанной с таблицами. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]преобразует изменения в соответствующие команды SQL `DELETE` .  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любую из следующих задач.  
  
- Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.  
  
- Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.  
  
 В противном случае создается исключение. См. второй пример кода далее в этом разделе.  
  
> [!NOTE]
> Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных. Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Разработчики, использующие Visual Studio, могут использовать реляционный конструктор объектов для разработки хранимых процедур для той же цели.  
  
 В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в разделе [Практическое руководство. Подключитесь к базе](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)данных.  
  
### <a name="to-delete-a-row-in-the-database"></a>Удаление строки в базе данных  
  
1. Отправьте в базу данных запрос на удаляемую строку.  
  
2. Вызовите метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.  
  
3. Отправьте изменение в базу данных.  
  
## <a name="example"></a>Пример  
 В первом примере кода в базу данных отправляется запрос на сведения о заказе "Order #11000", помечаются сведения для удаления, а изменения отправляются в базу данных.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a>Пример  
 Целью второго примера является удаление заказа (с номером 10250). Код сначала проверяет таблицу `OrderDetails` на наличие в ней дочерних элементов удаляемого заказа. Если в таблице есть дочерние элементы заказа, сначала они, а затем сам заказ помечаются для удаления. <xref:System.Data.Linq.DataContext> располагает фактические действия по удалению в надлежащей последовательности, чтобы команды удаления, отправляемые в базу данных, подчинялись ее ограничениям.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
