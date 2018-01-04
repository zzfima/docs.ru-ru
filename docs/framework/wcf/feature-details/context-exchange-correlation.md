---
title: "Корреляция обмена контекстом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ab311974b1fe8cbc2707ee0818806d6264a1573
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="context-exchange-correlation"></a>Корреляция обмена контекстом
Корреляция контекста основан на механизме обмена контекстом, описанной в [спецификации протокола обмена контекстом .NET](http://go.microsoft.com/fwlink/?LinkId=166059). Для связывания сообщений с нужным экземпляром корреляция контекста использует известный заголовок контекста или файл cookie. Для реализации корреляции контекста необходимо использование привязки на основе контекста, например <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> или <xref:System.ServiceModel.NetTcpContextBinding> для конечных точек, предоставляемых для <xref:System.ServiceModel.Activities.WorkflowServiceHost>. В этом разделе описана работа корреляции контекста с действиями обмена сообщениями в службе рабочего процесса.  
  
## <a name="using-context-correlation"></a>Использование корреляции контекста  
 Корреляция контекста используется в том случае, если клиенту необходимо выполнять повторяющиеся вызовы к службе рабочего процесса, а ее размещение было выполнено по одной из привязок контекста. Этот тип корреляции инициализируется путем <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары в службе рабочего процесса. Контекст возвращается клиенту вместе с ответом, после чего он присоединяет этот контекст к последующим вызовам службы.  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>Настройка корреляции контекста в службе рабочего процесса  
 Корреляция контекста инициализируется с помощью объекта <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, связанного с действием <xref:System.ServiceModel.Activities.SendReply>, которое отвечает на исходное входящее сообщение. В следующем примере выполняется настройка <xref:System.ServiceModel.Activities.SendReply> для инициализации корреляции контекста.  
  
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
>  В данном примере фактически используется два типа корреляции: контекстная корреляция и корреляция запросов и ответов. Контекстная корреляция используется для того, чтобы направить вызовы от клиентов к нужному экземпляру. Корреляция запросов и ответов используется действиями <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> совместно для реализации двусторонней работы, моделируемой этими действиями. В этом примере контекстная корреляция явным образом настроен и <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары использует корреляцию запросов и ответов по умолчанию, предоставляемый неявный <xref:System.ServiceModel.Activities.CorrelationHandle> управления <xref:System.ServiceModel.Activities.WorkflowServiceHost>. При использовании **ReceiveAndSendReply** явным образом настроен шаблон действия в конструкторе корреляция запросов и ответов рабочего процесса. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Корреляция запросов и ответов и неявного управления дескриптором взаимосвязи, в разделе [запрос-ответ](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) и [Общие сведения о корреляции](../../../../docs/framework/wcf/feature-details/correlation-overview.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]**ReceiveAndSendReply** шаблон действия в разделе [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).  
  
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
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>Настройка корреляции контекста в клиенте рабочего процесса  
 Если клиентом является другой рабочий процесс, то корреляцию контекста необходимо настроить также и для клиента. В рабочем процессе клиента <xref:System.ServiceModel.Activities.ReceiveReply> из <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пару, которая производила первоначальный вызов к службе рабочего процесса должен быть настроен с <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
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
  
 Обратите внимание, что в этих примерах корреляция контекста была настроена явным образом. Если рабочий процесс клиента не размещен в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то корреляция должна быть настроена явным образом, если только в действии <xref:System.ServiceModel.Activities.CorrelationScope> не содержатся другие действия. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Корреляция контекста, в разделе [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) образца.  
  
 Если клиент, который выполняет вызовы службы рабочих процессов, сам не является рабочим процессом, он может производить повторяющиеся вызовы при условии, что контекст, возвращенный первым вызовом службы рабочих процессов, при последующих вызовах явным образом передается обратно. Прокси, сформированные при добавлении ссылки на службу в хранилище [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], которые передают этот контекст по умолчанию.
