---
title: Корреляция обмена контекстом
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: da5ab2c89e4e2011c38f5fca99aeb5c2c73801a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="7d013-102">Корреляция обмена контекстом</span><span class="sxs-lookup"><span data-stu-id="7d013-102">Context Exchange Correlation</span></span>
<span data-ttu-id="7d013-103">Корреляция контекста основан на механизме обмена контекстом, описанной в [спецификации протокола обмена контекстом .NET](http://go.microsoft.com/fwlink/?LinkId=166059).</span><span class="sxs-lookup"><span data-stu-id="7d013-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="7d013-104">Для связывания сообщений с нужным экземпляром корреляция контекста использует известный заголовок контекста или файл cookie.</span><span class="sxs-lookup"><span data-stu-id="7d013-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="7d013-105">Для реализации корреляции контекста необходимо использование привязки на основе контекста, например <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> или <xref:System.ServiceModel.NetTcpContextBinding> для конечных точек, предоставляемых для <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7d013-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7d013-106">В этом разделе описана работа корреляции контекста с действиями обмена сообщениями в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d013-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="7d013-107">Использование корреляции контекста</span><span class="sxs-lookup"><span data-stu-id="7d013-107">Using Context Correlation</span></span>  
 <span data-ttu-id="7d013-108">Корреляция контекста используется в том случае, если клиенту необходимо выполнять повторяющиеся вызовы к службе рабочего процесса, а ее размещение было выполнено по одной из привязок контекста.</span><span class="sxs-lookup"><span data-stu-id="7d013-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="7d013-109">Этот тип корреляции инициализируется путем <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d013-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="7d013-110">Контекст возвращается клиенту вместе с ответом, после чего он присоединяет этот контекст к последующим вызовам службы.</span><span class="sxs-lookup"><span data-stu-id="7d013-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="7d013-111">Настройка корреляции контекста в службе рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d013-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="7d013-112">Корреляция контекста инициализируется с помощью объекта <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, связанного с действием <xref:System.ServiceModel.Activities.SendReply>, которое отвечает на исходное входящее сообщение.</span><span class="sxs-lookup"><span data-stu-id="7d013-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="7d013-113">В следующем примере выполняется настройка <xref:System.ServiceModel.Activities.SendReply> для инициализации корреляции контекста.</span><span class="sxs-lookup"><span data-stu-id="7d013-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
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
>  <span data-ttu-id="7d013-114">В данном примере фактически используется два типа корреляции: контекстная корреляция и корреляция запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="7d013-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="7d013-115">Контекстная корреляция используется для того, чтобы направить вызовы от клиентов к нужному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="7d013-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="7d013-116">Корреляция запросов и ответов используется действиями <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> совместно для реализации двусторонней работы, моделируемой этими действиями.</span><span class="sxs-lookup"><span data-stu-id="7d013-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="7d013-117">В этом примере контекстная корреляция явным образом настроен и <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары использует корреляцию запросов и ответов по умолчанию, предоставляемый неявный <xref:System.ServiceModel.Activities.CorrelationHandle> управления <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7d013-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7d013-118">При использовании **ReceiveAndSendReply** явным образом настроен шаблон действия в конструкторе корреляция запросов и ответов рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7d013-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> <span data-ttu-id="7d013-119">Дополнительные сведения о корреляции типа запрос ответ и неявного управления дескриптором взаимосвязи см. в разделе [запрос-ответ](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) и [Общие сведения о корреляции](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d013-119">For more information about request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> <span data-ttu-id="7d013-120">Дополнительные сведения о **ReceiveAndSendReply** шаблон действия в разделе [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span><span class="sxs-lookup"><span data-stu-id="7d013-120">For more information about the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="7d013-121">Последующие действия <xref:System.ServiceModel.Activities.Receive> в службе рабочего процесса могут ссылаться на <xref:System.ServiceModel.Activities.CorrelationHandle>, инициализированный <xref:System.ServiceModel.Activities.SendReply> в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="7d013-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="7d013-122">Затем конечная точка настраивается в <xref:System.ServiceModel.Activities.WorkflowServiceHost> для использования привязки на основе контекста, например <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="7d013-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="7d013-123">Настройка корреляции контекста в клиенте рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7d013-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="7d013-124">Если клиентом является другой рабочий процесс, то корреляцию контекста необходимо настроить также и для клиента.</span><span class="sxs-lookup"><span data-stu-id="7d013-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="7d013-125">В рабочем процессе клиента <xref:System.ServiceModel.Activities.ReceiveReply> из <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пару, которая производила первоначальный вызов к службе рабочего процесса должен быть настроен с <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="7d013-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
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
  
 <span data-ttu-id="7d013-126">После инициализации корреляции все последующие действия <xref:System.ServiceModel.Activities.Send> могут использовать дескриптор <xref:System.ServiceModel.Activities.CorrelationHandle> для вызова методов того же экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="7d013-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="7d013-127">Обратите внимание, что в этих примерах корреляция контекста была настроена явным образом.</span><span class="sxs-lookup"><span data-stu-id="7d013-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="7d013-128">Если рабочий процесс клиента не размещен в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то корреляция должна быть настроена явным образом, если только в действии <xref:System.ServiceModel.Activities.CorrelationScope> не содержатся другие действия.</span><span class="sxs-lookup"><span data-stu-id="7d013-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="7d013-129">Дополнительные сведения о корреляции контекста см. в разделе [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) образца.</span><span class="sxs-lookup"><span data-stu-id="7d013-129">For more information about context correlation, see the [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="7d013-130">Если клиент, который выполняет вызовы службы рабочих процессов, сам не является рабочим процессом, он может производить повторяющиеся вызовы при условии, что контекст, возвращенный первым вызовом службы рабочих процессов, при последующих вызовах явным образом передается обратно.</span><span class="sxs-lookup"><span data-stu-id="7d013-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="7d013-131">Прокси, сформированные при добавлении ссылки на службу в хранилище [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], которые передают этот контекст по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d013-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
