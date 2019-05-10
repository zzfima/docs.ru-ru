---
title: Практическое руководство. Как указать, когда возникают исключения параллелизма
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 0be17e7ceb6a5e5230d2619be350266d0282078c
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910806"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Практическое руководство. Как указать, когда возникают исключения параллелизма
Если в связи с конфликтами оптимистической блокировки обновление объектов не выполняется, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывается исключение <xref:System.Data.Linq.ChangeConflictException>. Дополнительные сведения см. в разделе [оптимистичный параллелизм: Общие сведения о](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Перед отправкой изменений в базу данных можно указать момент возникновения исключений блокировки.  
  
- Создавать исключение при первом сбое (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
- Завершить все попытки обновления, собрать все ошибки и сообщить о них в исключении (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Созданное исключение <xref:System.Data.Linq.ChangeConflictException> предоставляет доступ к коллекции <xref:System.Data.Linq.ChangeConflictCollection>. Данная коллекция содержит сведения о каждом конфликте (сопоставленном с одной неудачной попыткой обновления), включая доступ к коллекции <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Каждый конфликт члена сопоставляется с одним членом в обновлении, которое привело к сбою проверки блокировки.  
  
## <a name="example"></a>Пример  
 В следующем коде приведены примеры обоих значений.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
