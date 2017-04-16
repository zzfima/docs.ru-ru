---
title: "Практическое руководство. Реализация объекта Observer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "наблюдатели [платформа .NET Framework], шаблон разработки наблюдателя"
  - "шаблон разработки наблюдателя [платформа .NET Framework], реализация наблюдателей"
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Реализация объекта Observer
Шаблон разработки наблюдателя требует различения наблюдателя, который регистрируется для получения уведомлений, и поставщика, который проверяет данные и отправляет уведомления одному или нескольким наблюдателям.  В данном разделе рассматривается способ создания наблюдателя.  В связанном разделе, [Практическое руководство. Реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md), рассматривается способ создания поставщика.  
  
### Создание наблюдателя  
  
1.  Определите наблюдатель, то есть тип, реализующий интерфейс <xref:System.IObserver%601?displayProperty=fullName>.  Например, в следующем коде определяется тип с именем `TemperatureReporter`, представляющий собой созданную реализацию <xref:System.IObserver%601?displayProperty=fullName> с аргументом универсального типа `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Если наблюдатель может прекратить получение уведомлений до того, как поставщик вызовет его реализацию <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>, определите закрытую переменную, которая будет хранить реализацию <xref:System.IDisposable>, возвращенную методом <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName> поставщика.  Также необходимо определить метод подписки, вызывающий метод <xref:System.IObservable%601.Subscribe%2A> поставщика и хранящий возвращенный объект <xref:System.IDisposable>.  Например, следующий код определяет закрытую переменную с именем `unsubscriber` и определяет метод `Subscribe`, вызывающий метод <xref:System.IObservable%601.Subscribe%2A> поставщика и назначающий возвращенный объект переменной `unsubscriber`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Определите метод, позволяющий наблюдателю прекратить получение уведомлений до того, как поставщик вызовет его реализацию <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>, если эта функция необходима.  В следующем примере определяется метод `Unsubscribe`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Предоставьте реализации трех методов, определяемых интерфейсом <xref:System.IObserver%601>: <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>.  В зависимости от поставщика и потребностей приложения методы <xref:System.IObserver%601.OnError%2A> и <xref:System.IObserver%601.OnCompleted%2A> могут быть реализациями\-заглушками.  Обратите внимание, что метод <xref:System.IObserver%601.OnError%2A> не должен обрабатывать переданный объект <xref:System.Exception> как исключение, а метод <xref:System.IObserver%601.OnCompleted%2A> может вызывать реализацию <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> поставщика.  В следующем примере показана реализация <xref:System.IObserver%601> класса `TemperatureReporter`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## Пример  
 В следующем примере полностью приводится исходный код для класса `TemperatureReporter`, который предоставляет реализацию <xref:System.IObserver%601> для приложения, контролирующего температуру.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## См. также  
 <xref:System.IObserver%601>   
 [Шаблон разработки Observer](../../../docs/standard/events/observer-design-pattern.md)   
 [Практическое руководство. Реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md)   
 [Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)