---
title: "Обработка неупорядоченных сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Обработка неупорядоченных сообщений
Службы рабочих процессов могут зависеть от порядка отправки сообщений.Служба рабочих процессов содержит одно или несколько действий <xref:System.ServiceModel.Activities.Receive>. Каждое из этих действий <xref:System.ServiceModel.Activities.Receive> рассчитано на определенное сообщение.Поскольку доставка данных не гарантируется, отправляемые клиентами сообщения могут задерживаться и доставляться в порядке, на который служба рабочих процессов не рассчитана.Реализация службы рабочих процессов, которая не требует отправки сообщений в определенном порядке, обычно осуществляется с использованием параллельных действий.В результате усложнения протокола приложения рабочий процесс также слишком быстро становится сложным.Функция обработки внеочередных сообщений в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет создать рабочий процесс, исключив сложности реализации вложенных параллельных действий.Обработка внеочередных сообщений поддерживается только каналами, поддерживающими <xref:System.ServiceModel.Channele.ReceiveContext>, например привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ.  
  
## Реализация обработки внеочередных сообщений  
 Чтобы включить обработку внеочередных сообщений, в WorkflowService установите свойство <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в значение `true`.В следующем примере кода показана установка свойства <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> в коде.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
  
```  
  
 Можно также применить атрибут `AllowBufferedReceive` к службе рабочих процессов в XAML, как показано в следующем примере.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## См. также  
 <xref:System.ServiceModel.Channels.ReceiveContext>   
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)