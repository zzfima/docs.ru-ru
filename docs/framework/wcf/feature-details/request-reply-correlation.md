---
title: "Корреляция запросов и ответов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29286950cfef7d8e3e2c453bbdcc307c26e641de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="request-reply-correlation"></a>Корреляция запросов и ответов
Корреляция запросов и ответов используется с <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары для реализации двусторонней операции в службе рабочего процесса и с <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пары, вызывающей двустороннюю операцию в другой веб- Служба. При вызове двусторонней операции в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служба может быть либо традиционной, основанной на коде службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], либо службой рабочего процесса. Чтобы использовать корреляцию «запрос-ответ», необходимо использовать двустороннюю привязку, например <xref:System.ServiceModel.BasicHttpBinding>. Шаги инициализации корреляции, связанные с вызовом или реализацией двусторонней операции, похожи и описаны в данном разделе.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Использование корреляции в двусторонней операции с действиями Receive/SendReply  
 Объект <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары используется для реализации двусторонней операции в службе рабочего процесса. Среда выполнения использует корреляцию «запрос-ответ» для обеспечения отправки ответа нужному вызывающему объекту. Если рабочий процесс размещен при помощи объекта <xref:System.ServiceModel.Activities.WorkflowServiceHost>, как бывает со службами рабочего процесса, то достаточно инициализации корреляции по умолчанию. В этом сценарии <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> рабочим процессом используется пара и специальная конфигурация корреляции не требуется.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Явная инициализация корреляции «запрос-ответ»  
 Если параллельно работают другие двусторонние операции, корреляция должна быть явно настроена. Это можно сделать, указав <xref:System.ServiceModel.Activities.CorrelationHandle> и <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, либо путем заключения <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> внутри <xref:System.ServiceModel.Activities.CorrelationScope>. В этом примере настраивается корреляция запросов и ответов на <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары.  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 Вместо явной настройки корреляции можно использовать действие <xref:System.ServiceModel.Activities.CorrelationScope>. <xref:System.ServiceModel.Activities.CorrelationScope> предоставляет явный объект <xref:System.ServiceModel.Activities.CorrelationHandle> содержащимся в нем действиям обмена сообщениями. В этом примере <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пара содержится внутри <xref:System.ServiceModel.Activities.CorrelationScope>. Явная настройка корреляции не требуется.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 Если требуются дополнительные корреляции, их можно настроить с помощью свойства <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> соответствующих действий по обмену сообщениями, использующих нужные типы `CorrelationInitializer`.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Использование корреляции в двусторонней операции с действиями Send/ReceiveReply  
 Хотя <xref:System.ServiceModel.Activities.Receive> действия может использоваться только в службе рабочего процесса, размещенной на <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пары могут использоваться в любой рабочий процесс, необходимо вызвать метод веб-службы. Если рабочий процесс размещен при помощи <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то действует по умолчанию корреляция, описанная в предыдущем разделе; в противном случае корреляцию необходимо настроить либо явно при помощи желаемого <xref:System.ServiceModel.Activities.CorrelationInitializer> и <xref:System.ServiceModel.Activities.CorrelationHandle>, либо при помощи неявного управления обработкой <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 При использовании **добавить ссылку на службу** в службе с двусторонними операциями формируются действия, которые упаковывают <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> явно связать действие, которое внутренне корреляция запросов и ответов указано.
