---
title: "Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Практическое руководство. Асинхронный вызов операций с использованием фабрики каналов
В этой теме описывается, каким образом клиент может асинхронно обратиться к операции службы при использовании клиентского приложения, основанного на <xref:System.ServiceModel.ChannelFactory%601>.  \(При вызове службы с помощью объекта <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> можно использовать управляемую событиями модель асинхронных вызовов.  Для получения дополнительной информации см. [Как асинхронно вызывать операции службы](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  Дополнительные сведения об управляемой событиями модели асинхронного вызова см. в разделе [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md).\)  
  
 Служба в этом разделе реализует интерфейс `ICalculator`.  Клиент может асинхронно вызвать операции для этого интерфейса, это означает, что операции типа `Add` разделяются на два метода, `BeginAdd` и `EndAdd`, первый из них инициирует вызов, а второй извлекает результат после завершения операции.  Пример, в котором показана реализация асинхронной операции в службе, см. в разделе [Как асинхронно реализовывать операции службы](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).  Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [Синхронные и асинхронные операции](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
## Процедура  
  
#### Асинхронный вызов операций службы WCF  
  
1.  Запустите средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с параметром `/async`, как показано в следующей команде.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
  
    ```  
  
     Результатом станет создание асинхронной версии клиента контракта службы для операции.  
  
2.  Создайте функцию обратного вызова, вызываемую после завершения асинхронной операции, как показано в следующем примере кода.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  Чтобы асинхронно обратиться к операции службы, создайте клиент и вызовите `Begin[Operation]` \(например `BeginAdd`\) и задайте функцию обратного вызова, как показано в следующем примере кода.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     При выполнении функции обратного вызова клиент вызывает `End<operation>` \(например `EndAdd`\), чтобы извлечь результат.  
  
## Пример  
 Служба, используемая с клиентским кодом, который применяется в предыдущей процедуре, реализует интерфейс `ICalculator`, как показано в следующем коде.  На стороне службы операции контракта `Add` и `Subtract` вызываются синхронно во время выполнения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], даже если на предыдущих этапах клиента выполнялся асинхронный вызов для клиента.  Операции `Multiply` и `Divide` используются для асинхронного вызова службы на стороне службы, даже если клиент вызывает их синхронно.  В этом примере свойству <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> присваивается значение `true`.  Этот параметр свойства в сочетании с реализацией асинхронной модели [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] сообщает среде выполнения о необходимости асинхронного вызова операции.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## См. также  
 [Service Contract: Asynchronous Sample](http://msdn.microsoft.com/ru-ru/833db946-f511-4f64-a26f-2759a11217c7)