---
title: "Запрос состояния асинхронной операции"
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Запрос состояния асинхронной операции
Приложения, которые могут выполнять другую работу во время ожидания результатов асинхронной операции не должны блокировать ожидание до завершения операции. Для продолжения выполнения инструкций при ожидании завершения асинхронной операции, используйте один из следующих параметров:  
  
-   Используйте <xref:System.IAsyncResult.IsCompleted%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод, чтобы определить, завершена ли операция. Такой подход известен как запрос и демонстрируются в данном разделе.  
  
-   Используйте <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке. Пример, демонстрирующий этот способ см. в разделе [использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен для компьютера, заданного пользователем. В этом примере запускает асинхронную операцию, а затем выводятся точки («.») с помощью консоли до завершения операции. Обратите внимание, что **null** (**ничего** в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> и <xref:System.Object> параметры так, как эти параметры не являются обязательными при использовании такого подхода.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
