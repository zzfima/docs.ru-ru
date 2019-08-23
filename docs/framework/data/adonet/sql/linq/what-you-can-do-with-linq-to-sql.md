---
title: Возможности LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: 21ed620ab5b7a78fc4f396cc474e7c62b70f1ddd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946622"
---
# <a name="what-you-can-do-with-linq-to-sql"></a>Возможности LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает все основные возможности, необходимые для разработчиков на SQL. Можно запрашивать данные, вставлять, обновлять и удалять сведения из таблиц.  
  
## <a name="selecting"></a>Выбор  
 Выборка (*проекция*) достигается написанием запроса [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] на выбранном языке программирования, последующим выполнением этого запроса и получением результатов. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически преобразует все необходимые операции в привычные операции SQL. Для получения дополнительной информации см. [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 В следующем примере извлекаются названий компаний клиентов из Лондона, которые затем отображаются в окне консоли.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a>Вставка  
 Для выполнения SQL `Insert`просто нужно добавить объекты в созданную объектную модель и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext>.  
  
 В следующем примере новый клиент и сведения о нем добавляются в таблицу `Customers` с помощью метода <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a>Updating  
 Чтобы `Update` запись в базе данных, сначала следует извлечь элемент и изменить его непосредственно в объектной модели. После изменения объекта вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext> , чтобы обновить базу данных.  
  
 В следующем примере извлекаются все клиенты из Лондона. Затем название города меняется с "Лондон" на "Лондон - Метро". Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для отправления изменений в базу данных.  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a>Удаление  
 Чтобы `Delete` элемент, удалите его из коллекции, в которую он входит, а затем вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext> , чтобы применить изменение.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не распознает операции каскадного удаления. Если вы хотите удалить строку в таблице с ограничениями, см. раздел [как Удаляет строки из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 В следующем примере из базы данных извлекается клиент, `CustomerID` которого равен `98128` . Затем, после подтверждения извлечения строки клиента, вызывается метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> , необходимый для удаления объекта из коллекции. Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для передачи удаления в базу данных.  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
