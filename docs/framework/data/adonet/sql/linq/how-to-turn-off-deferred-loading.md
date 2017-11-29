---
title: "Практическое руководство. Выключение отложенной загрузки"
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
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d98b190ef4454ff29318eb6ef0f20624c85b62a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-turn-off-deferred-loading"></a>Практическое руководство. Выключение отложенной загрузки
Чтобы отключить отложенную загрузку, свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> следует задать значение `false`. Дополнительные сведения см. в разделе [отложенное или немедленное загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
> [!NOTE]
>  Отложенная загрузка отключается при отключении отслеживания объекта. Дополнительные сведения см. в разделе [как: извлечения сведений как доступных только для чтения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано отключение отложенной загрузки путем установки свойству <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> значения `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Запросы к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
