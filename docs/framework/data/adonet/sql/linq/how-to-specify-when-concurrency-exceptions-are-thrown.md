---
title: "Практическое руководство. Выбор ситуаций, в которых создаются исключения параллельности"
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
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8af833574544410977b9f881f9b2db4e6d88aa73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Практическое руководство. Выбор ситуаций, в которых создаются исключения параллельности
Если в связи с конфликтами оптимистической блокировки обновление объектов не выполняется, в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызывается исключение <xref:System.Data.Linq.ChangeConflictException>. Дополнительные сведения см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Перед отправкой изменений в базу данных можно указать момент возникновения исключений блокировки.  
  
-   Создавать исключение при первом сбое (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
-   Завершить все попытки обновления, собрать все ошибки и сообщить о них в исключении (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Созданное исключение <xref:System.Data.Linq.ChangeConflictException> предоставляет доступ к коллекции <xref:System.Data.Linq.ChangeConflictCollection>. Данная коллекция содержит сведения о каждом конфликте (сопоставленном с одной неудачной попыткой обновления), включая доступ к коллекции <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>. Каждый конфликт члена сопоставляется с одним членом в обновлении, которое привело к сбою проверки блокировки.  
  
## <a name="example"></a>Пример  
 В следующем коде приведены примеры обоих значений.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Как: управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
