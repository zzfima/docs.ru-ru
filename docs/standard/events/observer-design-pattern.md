---
title: Шаблон разработки Observer
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IObserver(Of T) interface
- IObservable<T> interface
- IObserver<T> interface
- IObservable(Of T) interface
- observer design pattern [.NET Framework]
ms.assetid: 3680171f-f522-453c-aa4a-54f755a78f88
ms.openlocfilehash: 817337cec604a431f9f7d4eacb04378ee0d3c227
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131576"
---
# <a name="observer-design-pattern"></a>Шаблон разработки Observer

Шаблон разработки наблюдателя позволяет подписчику регистрироваться у поставщика и получать от него уведомления. Он подходит для любого сценария, в котором требуется использование push-уведомлений. Шаблон определяет *поставщик* (также называемый *субъектом* или *наблюдаемым*) и ноль, один или несколько *наблюдателей*. Наблюдатели регистрируются у поставщика, и при возникновении предварительно заданного условия, события или изменения состояния поставщик автоматически уведомляет все наблюдатели путем вызова одного из их методов. В вызове метода поставщик также может предоставить наблюдателям сведения о текущем состоянии. В .NET Framework шаблон разработки наблюдателя применяется путем реализации универсальных интерфейсов <xref:System.IObservable%601?displayProperty=nameWithType> и <xref:System.IObserver%601?displayProperty=nameWithType>. Параметр универсального типа представляет тип, который предоставляет сведения об уведомлении.

## <a name="applying-the-pattern"></a>Применение шаблона

Шаблон разработки наблюдателя подходит для распределенных push-уведомлений, так как он поддерживает четкое разделение двух разных компонентов или уровней приложения, таких как уровень источника данных (бизнес-логика) и уровень пользовательского интерфейса (отображение). Шаблон можно реализовывать во всех случаях, когда поставщик использует обратные вызовы для предоставления текущих сведений клиентам.

Для реализации шаблона необходимы перечисленные ниже элементы.

- Поставщик или субъект, то есть объект, отправляющий уведомления наблюдателям. Поставщик — это класс или структура, реализующие интерфейс <xref:System.IObservable%601>. Поставщик должен реализовывать единственный метод, <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>, вызываемый наблюдателями, которым требуется получать уведомления от поставщика.

- Наблюдатель, то есть объект, получающий уведомления от поставщика. Наблюдатель — это класс или структура, реализующие интерфейс <xref:System.IObserver%601>. Наблюдатель должен реализовывать три метода, которые вызываются поставщиком:

  - метод <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, предоставляющий наблюдателю новые или текущие сведения;

  - метод <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, информирующий наблюдатель о том, что произошла ошибка;

  - метод <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, указывающий, что поставщик завершил отправку уведомлений.

- Механизм, который позволяет поставщику отслеживать наблюдатели. Как правило, поставщик использует объект контейнера, например объект <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, для хранения ссылок на реализации <xref:System.IObserver%601>, которые подписаны на уведомления. Использование контейнера хранилища в этих целях позволяет поставщику обрабатывать от нуля до неограниченного числа наблюдателей. Порядок, в котором наблюдатели получают уведомления, не определен. Поставщик может использовать любой метод для определения порядка.

- Реализация <xref:System.IDisposable>, которая позволяет поставщику удалять наблюдатели по завершении уведомления. Наблюдатели получают ссылку на реализацию <xref:System.IDisposable> из метода <xref:System.IObservable%601.Subscribe%2A>, поэтому они также могут вызывать метод <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>, чтобы отменить подписку, прежде чем поставщик завершит отправку уведомлений.

- Объект, содержащий данные, которые поставщик отправляет своим наблюдателям. Тип этого объекта соответствует параметру универсального типа интерфейсов <xref:System.IObservable%601> и <xref:System.IObserver%601>. Несмотря на то что этот объект может совпадать с реализацией <xref:System.IObservable%601>, чаще всего это отдельный тип.

