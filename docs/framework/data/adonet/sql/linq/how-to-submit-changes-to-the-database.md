---
title: Практическое руководство. Как отправить изменения в базу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
ms.openlocfilehash: 222ce575d9e977cc8b68862385b4a1b147c6394a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326389"
---
# <a name="how-to-submit-changes-to-the-database"></a>Практическое руководство. Как отправить изменения в базу данных
Независимо от количества изменений, произведенных над объектами, эти изменения выполняются только над репликам, содержащимся в памяти. Фактические данные в базе данных при этом не изменяются. Изменения не передаются на сервер до тех пор, пока не будет явно вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> класса <xref:System.Data.Linq.DataContext>.  
  
 При вызове этого метода класс <xref:System.Data.Linq.DataContext> пытается преобразовать сделанные изменения в эквивалентные команды SQL. Можно использовать собственную пользовательскую логику для переопределения этих действий, однако порядок отправки управляется службой для <xref:System.Data.Linq.DataContext> называется *обработчиком изменений*. Ниже представлена последовательность событий.  
  
1. При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает набор известных объектов, чтобы определить, присоединены ли к ним новые экземпляры. При положительном результате новые экземпляры добавляются в набор отслеживаемых объектов.  
  
2. Все объекты, содержащие ожидающие изменения, упорядочиваются в последовательности объектов на основе зависимостей между ними. Объекты, изменения которых зависят от других объектов, располагаются после своих зависимостей.  
  
3. Непосредственно после передачи фактических изменений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] начинает транзакцию для инкапсуляции ряда отдельных команд.  
  
4. Изменения объектов последовательно преобразуются в команды SQL и отправляются на сервер.  
  
 В данный момент любые ошибки, обнаруженные базой данных, приводят к остановке процесса отправки и вызову исключения. Выполняется откат всех изменений базы данных к состоянию до начала отправки. Класс <xref:System.Data.Linq.DataContext> по-прежнему содержит запись всех изменений. Поэтому можно попытаться исправить проблему и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> еще раз, как показано в следующем примере кода.  
  
## <a name="example"></a>Пример  
 После успешного завершения транзакции, содержащей отправку, класс <xref:System.Data.Linq.DataContext> принимает изменения объектов, пропуская сведения об отслеживании изменений.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Обнаруживать и разрешать конфликты отправки](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)
- [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
