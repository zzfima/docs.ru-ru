---
title: Асинхронная модель программирования (APM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
ms.openlocfilehash: 0a9ea3c8c9c589bb5954fa9771ffd1bb095f6d73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140140"
---
# <a name="asynchronous-programming-model-apm"></a>Асинхронная модель программирования (APM)
Асинхронная операция, использующая шаблон разработки <xref:System.IAsyncResult>, реализуется в виде двух методов с именами `BeginOperationName` и `EndOperationName`, которые соответственно начинают и завершают асинхронную операцию *OperationName*. Например, класс <xref:System.IO.FileStream> предоставляет методы <xref:System.IO.FileStream.BeginRead%2A> и <xref:System.IO.FileStream.EndRead%2A> для асинхронного считывания байтов из файла. Эти методы реализуют асинхронную версию метода <xref:System.IO.FileStream.Read%2A> .  
  
> [!NOTE]
> Начиная с версии .NET Framework 4 библиотека параллельных задач предоставляет новую модель для асинхронного и параллельного программирования. Дополнительные сведения см. в разделах [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) и [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).)  
  
 После вызова метода `BeginOperationName` приложение может продолжить выполнение инструкций в вызывающем потоке, пока асинхронная операция выполняется в другом потоке. Для каждого вызова метода `BeginOperationName` приложение должно вызывать метод `EndOperationName`, получающий результаты операции.  
  
## <a name="beginning-an-asynchronous-operation"></a>Начало асинхронной операции  
 Метод `BeginOperationName` начинает асинхронную операцию *OperationName* и возвращает объект, реализующий интерфейс <xref:System.IAsyncResult>. В объектах<xref:System.IAsyncResult> хранятся сведения об асинхронных операциях. В таблице ниже приведены сведения об асинхронной операции.  
  
|Участник|Описание:|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|Относящийся к необязательному приложению объект, содержащий сведения об асинхронной операции.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|Объект <xref:System.Threading.WaitHandle> , который можно использовать, чтобы заблокировать выполнение приложения до завершения асинхронной операции.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|Значение, показывающее, что асинхронная операция выполнена в потоке, который использовался для вызова метода `BeginOperationName`, а не в отдельном потоке <xref:System.Threading.ThreadPool>.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|Значение, показывающее, выполнена ли асинхронная операция.|  
  
 Метод `BeginOperationName` принимает любые параметры, объявленные в сигнатуре синхронной версии метода, которые передаются по значению или по ссылке. Выходные параметры не входят в сигнатуру метода `BeginOperationName`. В сигнатуру метода `BeginOperationName` также входят два дополнительных параметра. Первый из них определяет делегат <xref:System.AsyncCallback> , который ссылается на метод, вызываемый при завершении асинхронной операции. Вызывающий объект может указать значение `null` (`Nothing` в Visual Basic), если не нужно вызывать метод при завершении операции. Вторым дополнительным параметром является определяемый пользователем объект. Этот объект можно использовать для передачи сведений о состоянии, относящихся к приложению, в метод, который вызывается при завершении асинхронной операции. Если метод `BeginOperationName` принимает дополнительные параметры, относящиеся к операции, например массив байт для хранения байт, считанных из файла, объект <xref:System.AsyncCallback> и объект состояния приложения являются последними параметрами в сигнатуре метода `BeginOperationName`.  
  
 `BeginOperationName` немедленно возвращает управление в вызывающий поток. Если метод `BeginOperationName` создает исключения, это происходит до запуска асинхронной операции. Если метод `BeginOperationName` создает исключения, метод обратного вызова не вызывается.  
  
## <a name="ending-an-asynchronous-operation"></a>Завершение асинхронной операции  
 Метод `EndOperationName` завершает асинхронную операцию *OperationName*. Возвращаемое значение метода `EndOperationName` имеет тот же тип, что и значение его синхронной версии, и определяется асинхронной операцией. Например, метод <xref:System.IO.FileStream.EndRead%2A> возвращает число байтов, считанных из потока <xref:System.IO.FileStream> , а метод <xref:System.Net.Dns.EndGetHostByName%2A> возвращает объект <xref:System.Net.IPHostEntry> , содержащий сведения о сервере. Метод `EndOperationName` принимает любые выходные параметры out и ref, объявленные в сигнатуре синхронной версии метода. В дополнение к параметрам из синхронного метода метод `EndOperationName` также включает параметр <xref:System.IAsyncResult>. Вызывающие объекты должны передавать экземпляр, возвращаемый соответствующим вызовом метода `BeginOperationName`.  
  
 Если асинхронная операция, представленная объектом <xref:System.IAsyncResult>, не завершилась к моменту вызова метода `EndOperationName`, метод `EndOperationName` блокирует выполнение вызывающего потока до момента завершения асинхронной операции. Исключения, создаваемые асинхронной операцией, возникают из метода `EndOperationName`. Многократный вызов метода `EndOperationName` с одним экземпляром <xref:System.IAsyncResult> не определен. Аналогично, вызов метода `EndOperationName` с объектом <xref:System.IAsyncResult>, который не был возвращен соответствующим методом Begin, также имеет неопределенный эффект.  
  
> [!NOTE]
> В случае реализации этих неопределенных сценариев рекомендуется вызывать исключение <xref:System.InvalidOperationException>.  
  
> [!NOTE]
> В случае реализации этого шаблона разработки необходимо уведомить вызывающий объект о завершении асинхронной операции, установив свойство <xref:System.IAsyncResult.IsCompleted%2A> в значение true, вызвав асинхронный метод обратного вызова (если он указан) и отправив сигнал <xref:System.IAsyncResult.AsyncWaitHandle%2A>.  
  
 Разработчики приложений имеют выбор способов доступа к результатам асинхронной операции. Правильный выбор зависит от того, содержит ли приложение инструкции, которые могут выполняться, пока не завершена операция. Если приложение не может выполнять дополнительную работу, пока не получены результаты асинхронной операции, его необходимо заблокировать до момента, когда станут доступны результаты. Чтобы заблокировать работу до завершения асинхронной операции, используйте один из описанных ниже способов.  
  
- Вызов метода `EndOperationName` из главного потока приложения блокирует выполнение приложения до завершения операции. Пример с демонстрацией этого способа см. в статье [Блокировка выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
- Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> , чтобы заблокировать выполнение приложения до завершения одной или нескольких операций. Пример, демонстрирующий этот способ, см. в разделе [Блокировка выполнения приложения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 В приложениях, которые не нужно блокировать до завершения асинхронной операции, можно использовать один из описанных ниже способов.  
  
- Можно запрашивать состояние выполнения операции, периодически проверяя свойство <xref:System.IAsyncResult.IsCompleted%2A>, а когда операция будет завершена, вызвать метод `EndOperationName`. Пример, демонстрирующий этот способ, см. в разделе [Запрос состояния асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
- Используйте делегат <xref:System.AsyncCallback> для указания метода, который должен вызываться при завершении операции. Пример, демонстрирующий этот способ, см. в разделе [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Асинхронный вызов синхронных методов](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)
- [Использование делегата AsyncCallback и объекта состояния](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
