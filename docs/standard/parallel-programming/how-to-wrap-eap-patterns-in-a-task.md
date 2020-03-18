---
title: Практическое руководство. Создание задачи-оболочки для шаблонов EAP
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: ac7436892c644340286bb4670bf75c9cd63a8ce5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106822"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Практическое руководство. Создание задачи-оболочки для шаблонов EAP
В следующем примере показан способ предоставления произвольной последовательности асинхронных операций на основе событий (EAP) как одной задачи с помощью <xref:System.Threading.Tasks.TaskCompletionSource%601>. В примере также показано использование <xref:System.Threading.CancellationToken> для вызова встроенных методов отмены в объектах <xref:System.Net.WebClient>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>См. также раздел

- [Библиотека параллельных задач и традиционное асинхронное программирование .NET Framework](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
