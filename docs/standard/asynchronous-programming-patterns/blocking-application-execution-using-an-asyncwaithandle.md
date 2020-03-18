---
title: Блокирование выполнения приложения с помощью AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
ms.openlocfilehash: 16b5a297c13cd9096548ed489e4994b72a48da67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121424"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Блокирование выполнения приложения с помощью AsyncWaitHandle
Приложения, которые не могут продолжать работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения этой операции. Используйте один из следующих вариантов, чтобы блокировать основной поток приложения на период ожидания асинхронной операции.  
  
- Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin**_имя_операции_ асинхронной операции. Именно этот подход демонстрируется в этой статье.  
  
- Вызовите метод **End**_имя_операции_ асинхронной операции. Пример с демонстрацией этого подхода см. в статье [Блокировка выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Приложения, использующие один или несколько объектов <xref:System.Threading.WaitHandle>, чтобы блокировать выполнение до завершения асинхронной операции, обычно вызывают метод **Begin**_имя_операции_, затем выполняют все, что можно сделать без результатов этой операции и блокируются до завершения асинхронных операций. Чтобы заблокировать приложение в ожидании одной операции, вызовите один из методов <xref:System.Threading.WaitHandle.WaitOne%2A> с использованием <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Чтобы заблокировать приложение в ожидании нескольких асинхронных операций, сохраните соответствующие объекты <xref:System.IAsyncResult.AsyncWaitHandle%2A> в массиве и вызовите один из методов <xref:System.Threading.WaitHandle.WaitAll%2A>. Чтобы заблокировать приложение в ожидании одной из нескольких асинхронных операций, сохраните соответствующие объекты <xref:System.IAsyncResult.AsyncWaitHandle%2A> в массиве и вызовите один из методов <xref:System.Threading.WaitHandle.WaitAny%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода асинхронные методы класса DNS используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере. В этом примере показана блокировка с использованием объекта <xref:System.Threading.WaitHandle>, связанного с асинхронной операцией. Обратите внимание, что в параметрах `null`, `Nothing` и <xref:System.Net.Dns.BeginGetHostByName%2A> передается значение `requestCallback` (`stateObject` в Visual Basic), так как при этом подходе они не являются обязательными.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
