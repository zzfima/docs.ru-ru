---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 2de0182cc0b87768a9cff553b7ec6e77f8ccc7b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793771"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Практическое руководство. Как обнаруживать и разрешать конфликты отправки
Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями. Дополнительные сведения см. в разделе [Практическое руководство. Управление конфликтами](how-to-manage-change-conflicts.md)изменений.  
  
## <a name="example"></a>Пример  
 `try` В следующем примере показан / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключение. Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».  
  
> [!NOTE]
> Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic). Дополнительные сведения см. в разделе <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
- [Практическое руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md)
