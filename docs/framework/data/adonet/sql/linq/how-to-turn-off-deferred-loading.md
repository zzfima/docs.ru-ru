---
title: Практическое руководство. Как отключить отложенную загрузку
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 6559392527bb02afe9cea61e704f1f371c6d5470
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781651"
---
# <a name="how-to-turn-off-deferred-loading"></a>Практическое руководство. Как отключить отложенную загрузку
Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`. Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).  
  
> [!NOTE]
> Отложенная загрузка отключается при отключении отслеживания объекта. Дополнительные сведения см. в разделе [Практическое руководство. Получение сведений только](how-to-retrieve-information-as-read-only.md)для чтения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
- [Запрос к базе данных](querying-the-database.md)
