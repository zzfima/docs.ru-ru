---
title: Практическое руководство. Реализация поставщика
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
ms.openlocfilehash: f5bb3cda0caa39ba3fd094b80e0b769a4bfc1f85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141551"
---
# <a name="how-to-implement-a-provider"></a>Практическое руководство. Реализация поставщика
Шаблон разработки наблюдателя подразумевает разделение ролей поставщика, который отслеживает данные и отправляет уведомления, и одного или нескольких наблюдателей, которые получают от поставщика уведомления (обратные вызовы). В этой статье описан процесс создания поставщика. Создание наблюдателя рассматривается в схожей статье [Практическое руководство. Реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md).  
  
### <a name="to-create-a-provider"></a>Создание поставщика  
  
1. Определите данные, за отправку которых наблюдателям будет отвечать этот поставщик. Сам поставщик и отправляемые им данные могут иметь одинаковый тип, но обычно они представлены разными типами. Например, в приложении контроля температуры структура `Temperature` определяет данные, которые отслеживаются поставщиком (он представлен классом `TemperatureMonitor`, который мы определим на следующем этапе) и на которые подписываются наблюдатели.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2. Определите поставщик данных в виде типа, реализующего интерфейс <xref:System.IObservable%601?displayProperty=nameWithType>. Аргумент универсального типа для поставщика определяет тип данных, отправляемых наблюдателям. В следующем примере определяется класс `TemperatureMonitor`, который представляет собой реализацию <xref:System.IObservable%601?displayProperty=nameWithType> с аргументом универсального типа `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3. Выберите способ, который поставщик будет использовать для хранения ссылок на наблюдатели, которые он должен извещать при соответствующих условиях. Чаще всего для этого используется объект коллекции, например универсальный объект <xref:System.Collections.Generic.List%601>. В следующем примере определяется закрытый объект <xref:System.Collections.Generic.List%601>, экземпляр которого создается в конструкторе класса `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4. Определите реализацию <xref:System.IDisposable>, которую поставщик передает подписчикам, чтобы они могли в любой момент отключить отправку уведомлений. В следующем примере определяется вложенный класс `Unsubscriber`, в который передается ссылка на коллекцию подписчиков и на отдельного подписчика при создании экземпляра класса. Этот код позволяет подписчику вызвать для объекта реализацию <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>, чтобы удалить себя из коллекции подписчиков.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5. Выполните метод <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>. В этот метод передается ссылка на интерфейс <xref:System.IObserver%601?displayProperty=nameWithType>, которую нужно сохранить в объекте, созданном для этой цели на шаге 3. Затем метод должен возвращать реализацию <xref:System.IDisposable>, разработанную на шаге 4. Ниже представлен пример реализации метода <xref:System.IObservable%601.Subscribe%2A> в классе `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6. Организуйте уведомление наблюдателей, вызывая их реализации методов <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. В некоторых случаях поставщик может не вызывать метод <xref:System.IObserver%601.OnError%2A> при возникновении ошибки. Например, при помощи указанного ниже метода `GetTemperature` моделируется монитор, который считывает температурные данные каждые пять секунд и уведомляет наблюдателей, если температура изменилась по крайней мере на 0,1 градуса с момента предыдущего измерения. Если устройство не передает данные о температуре (то есть получено значение null), поставщик уведомляет наблюдатели о завершении передачи. Обратите внимание, что помимо вызова метода <xref:System.IObserver%601.OnCompleted%2A> для каждого наблюдателя, метод `GetTemperature` инициирует очистку коллекции <xref:System.Collections.Generic.List%601>. В этом случае поставщик не вызывает метод <xref:System.IObserver%601.OnError%2A> для своих наблюдателей.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Пример  
 Ниже представлен полный пример исходного кода, определяющий реализацию <xref:System.IObservable%601> для приложения контроля температуры. Он содержит структуру `Temperature` для данных, отправляемых наблюдателям, и класс `TemperatureMonitor`, который является реализацией <xref:System.IObservable%601>.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IObservable%601>
- [Шаблон разработки наблюдателя](../../../docs/standard/events/observer-design-pattern.md)
- [Практическое руководство. Реализация объекта Observer](../../../docs/standard/events/how-to-implement-an-observer.md)
- [Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)
