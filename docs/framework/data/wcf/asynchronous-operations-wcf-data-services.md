---
title: Асинхронные операции (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 5191f3d03facaafc64f6df494ff90cd0ce1c1988
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346180"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Асинхронные операции (службы данных WCF)
При разработке веб-приложений необходимо учитывать наличие большего времени задержки между клиентом и сервером по сравнению с приложениями, выполняющимися во внутренних сетях. Чтобы оптимизировать производительность и взаимодействие с пользователем приложения, мы рекомендуем использовать асинхронные методы классов <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601> при доступе к серверам WCF Data Services через Интернет.  
  
 Несмотря на то, что WCF Data Services серверы обрабатывают HTTP-запросы асинхронно, некоторые методы WCF Data Services клиентских библиотек являются синхронными и ожидают завершения всего обмена запроса-ответа до продолжения выполнения. Асинхронные методы клиентских библиотек WCF Data Services не ожидают завершения этого обмена и могут позволить приложению поддерживать реагирующий пользовательский интерфейс.  
  
 Асинхронные операции можно выполнять с помощью пары методов в классах <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>, которые начинаются с *Begin* и *End* соответственно. Методы *Begin* регистрируют делегат, который служба вызывает при завершении операции. Методы *End* должны вызываться в делегате, зарегистрированном для обработчика обратного вызова из завершенных операций. При вызове метода *End* для завершения асинхронной операции необходимо сделать это из того же <xref:System.Data.Services.Client.DataServiceQuery%601> или <xref:System.Data.Services.Client.DataServiceContext> экземпляра, который использовался для начала операции. Каждый метод *Begin* принимает параметр `state`, который может передавать объект состояния обратному вызову. Этот объект состояния извлекается из <xref:System.IAsyncResult>, предоставляемого с обратным вызовом, и используется для вызова соответствующего метода *End* для завершения асинхронной операции. Например, если передать экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> в качестве параметра `state` при вызове применительно к экземпляру метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>, тот же экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> возвращается интерфейсом <xref:System.IAsyncResult>. Этот экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> затем используется при вызове метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для завершения операции запроса. Дополнительные сведения см. [в разделе инструкции. выполнение запросов асинхронной службы данных](how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
> Клиентские библиотеки, предоставленные в среде .NET Framework для Silverlight, поддерживают только асинхронные операции. Дополнительные сведения см. в разделе [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Клиентские библиотеки .NET Framework поддерживают следующие асинхронные операции.  
  
|Операция|Методы|  
|---------------|-------------|  
|Выполнение запроса <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Выполнение запроса из контекста <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Выполнение пакетного запроса из контекста <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Загрузка связанной сущности в контекст <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Сохранение изменений в объектах контекста <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Вопросы использования потоков в асинхронных операциях  
 В многопоточном приложении делегат, зарегистрированный в качестве обратного вызова для асинхронной операции, не обязательно вызывается в том же потоке, который использовался для вызова метода *Begin* , который создает первоначальный запрос. В приложении, где обратный вызов должен быть вызван в определенном потоке, необходимо явным образом маршалировать выполнение метода *End* , который обрабатывает ответ, в нужный поток. Например, в приложениях на основе Windows Presentation Foundation (WPF) и на основе Silverlight необходимо выполнить маршалинг ответа обратно в поток пользовательского интерфейса с помощью метода <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> объекта <xref:System.Windows.Threading.Dispatcher>. Дополнительные сведения см. [в разделе запросы к службе данных (WCF Data Services/Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>См. также:

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
