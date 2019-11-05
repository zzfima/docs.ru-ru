---
title: Использование делегата AsyncCallback и объекта состояния
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: c7bd0a7606b5f93289cf39d33794457265e7e453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094609"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Использование делегата AsyncCallback и объекта состояния
Если вы используете делегат <xref:System.AsyncCallback>, чтобы обрабатывать результаты асинхронной операции в отдельном потоке, для передачи сведений между обратными вызовами и получения результата можно использовать объект состояния. В этой статье для демонстрации этого метода мы дополним пример, приведенный в статье [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются для получения из службы доменных имен (DNS) сведений об указанных пользователем компьютерах. В примере определяется и используется класс `HostRequest` для хранения сведений о состоянии. Для каждого введенного пользователем имени компьютера создается объект `HostRequest`. Этот объект передается в метод <xref:System.Net.Dns.BeginGetHostByName%2A>. Метод `ProcessDnsInformation` вызывается каждый раз при завершении запроса. Объект `HostRequest` извлекается с помощью свойства <xref:System.IAsyncResult.AsyncState%2A>. Метод `ProcessDnsInformation` использует объект `HostRequest` для сохранения значения <xref:System.Net.IPHostEntry> или исключения <xref:System.Net.Sockets.SocketException>, возвращенных запросом. Когда все запросы завершаются, приложение выполняет итерацию всех объектов `HostRequest` и выводит сведения о DNS или сообщение об ошибке <xref:System.Net.Sockets.SocketException>.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
