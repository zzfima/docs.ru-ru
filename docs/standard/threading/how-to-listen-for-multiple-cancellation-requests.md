---
title: "Практическое руководство. Прослушивание нескольких запросов на отмену"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 397de114a3d8c3cbcfbc8ab55e4dbaf45ca9b652
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Практическое руководство. Прослушивание нескольких запросов на отмену
В этом примере показано, как одновременно прослушивать два маркера отмены, любой из которых запускает отмену операции.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы Visual Studio не прерывал выполнение программы после первой ошибки, снимите флажок "Только мой код", последовательно выбрав **Сервис, Параметры, Отладка, Общие**.  
  
## <a name="example"></a>Пример  
 В следующем примере используется метод <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> для объединения двух маркеров в один. Это позволяет передавать маркер в методы, которые принимают в качестве аргумента только один маркер отмены. В этом примере показан типичный сценарий, в котором методу нужно одновременно отслеживать два маркера: полученный вне класса и созданный внутри класса.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Если связанный токен создает исключение <xref:System.OperationCanceledException>, в это исключение передается именно связанный маркер, а не один из тех, на основе которых он создан. Чтобы определить, какой из маркеров использовался для отмены, напрямую проверьте состояние объединенных маркеров.  
  
 В этом примере никогда не возникнет исключение <xref:System.AggregateException>, но мы включаем его перехват, поскольку в реальных сценариях любые исключения, кроме <xref:System.OperationCanceledException>, передаются из делегата задачи именно в оболочке <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>См. также  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
