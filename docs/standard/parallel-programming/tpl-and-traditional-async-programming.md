---
title: Библиотека параллельных задач и традиционное асинхронное программирование .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, with other asynchronous models
ms.assetid: e7b31170-a156-433f-9f26-b1fc7cd1776f
ms.openlocfilehash: 27766c10d0624b5eda8256a3211662036a1b16b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139950"
---
# <a name="tpl-and-traditional-net-framework-asynchronous-programming"></a>Библиотека параллельных задач и традиционное асинхронное программирование .NET Framework
Платформа .NET Framework предоставляет следующие две стандартные модели для выполнения асинхронных операций ввода-вывода и вычислений.  
  
- Асинхронная модель программирования (APM), в которой асинхронные операции представляются с помощью пары методов Begin и End, таких как <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> и <xref:System.IO.Stream.EndRead%2A?displayProperty=nameWithType>.  
  
- Асинхронная модель на основе событий (EAP), в которой асинхронные операции представлены с помощью пары метода и события, называемых *имя_операции*Async и *имя_операции*Completed, например, <xref:System.Net.WebClient.DownloadStringAsync%2A?displayProperty=nameWithType> и <xref:System.Net.WebClient.DownloadStringCompleted?displayProperty=nameWithType>. (Модель EAP появилась в .NET Framework версии 2.0.)  
  
 Библиотека параллельных задач (TPL) может использоваться различными способами вместе с любой из асинхронных моделей. Вы можете предоставлять операции APM и EAP как задачи для пользователей библиотеки или предоставлять модели APM, но использовать объекты задач для их внутренней реализации. В обоих случаях с помощью объектов задач можно упростить код и использовать преимущества следующих полезных функций.  
  
- Регистрация обратных вызовов в форме продолжений задачи в любое время после запуска задачи.  
  
- Согласование нескольких операций, которые выполняются в ответ на метод `Begin_` с помощью методов <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> и <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> или методов <xref:System.Threading.Tasks.Task.WaitAll%2A> или <xref:System.Threading.Tasks.Task.WaitAny%2A>.  
  
- Инкапсуляция асинхронных операций ввода-вывода и вычислений в одном и том же объекте задачи.  
  
- Мониторинг состояния объекта задачи.  
  
- Маршалирование состояния операции в объекте задачи с помощью <xref:System.Threading.Tasks.TaskCompletionSource%601>.  
  
