---
title: "Асинхронные операции (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "асинхронные операции [службы WCF Data Services]"
  - "Службы WCF Data Services, асинхронные операции"
  - "Службы WCF Data Services, клиентская библиотека"
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Асинхронные операции (службы WCF Data Services)
При разработке веб\-приложений необходимо учитывать наличие большего времени задержки между клиентом и сервером по сравнению с приложениями, выполняющимися во внутренних сетях.  Для оптимизации производительности и взаимодействия приложения с пользователем рекомендуется использовать асинхронные методы классов <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601> при доступе к серверам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] через Интернет.  
  
 Хотя серверы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] обрабатывают запросы HTTP асинхронно, некоторое методы клиентской библиотеки служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] являются синхронными и ожидают завершения всего обмена запрос\-ответ до продолжения выполнения.  Асинхронные методы клиентской библиотеки служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] не ожидают завершения этого обмена и дают возможность приложению в это время поддерживать быстро реагирующий пользовательский интерфейс.  
  
 Асинхронные операции можно выполнять с помощью пары методов классов <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>, которые соответственно начинаются со слова *Begin* и *End*.  Методы *Begin* регистрируют делегат, который будет вызван службой по завершении операции.  Методы *End* должны вызываться в делегате, зарегистрированном для обработки обратного вызова по завершении операций.  При вызове метода *End* для завершения асинхронной операции сделать это нужно с использованием того же экземпляра <xref:System.Data.Services.Client.DataServiceQuery%601> или <xref:System.Data.Services.Client.DataServiceContext>, который использовался для запуска операции.  Каждый метод *Begin* принимает параметр `state`, который может передавать объект состояния в метод обратного вызова.  Этот объект состояния извлекается из интерфейса <xref:System.IAsyncResult>, предоставляемого методом обратного вызова и используемого при вызове соответствующего метода *End* для завершения асинхронной операции.  Например, если передать экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> в качестве параметра `state` при вызове применительно к экземпляру метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>, тот же экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> возвращается интерфейсом <xref:System.IAsyncResult>.  Этот экземпляр <xref:System.Data.Services.Client.DataServiceQuery%601> затем используется при вызове метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для завершения операции запроса.  Для получения дополнительной информации см. [Как выполнить асинхронные запросы службы данных](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Клиентские библиотеки, предоставленные в среде .NET Framework для Silverlight, поддерживают только асинхронные операции.  Дополнительные сведения см. в разделе [Службы WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=143149)  
  
 Клиентские библиотеки .NET Framework поддерживают следующие асинхронные операции.  
  
|Операция|Методы|  
|--------------|------------|  
|Выполнение запроса <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Выполнение запроса из контекста <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Выполнение пакетного запроса из контекста <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Загрузка связанной сущности в контекст <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Сохранение изменений в объектах контекста <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## Вопросы использования потоков в асинхронных операциях  
 В многопоточном приложении делегат, зарегистрированный как метод обратного вызова для асинхронной операции, не обязательно вызывать в том же потоке, который использовался для вызова метода *Begin*, создавшего первоначальный запрос.  В приложении, в котором метод обратного вызова должен быть вызван из определенного потока, необходимо выполнить явный маршалинг выполнения метода *End*, который обрабатывает ответ, в нужный поток.  Например, в приложениях на основе Windows Presentation Foundation \(WPF\) и на основе Silverlight необходимо выполнить маршалинг ответа обратно в поток пользовательского интерфейса с помощью метода <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> объекта <xref:System.Windows.Threading.Dispatcher>.  Для получения дополнительной информации см. [Querying the Data Service \(WCF Data Services\/Silverlight\)](http://msdn.microsoft.com/ru-ru/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)