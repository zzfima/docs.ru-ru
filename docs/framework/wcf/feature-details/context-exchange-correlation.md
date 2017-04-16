---
title: "Корреляция обмена контекстом | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Корреляция обмена контекстом
Корреляция контекста реализована на основе механизма обмена контекстом, описанного в разделе [Спецификации протокола обмена контекстом .NET](http://go.microsoft.com/fwlink/?LinkId=166059).Для связывания сообщений с нужным экземпляром корреляция контекста использует известный заголовок контекста или файл cookie.Для реализации корреляции контекста необходимо использование привязки на основе контекста, например <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> или <xref:System.ServiceModel.NetTcpContextBinding> для конечных точек, предоставляемых для <xref:System.ServiceModel.Activities.WorkflowServiceHost>.В этом разделе описана работа корреляции контекста с действиями обмена сообщениями в службе рабочего процесса.  
  
## Использование корреляции контекста  
 Корреляция контекста используется в том случае, если клиенту необходимо выполнять повторяющиеся вызовы к службе рабочего процесса, а ее размещение было выполнено по одной из привязок контекста.Этот тип корреляции инициализируется с помощью пары <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> в службе рабочего процесса.Контекст возвращается клиенту вместе с ответом, после чего он присоединяет этот контекст к последующим вызовам службы.  
  
### Настройка корреляции контекста в службе рабочего процесса  
 Корреляция контекста инициализируется с помощью объекта <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, связанного с действием <xref:System.ServiceModel.Activities.SendReply>, которое отвечает на исходное входящее сообщение.В следующем примере выполняется настройка <xref:System.ServiceModel.Activities.SendReply> для инициализации корреляции контекста.  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  В данном примере фактически используется два типа корреляции: контекстная корреляция и корреляция запросов и ответов.Контекстная корреляция используется для того, чтобы направить вызовы от клиентов к нужному экземпляру.Корреляция запросов и ответов используется действиями <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> совместно для реализации двусторонней работы, моделируемой этими действиями.В данном примере явно настроена только контекстная корреляция, а пара <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> использует корреляцию запросов и ответов по умолчанию, которая обеспечивается при явном управлении дескриптором <xref:System.ServiceModel.Activities.CorrelationHandle> при помощи объекта <xref:System.ServiceModel.Activities.WorkflowServiceHost>.При использовании в конструкторе рабочих процессов шаблона действий в **ReceiveAndSendReply** явно настраивается использование шаблона «запрос\-ответ».[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об управлении обработкой неявной корреляции и корреляции «запрос\-ответ» см. в разделах [Запрос\-ответ](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) и [Общие сведения о корреляции](../../../../docs/framework/wcf/feature-details/correlation-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о шаблоне действия **ReceiveAndSendReply** см. в разделе [ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md).  
  
 Последующие действия <xref:System.ServiceModel.Activities.Receive> в службе рабочего процесса могут ссылаться на <xref:System.ServiceModel.Activities.CorrelationHandle>, инициализированный <xref:System.ServiceModel.Activities.SendReply> в предыдущем примере.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 Затем конечная точка настраивается в <xref:System.ServiceModel.Activities.WorkflowServiceHost> для использования привязки на основе контекста, например <xref:System.ServiceModel.BasicHttpContextBinding>.  
  
```xml  
<endpoint  
  contract=”IOrderContract”  
  binding = “basicHttpContextBinding”  
  address=”http://localhost:8080/OrderService” />  
```  
  
### Настройка корреляции контекста в клиенте рабочего процесса  
 Если клиентом является другой рабочий процесс, то корреляцию контекста необходимо настроить также и для клиента.В рабочем процессе клиента <xref:System.ServiceModel.Activities.ReceiveReply> пару <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>, которая производила первоначальный вызов службы рабочего процесса, необходимо настроить с помощью <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 После инициализации корреляции все последующие действия <xref:System.ServiceModel.Activities.Send> могут использовать дескриптор <xref:System.ServiceModel.Activities.CorrelationHandle> для вызова методов того же экземпляра службы.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 Обратите внимание, что в этих примерах корреляция контекста была настроена явным образом.Если рабочий процесс клиента не размещен в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то корреляция должна быть настроена явным образом, если только в действии <xref:System.ServiceModel.Activities.CorrelationScope> не содержатся другие действия.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] корреляции контекст см. в образце [NetContextExchangeCorrelation](http://msdn.microsoft.com/ru-ru/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf).  
  
 Если клиент, который выполняет вызовы службы рабочих процессов, сам не является рабочим процессом, он может производить повторяющиеся вызовы при условии, что контекст, возвращенный первым вызовом службы рабочих процессов, при последующих вызовах явным образом передается обратно.Прокси, сформированные при добавлении ссылки на службу в хранилище [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], которые передают этот контекст по умолчанию.