## <a name="wrapping-apm-operations-in-a-task"></a>Включение операций APM в задачу  
 Оба класса <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType> и <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> предоставляют несколько перегрузок методов <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType>, которые позволяют инкапсулировать пару методов Begin и End APM в одном экземпляре <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Различные перегрузки размещают все пары методов Begin и End, имеющие от нуля до трех входных параметров.  
  
 Для пар, содержащих методы `End`, возвращающие значение (`Function` в Visual Basic), используйте методы в объекте <xref:System.Threading.Tasks.TaskFactory%601>, который создает <xref:System.Threading.Tasks.Task%601>. Для методов `End`, возвращающих значение void (`Sub` в Visual Basic), используйте методы в объекте <xref:System.Threading.Tasks.TaskFactory>, который создает <xref:System.Threading.Tasks.Task>.  
  
 Для тех нескольких случаев, в которых метод `Begin` имеет более трех параметров или содержит параметры `ref` или `out`, предоставляются дополнительные перегрузки `FromAsync`, которые инкапсулируют только метод `End`.  
  
 В следующем примере показана сигнатура для перегрузки `FromAsync`, которая соответствует методам <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> и <xref:System.IO.FileStream.EndRead%2A?displayProperty=nameWithType>. Эта перегрузка принимает три входных параметра, как показано ниже.  
  
 [!code-csharp[FromAsync#01](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#01)]
 [!code-vb[FromAsync#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#01)]  
  
 Первый параметр является делегатом <xref:System.Func%606>, который соответствует сигнатуре метода <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>. Второй параметр — это делегат <xref:System.Func%602>, который принимает <xref:System.IAsyncResult> и возвращает `TResult`. Поскольку метод <xref:System.IO.FileStream.EndRead%2A> возвращает целое число, компилятор выводит тип `TResult` как <xref:System.Int32> и тип задачи как <xref:System.Threading.Tasks.Task>. Последние четыре параметра идентичны параметрам в методе <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>:  
  
- буфер для хранения файлов данных;  
  
- смещение в буфере, с которого начинается запись;  
  
- максимальный объем данных для чтения из файла;  
  
- дополнительный объект, который хранит пользовательские данные состояния для передачи в обратный вызов.  
  
### <a name="using-continuewith-for-the-callback-functionality"></a>Использование ContinueWith для функциональности обратного вызова  
 Если требуется доступ к данным в файле, а не просто количество байтов, метода <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> недостаточно. Вместо него используйте <xref:System.Threading.Tasks.Task>, чье свойство `Result` содержит данные файла. Это можно сделать, добавив продолжение в исходную задачу. Продолжение выполняет работу, которая обычно выполняется делегатом <xref:System.AsyncCallback>. Оно вызывается, когда завершается предшествующая задача и заполняется буфер данных. (Объект <xref:System.IO.FileStream> должен быть закрыт перед возвратом.)  
  
 В следующем примере показано, как возвращать объект <xref:System.Threading.Tasks.Task>, инкапсулирующий пару BeginRead и EndRead класса <xref:System.IO.FileStream>.  
  
 [!code-csharp[FromAsync#03](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#03)]
 [!code-vb[FromAsync#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#03)]  
  
 Затем может быть вызван метод, как показано ниже.  
  
 [!code-csharp[FromAsync#04](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#04)]
 [!code-vb[FromAsync#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#04)]  
  
### <a name="providing-custom-state-data"></a>Предоставление пользовательских данных состояния  
 Если в обычных операциях <xref:System.IAsyncResult> вашему делегату <xref:System.AsyncCallback> требуются некоторые пользовательские данные состояния, вы должны передать их с помощью последнего параметра в методе `Begin`, чтобы эти данные могли быть упакованы в объект <xref:System.IAsyncResult>, который в конечном счете передается в метод обратного вызова. Обычно при использовании методов `FromAsync` это не требуется. Если пользовательские данные известны продолжению, их можно захватить непосредственно в делегате продолжения. Следующий пример похож на предыдущий пример, но вместо проверки свойства `Result` в предшествующей задаче продолжение проверяет пользовательские данные состояния, напрямую доступные пользовательскому делегату продолжения.  
  
 [!code-csharp[FromAsync#05](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#05)]
 [!code-vb[FromAsync#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#05)]  
  
### <a name="synchronizing-multiple-fromasync-tasks"></a>Синхронизация нескольких задач FromAsync  
 Статические методы <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> и <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> обеспечивают дополнительную гибкость при использовании в сочетании с методами `FromAsync`. В следующем примере показывается, как инициировать несколько асинхронных операций ввода-вывода, а затем подождать их завершения до выполнения продолжения.  
  
 [!code-csharp[FromAsync#06](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#06)]
 [!code-vb[FromAsync#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#06)]  
  
### <a name="fromasync-tasks-for-only-the-end-method"></a>Задачи FromAsync только для метода End  
 В тех нескольких случаях, когда метод `Begin` требует более трех входных параметров или имеет параметры `ref` или `out`, можно использовать перегрузки `FromAsync`, например <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%600%7D%29?displayProperty=nameWithType>, представляющие только метод `End`. Эти методы могут также использоваться в любом сценарии, в котором передается объект <xref:System.IAsyncResult> и требуется инкапсулировать его в задачу.  
  
 [!code-csharp[FromAsync#07](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#07)]
 [!code-vb[FromAsync#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#07)]  
  
### <a name="starting-and-canceling-fromasync-tasks"></a>Запуск и отмена задач FromAsync  
 Задача, возвращаемая методом `FromAsync`, имеет состояние WaitingForActivation и будет запущена системой в некоторой точке после создания задачи. При попытке вызвать Start в такой задаче возникнет исключение.  
  
 Вы не можете отменить задачу `FromAsync`, поскольку базовые API .NET Framework в настоящее время не поддерживают отмену выполняющегося файла или сетевой операции ввода-вывода. Можно добавить функциональность отмены в метод, который инкапсулирует вызов `FromAsync`, но вы можете отвечать только на отмену перед тем как вызывается `FromAsync` или после его завершения (например, в задаче продолжения).  
  
 Некоторые классы, поддерживающие EAP, например <xref:System.Net.WebClient>, поддерживают отмену, и можно интегрировать эту встроенную функциональность отмены с помощью токенов отмены.  
  
## <a name="exposing-complex-eap-operations-as-tasks"></a>Предоставление сложных операций EAP как задач  
 Библиотека параллельных задач не предоставляет методы, которые специально разработаны для инкапсуляции асинхронной операции на основе события тем же способом, которым семейство методов `FromAsync` создает программу-оболочку шаблона <xref:System.IAsyncResult>. Однако TPL предоставляет класс <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType>, который может использоваться для представления любого произвольного набора операций как <xref:System.Threading.Tasks.Task%601>. Операции могут быть синхронными или асинхронными, а также могут быть операциями ввода-вывода и вычислений.  
  
 В следующем примере показано, как использовать <xref:System.Threading.Tasks.TaskCompletionSource%601> для предоставления набора асинхронных операций <xref:System.Net.WebClient> клиентскому коду как базовой <xref:System.Threading.Tasks.Task%601>. Этот метод позволяет ввести массив URL-адресов, слово или имя для поиска, а затем возвращает число, указывающее, сколько раз условие поиска обнаруживается на каждом сайте.  
  
 [!code-csharp[FromAsync#10](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/snippet10.cs#10)]
 [!code-vb[FromAsync#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/snippet10.vb#10)]  
  
 Более полный пример, включающий дополнительную обработку исключений и показывающий, как вызывать этот метод из клиентского кода, см. в разделе [Как создавать оболочки шаблонов EAP в задаче](../../../docs/standard/parallel-programming/how-to-wrap-eap-patterns-in-a-task.md).  
  
 Следует помнить, что любая задача, созданная объектом <xref:System.Threading.Tasks.TaskCompletionSource%601>, будет запущена этим TaskCompletionSource, и, таким образом, пользовательский код не должен вызывать метод Start в этой задаче.  
  
## <a name="implementing-the-apm-pattern-by-using-tasks"></a>Реализация шаблона APM с помощью задач  
 В некоторых сценариях может возникнуть необходимость напрямую предоставить шаблон <xref:System.IAsyncResult> с помощью пары методов Begin/End в API. Например, вам может потребоваться поддерживать согласованность с существующими API или у вас могут быть автоматизированные средства, которым требуется этот шаблон. В таких случаях можно использовать задачи для упрощения реализации шаблона APM внутренним образом.  
  
 В следующем примере показано, как использовать задачи для реализации пары методов Begin и End APM для долгосрочного метода вычислений.  
  
 [!code-csharp[FromAsync#09](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#09)]
 [!code-vb[FromAsync#09](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#09)]  
  
## <a name="using-the-streamextensions-sample-code"></a>Использование примера кода StreamExtensions  
 Файл Streamextensions.cs (см. [примеры параллельного программирования в .NET Framework 4](https://code.msdn.microsoft.com/ParExtSamples)) содержит несколько базовых реализаций, в которых используются объекты задачи для асинхронных операций файлового и сетевого ввода-вывода.  
  
## <a name="see-also"></a>См. также

- [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