> [!NOTE]
> Помимо реализации шаблона разработки наблюдателя, возможно, вас заинтересуют библиотеки, создаваемые с помощью интерфейсов <xref:System.IObservable%601> и <xref:System.IObserver%601>. Например, [Реактивные расширения для .NET (Rx)](https://docs.microsoft.com/previous-versions/dotnet/reactive-extensions/hh242985(v=vs.103)) — это набор методов расширения и стандартных операторов последовательности LINQ для поддержки асинхронного программирования.

## <a name="implementing-the-pattern"></a>Реализация шаблона

В примере ниже шаблон разработки наблюдателя используется для реализации информационной системы выдачи багажа в аэропорту. Класс `BaggageInfo` предоставляет информацию о прибывающих рейсах и лентах, с которых можно получить багаж с каждого рейса. Он показан в примере ниже.

[!code-csharp[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#1)]
[!code-vb[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#1)]

Класс `BaggageHandler` отвечает за получение информации о прибывающих рейсах и лентах выдачи багажа. На внутреннем уровне он поддерживает две коллекции:

- `observers` — коллекция клиентов, которые будут получать обновленную информацию;

- `flights` — коллекция рейсов и соответствующих им лент.

Обе коллекции представлены универсальными объектами <xref:System.Collections.Generic.List%601>, экземпляры которых создаются в конструкторе класса `BaggageHandler`. Исходный код для класса `BaggageHandler` показан в примере ниже.

[!code-csharp[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#2)]
[!code-vb[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#2)]

Клиенты, которым требуется получить обновленную информацию, вызывают метод `BaggageHandler.Subscribe`. Если клиент ранее не подписался на уведомления, ссылка на реализацию <xref:System.IObserver%601> клиента добавляется в коллекцию `observers`.

Чтобы указать, что багаж с определенного рейса либо выгружается, либо более не выгружается, можно вызвать перегруженный метод `BaggageHandler.BaggageStatus`. В первом случае методу передается номер рейса, аэропорт его отправления и лента, на которую выгружается багаж. Во втором случае методу передается только номер рейса. Для выгружаемого багажа метод проверяет, существует ли переданная методу информация `BaggageInfo` в коллекции `flights`. Если нет, метод добавляет эту информацию и вызывает метод `OnNext` каждого наблюдателя. Для рейсов, багаж которых более не выгружается, метод проверяет, хранится ли информация об этом рейсе в коллекции `flights`. Если да, метод вызывает метод `OnNext` каждого наблюдателя и удаляет объект `BaggageInfo` из коллекции `flights`.

После посадки последнего рейса текущего дня и обработки его багажа вызывается метод `BaggageHandler.LastBaggageClaimed`. Этот метод вызывает метод `OnCompleted` каждого наблюдателя, чтобы указать, что все уведомления завершены, а затем очищает коллекцию `observers`.

Метод <xref:System.IObservable%601.Subscribe%2A> поставщика возвращает реализацию <xref:System.IDisposable>, позволяющую наблюдателям прекратить получение уведомлений до вызова метода <xref:System.IObserver%601.OnCompleted%2A>. Исходный код для этого класса `Unsubscriber(Of BaggageInfo)` показан в примере ниже. Когда в методе `BaggageHandler.Subscribe` создается экземпляр этого класса, ему передается ссылка на коллекцию `observers` и ссылка на наблюдатель, добавленный в эту коллекцию. Эти ссылки присваиваются локальным переменным. Когда вызывается метод `Dispose` объекта, он проверяет, существует ли еще наблюдатель в коллекции `observers`, и если это так, удаляет наблюдатель.

[!code-csharp[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#3)]
[!code-vb[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#3)]

В примере ниже приводится реализация интерфейса <xref:System.IObserver%601> с именем `ArrivalsMonitor`, которая является базовым классом, выводящим сведения о выдаче багажа. Сведения выводятся в алфавитном порядке по названию города отправления. Методы `ArrivalsMonitor` помечаются как `overridable` (в Visual Basic) или `virtual` (в C#), поэтому все они могут переопределяться производным классом.

[!code-csharp[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/observer.cs#4)]
[!code-vb[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/observer.vb#4)]

Класс `ArrivalsMonitor` включает в себя методы `Subscribe` и `Unsubscribe`. Метод `Subscribe` позволяет классу сохранять реализацию <xref:System.IDisposable>, возвращаемую вызовом <xref:System.IObservable%601.Subscribe%2A>, в закрытой переменной. Метод `Unsubscribe` позволяет классу отменить подписку на уведомления путем вызова реализации класса <xref:System.IDisposable.Dispose%2A> поставщика. `ArrivalsMonitor` также предоставляет реализации методов <xref:System.IObserver%601.OnNext%2A>, <xref:System.IObserver%601.OnError%2A> и <xref:System.IObserver%601.OnCompleted%2A>. Только реализация <xref:System.IObserver%601.OnNext%2A> содержит значительный объем кода. Метод работает с закрытым отсортированным универсальным объектом <xref:System.Collections.Generic.List%601>, содержащим информацию об аэропортах отправления для прибывающих рейсов и о лентах, где можно найти багаж с этих рейсов. Если класс `BaggageHandler` сообщает о прибытии нового рейса, реализация метода <xref:System.IObserver%601.OnNext%2A> добавляет информацию об этом рейсе в список. Если класс `BaggageHandler` сообщает о том, что багаж рейса выгружен, метод <xref:System.IObserver%601.OnNext%2A> удаляет этот рейс из списка. При любом изменении список сортируется и выводится на консоль.

В примере ниже содержится точка входа в приложение, создающая экземпляр класса `BaggageHandler` и два экземпляра класса `ArrivalsMonitor` и использующая метод `BaggageHandler.BaggageStatus` для добавления и удаления информации о прибывающих рейсах. Во всех случаях наблюдатели получают обновления и правильно выводят информацию о выдаче багажа.

[!code-csharp[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/program.cs#5)]
[!code-vb[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/module1.vb#5)]

## <a name="related-topics"></a>См. также

|Заголовок|ОПИСАНИЕ|
|-----------|-----------------|
|[Рекомендации по шаблону разработки Observer](../../../docs/standard/events/observer-design-pattern-best-practices.md)|Рекомендации по разработке приложений, реализующих шаблон разработки наблюдателя.|
|[Практическое руководство. Реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md)|Пошаговая реализация поставщика для приложения контроля температуры.|
|[Практическое руководство. Реализация наблюдателя](../../../docs/standard/events/how-to-implement-an-observer.md)|Пошаговая реализация наблюдателя для приложения контроля температуры.|
