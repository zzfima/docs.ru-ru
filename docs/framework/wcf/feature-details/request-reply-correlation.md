---
title: "Корреляция запросов и ответов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Корреляция запросов и ответов
Корреляция «запрос\-ответ» используется вместе с парой действий <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>, реализующей двустороннюю операцию в службе рабочего процесса и с парой <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>, вызывающей двустороннюю операцию в другой веб\-службе.  При вызове двусторонней операции в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служба может быть либо традиционной, основанной на коде службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], либо службой рабочего процесса.  Чтобы использовать корреляцию «запрос\-ответ», необходимо использовать двустороннюю привязку, например <xref:System.ServiceModel.BasicHttpBinding>.  Шаги инициализации корреляции, связанные с вызовом или реализацией двусторонней операции, похожи и описаны в данном разделе.  
  
## Использование корреляции в двусторонней операции с действиями Receive\/SendReply  
 Пара <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> используется для реализации двусторонней операции в службе рабочего процесса.  Среда выполнения использует корреляцию «запрос\-ответ» для обеспечения отправки ответа нужному вызывающему объекту.  Если рабочий процесс размещен при помощи объекта <xref:System.ServiceModel.Activities.WorkflowServiceHost>, как бывает со службами рабочего процесса, то достаточно инициализации корреляции по умолчанию.  В данном сценарии рабочим процессом используется пара <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> и специальная конфигурация корреляции не требуется.  
  
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
  
### Явная инициализация корреляции «запрос\-ответ»  
 Если параллельно работают другие двусторонние операции, корреляция должна быть явно настроена.  Для этого можно задать объекты <xref:System.ServiceModel.Activities.CorrelationHandle> и <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> или поместить пару <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> в область <xref:System.ServiceModel.Activities.CorrelationScope>.  В данном примере корреляция «запрос\-ответ» настроена на паре <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>.  
  
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
  
 Вместо явной настройки корреляции можно использовать действие <xref:System.ServiceModel.Activities.CorrelationScope>.  <xref:System.ServiceModel.Activities.CorrelationScope> предоставляет явный объект <xref:System.ServiceModel.Activities.CorrelationHandle> содержащимся в нем действиям обмена сообщениями.  В этом примере пара <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> содержится в области <xref:System.ServiceModel.Activities.CorrelationScope>.  Явная настройка корреляции не требуется.  
  
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
  
## Использование корреляции в двусторонней операции с действиями Send\/ReceiveReply  
 Хотя действие <xref:System.ServiceModel.Activities.Receive> можно использовать только в службе рабочего процесса, размещенной на <xref:System.ServiceModel.Activities.WorkflowServiceHost>, действие <xref:System.ServiceModel.Activities.Send> и пару <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> можно использовать в любом рабочем процессе, который должен вызывать метод для веб\-службы.  Если рабочий процесс размещен при помощи <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то действует по умолчанию корреляция, описанная в предыдущем разделе; в противном случае корреляцию необходимо настроить либо явно при помощи желаемого <xref:System.ServiceModel.Activities.CorrelationInitializer> и <xref:System.ServiceModel.Activities.CorrelationHandle>, либо при помощи неявного управления обработкой <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 При применении команды **Добавить ссылку на службу** к службе с двусторонними операциями формируются действия, которые упаковывают парное действие <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> в явно заданной корреляции «запрос\-ответ».