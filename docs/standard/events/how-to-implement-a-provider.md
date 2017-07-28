---
title: "Практическое руководство. Реализация поставщика | Microsoft Docs"
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
  - "шаблон разработки наблюдателя [платформа .NET Framework], реализация поставщиков"
  - "поставщики [платформа .NET Framework], в шаблоне разработки наблюдателя"
  - "наблюдаемые объекты [платформа .NET Framework], в шаблоне разработки наблюдателя"
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Реализация поставщика
Шаблон разработки наблюдателя требует различения поставщика, который проверяет данные и отправляет уведомления, и одного или нескольких наблюдателей, которые получают уведомления \(обратные вызовы\) от поставщика.  В данном разделе рассматривается способ создания поставщика.  В связанном разделе, [Практическое руководство. Реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md), рассматривается способ создания наблюдателя.  
  
### Создание поставщика  
  
1.  Определите данные, за отправку которых наблюдателям отвечает поставщик.  Хотя поставщик и данные, отправляемые им наблюдателям, могут относиться к одному типу, обычно они представлены различными типами.  Например, в приложении контроля температуры структура `Temperature` определяет данные, которые поставщик \(представленный классом `TemperatureMonitor`, определенным в следующем пункте\) проверяет и на которые подписываются наблюдатели.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Определите поставщик данных, то есть тип, реализующий интерфейс <xref:System.IObservable%601?displayProperty=fullName>.  Аргумент универсального типа поставщика является типом, отправляемым поставщиком наблюдателям.  В следующем примере определяется класс `TemperatureMonitor`, представляющий собой созданную реализацию <xref:System.IObservable%601?displayProperty=fullName> с аргументом универсального типа `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Определите способ хранения поставщиком ссылок на наблюдатели, чтобы каждый наблюдатель мог быть оповещен, когда это необходимо.  Чаще всего для этого используется объект коллекции, такой как универсальный объект <xref:System.Collections.Generic.List%601>.  В следующем примере определяется закрытый объект <xref:System.Collections.Generic.List%601>, экземпляр которого создается в конструкторе класса `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Определите реализацию <xref:System.IDisposable>, которую поставщик может возвращать подписчикам, чтобы они могли прекратить получение уведомлений в любой момент.  В следующем примере определяется вложенный класс `Unsubscriber`, который передается в качестве ссылки на коллекцию подписчиков и на подписчика, когда создается экземпляр класса.  Этот код позволяет подписчику вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> для удаления себя из коллекции подписчиков.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Реализуйте метод <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName>.  Этот метод передается в качестве ссылки на интерфейс <xref:System.IObserver%601?displayProperty=fullName> и должен храниться в объекте, созданном для этой цели на этапе 3.  Затем этот метод должен вернуть реализацию <xref:System.IDisposable>, разработанную на этапе 4.  В следующем примере показана реализация метода <xref:System.IObservable%601.Subscribe%2A> в классе `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Уведомите наблюдатели соответствующим образом, вызвав их реализации <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>.  В некоторых случаях поставщик может не вызывать метод <xref:System.IObserver%601.OnError%2A> при возникновении ошибки.  Например, следующий метод `GetTemperature` моделирует монитор, считывающий температурные данные каждые пять секунд и уведомляющий наблюдатели, если температура изменилась хотя бы на 0,1 градуса с момента предыдущего измерения.  Если это устройство не сообщает температуру \(то есть, если его значением является NULL\), поставщик уведомляет наблюдатели, что передача завершена.  Обратите внимание, что в дополнение к вызову метода <xref:System.IObserver%601.OnCompleted%2A> каждого наблюдателя метод `GetTemperature` очищает коллекцию <xref:System.Collections.Generic.List%601>.  В данном случае поставщик не производит вызовы метода <xref:System.IObserver%601.OnError%2A> его наблюдателей.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## Пример  
 В следующем примере полностью приводится исходный код для определения реализации <xref:System.IObservable%601> для приложения, контролирующего температуру.  Сюда включается структура `Temperature`, то есть данные, отправляемые наблюдателям, и класс `TemperatureMonitor`, представляющий собой реализацию <xref:System.IObservable%601>.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## См. также  
 <xref:System.IObservable%601>   
 [Шаблон разработки Observer](../../../docs/standard/events/observer-design-pattern.md)   
 [Практическое руководство. Реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md)   
 [Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)