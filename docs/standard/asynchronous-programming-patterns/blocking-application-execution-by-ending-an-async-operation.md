---
title: Блокировка выполнения приложения путем завершения асинхронной операции
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
author: rpetrusha
ms.author: ronpet
dev_langs:
- csharp
- vb
ms.openlocfilehash: db46025ca1169f2f93a5b8eabb62a06ccc4bb95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567423"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Блокировка выполнения приложения путем завершения асинхронной операции
Приложения, которые не могут продолжать работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения этой операции. Используйте один из следующих вариантов, чтобы блокировать основной поток приложения на период ожидания асинхронной операции.  
  
-   Вызовите метод **End***имя_операции* асинхронной операции. Именно этот подход демонстрируется в этой статье.  
  
-   Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin***имя_операции* асинхронной операции. Пример с демонстрацией этого подхода см. в статье [Блокирование выполнения приложения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Приложения, использующие метод **End***имя_операции*, чтобы блокировать выполнение до завершения асинхронной операции, обычно вызывают метод **Begin***имя_операции*, затем выполняют все, что можно сделать без результатов этой операции и вызывают метод **End***имя_операции*.  
  
## <a name="example"></a>Пример  
 В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере. Обратите внимание, что в параметрах <xref:System.Net.Dns.BeginGetHostByName%2A>, `requestCallback` и `stateObject` передается значение `null` (`Nothing` в Visual Basic), так как при таком подходе эти аргументы не являются обязательными.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
