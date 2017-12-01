---
title: "Практическое руководство. Реализация поставщика"
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
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>Практическое руководство. Реализация поставщика
Шаблон разработки наблюдателя требует различения поставщика, который проверяет данные и отправляет уведомления, и одного или нескольких наблюдателей, которые получают уведомления (обратные вызовы) от поставщика. В этом разделе описывается создание поставщика. Связанный раздел, [как: реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md), рассматривается способ создания наблюдателя.  
  
### <a name="to-create-a-provider"></a>Для создания поставщика  
  
1.  Определяют данные, которые поставщик отвечает за отправку наблюдателям. Несмотря на то, что поставщик и данные, отправляемые им наблюдателям могут быть одного типа, они обычно представлены различные типы. Например, в приложении контроля температуры `Temperature` структура определяет данные, поставщик (представленный `TemperatureMonitor` класс, определенный в следующем шаге) отслеживает и на которые подписываются наблюдатели.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Определите поставщик данных, то есть тип, реализующий <xref:System.IObservable%601?displayProperty=nameWithType> интерфейса. Аргумент универсального типа поставщика является типом, которые поставщик отправляет наблюдателям. В следующем примере определяется `TemperatureMonitor` класс, представляющий собой созданную <xref:System.IObservable%601?displayProperty=nameWithType> реализации с помощью аргумента универсального типа `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Определите способ хранения поставщиком ссылок на наблюдатели, чтобы каждого наблюдателя можно получать уведомления, когда это необходимо. Чаще всего объект коллекции, например универсальный <xref:System.Collections.Generic.List%601> объект используется для этой цели. В следующем примере определяется закрытый <xref:System.Collections.Generic.List%601> объекта, экземпляр которого создается в `TemperatureMonitor` конструктора класса.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Определение <xref:System.IDisposable> реализацию, поставщик может возвращать подписчикам, чтобы они могли прекратить получение уведомлений в любое время. В следующем примере определяется вложенный `Unsubscriber` класс, который передается ссылка на коллекцию подписчиков и подписчика, когда экземпляр класса. Этот код позволяет подписчику вызвать объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> реализацию, чтобы удалить себя из коллекции подписчиков.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Выполните метод <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>. Метод передает ссылку на <xref:System.IObserver%601?displayProperty=nameWithType> интерфейс и должны быть сохранены в объекте, созданном для этой цели в шаге 3. Затем следует вернуть метод <xref:System.IDisposable> реализацию, разработанных на шаге 4. В следующем примере показана реализация <xref:System.IObservable%601.Subscribe%2A> метод `TemperatureMonitor` класса.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Уведомите наблюдатели соответствующим образом, вызвав их <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> реализации. В некоторых случаях поставщик может не вызывать <xref:System.IObserver%601.OnError%2A> метод при возникновении ошибки. Например, следующая `GetTemperature` метод моделирует монитор, считывающий температурные данные каждые пять секунд и уведомляющий наблюдатели, если температура изменилась по крайней мере.1 градусов с момента предыдущего измерения. Если устройство не сообщает температуру (то есть, если его значение равно null), поставщик уведомляет наблюдатели, что передача завершена. Обратите внимание, что, помимо вызова каждого наблюдателя <xref:System.IObserver%601.OnCompleted%2A> метода `GetTemperature` метод очищает <xref:System.Collections.Generic.List%601> коллекции. В этом случае поставщик не производит вызовы <xref:System.IObserver%601.OnError%2A> метод своих наблюдателей.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Пример  
 В следующем примере содержится полный исходный код для определения <xref:System.IObservable%601> реализацию для приложения контроля температуры. Он включает `Temperature` структуру, которая представляет собой данные, отправляемые наблюдателям, и `TemperatureMonitor` класса, который является <xref:System.IObservable%601> реализации.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IObservable%601>  
 [Шаблон разработки наблюдателя](../../../docs/standard/events/observer-design-pattern.md)  
 [Практическое руководство. Реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
