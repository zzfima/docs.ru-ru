---
title: "Практическое руководство. Реализация объекта Observer"
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
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a>Практическое руководство. Реализация объекта Observer
Шаблон разработки наблюдателя требует различения наблюдателя, который регистрируется для получения уведомлений, и поставщика, который проверяет данные и отправляет уведомления для одного или нескольких наблюдателей. В этом разделе описывается создание наблюдателя. Связанный раздел, [как: реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md), рассматривается способ создания поставщика.  
  
### <a name="to-create-an-observer"></a>Создание наблюдателя  
  
1.  Определите наблюдатель, то есть тип, реализующий <xref:System.IObserver%601?displayProperty=nameWithType> интерфейса. Например, следующий код определяет тип с именем `TemperatureReporter` , представляющий собой созданную <xref:System.IObserver%601?displayProperty=nameWithType> реализации с помощью аргумента универсального типа `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Если наблюдатель может прекратить получение уведомлений до вызова поставщиком его <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> реализацию, определить частную переменную, которая будет содержать <xref:System.IDisposable> реализацию, возвращенный поставщиком <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> метод. Также следует определить метод подписки, который вызывает поставщика <xref:System.IObservable%601.Subscribe%2A> метод и хранящий возвращенный <xref:System.IDisposable> объекта. Например, следующий код определяет закрытую переменную с именем `unsubscriber` и определяет `Subscribe` метод, который вызывает поставщика <xref:System.IObservable%601.Subscribe%2A> метод и назначает возвращаемый объект `unsubscriber` переменной.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Определите метод, позволяющий наблюдателю прекратить получение уведомлений до вызова поставщиком его <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> реализации, когда этот компонент является обязательным. В следующем примере определяется `Unsubscribe` метод.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Определить реализации трех методов, определяемых <xref:System.IObserver%601> интерфейса: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. В зависимости от поставщика и потребностям приложения <xref:System.IObserver%601.OnError%2A> и <xref:System.IObserver%601.OnCompleted%2A> методы могут быть заглушки реализации. Обратите внимание, что <xref:System.IObserver%601.OnError%2A> метод не должен обрабатывать переданный <xref:System.Exception> объект как исключение и <xref:System.IObserver%601.OnCompleted%2A> метод может вызывать поставщик <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> реализации. В следующем примере показан <xref:System.IObserver%601> реализация `TemperatureReporter` класса.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Пример  
 В следующем примере содержится полный исходный код для `TemperatureReporter` класс, предоставляющий <xref:System.IObserver%601> реализацию для приложения контроля температуры.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IObserver%601>  
 [Шаблон разработки наблюдателя](../../../docs/standard/events/observer-design-pattern.md)  
 [Практическое руководство. Реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
