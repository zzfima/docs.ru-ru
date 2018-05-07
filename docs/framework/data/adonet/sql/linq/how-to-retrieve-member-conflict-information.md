---
title: Практическое руководство. Получение сведений о конфликте членов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 5d0788daac6c1be8dd7670c330d1efc36b074c2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-member-conflict-information"></a>Практическое руководство. Получение сведений о конфликте членов
Класс <xref:System.Data.Linq.MemberChangeConflict> можно использовать для получения сведений об отдельных членах конфликта. В этом же контексте можно предусмотреть пользовательскую обработку конфликта для любого члена. Дополнительные сведения см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Пример  
 Следующий код выполняет итерацию объектов <xref:System.Data.Linq.ObjectChangeConflict>. Итерация выполняется для каждого объекта <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
>  Для предоставления сведений <xref:System.Reflection> добавьте пространство имен <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
