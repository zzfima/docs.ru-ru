---
title: "Сохраняемая дуплексная корреляция"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9371729dcac22b0611f8ea3ec29cc59daf5d67b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="durable-duplex-correlation"></a><span data-ttu-id="44ac7-102">Сохраняемая дуплексная корреляция</span><span class="sxs-lookup"><span data-stu-id="44ac7-102">Durable Duplex Correlation</span></span>
<span data-ttu-id="44ac7-103">Сохраняемую дуплексную корреляцию, также называемую корреляцией обратных вызовов, удобно использовать, когда служба рабочего процесса должна отправлять обратный вызов исходному вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="44ac7-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="44ac7-104">В отличие от дуплекса WCF, обратный вызов может выполняться в любой момент в будущем и не связан с одним и тем же каналом или временем существования канала. Единственное требование - у вызывающего должна быть конечная точка, прослушивающая сообщение обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="44ac7-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="44ac7-105">Благодаря этому обеспечивается возможность взаимодействия двух служб рабочего процесса в долговременных диалогах.</span><span class="sxs-lookup"><span data-stu-id="44ac7-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="44ac7-106">В данном разделе приведены общие сведения о сохраняемой дуплексной корреляции.</span><span class="sxs-lookup"><span data-stu-id="44ac7-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="44ac7-107">Использование сохраняемой дуплексной корреляции</span><span class="sxs-lookup"><span data-stu-id="44ac7-107">Using Durable Duplex Correlation</span></span>  
 <span data-ttu-id="44ac7-108">Чтобы использовать сохраняемую дуплексную корреляцию, две службы должны использовать контекстную привязку, которая поддерживает двусторонние операции, такие как <xref:System.ServiceModel.NetTcpContextBinding> или <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="44ac7-109">Вызывающая служба регистрирует <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> с привязкой на их клиентской конечной точке <xref:System.ServiceModel.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="44ac7-110">Принимающая служба получает эти данные в первоначальном вызове, а затем использует их для собственных <xref:System.ServiceModel.Endpoint> в действии <xref:System.ServiceModel.Activities.Send>, выполняющем обратный вызов вызывающей службы.</span><span class="sxs-lookup"><span data-stu-id="44ac7-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="44ac7-111">В этом примере две службы взаимодействуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="44ac7-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="44ac7-112">Первая служба вызывает метод для второй службы, а затем ожидает ответа.</span><span class="sxs-lookup"><span data-stu-id="44ac7-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="44ac7-113">Второй службе известно имя метода обратного вызова, но во время разработки конечная точка службы, реализующая этот метод, неизвестна.</span><span class="sxs-lookup"><span data-stu-id="44ac7-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44ac7-114">Сохраняемая дуплексная корреляция может быть использована только в случае, если параметр <xref:System.ServiceModel.Channels.AddressingVersion> конечной точки установлен в значение <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="44ac7-115">Если нет, то <xref:System.InvalidOperationException> исключение со следующим сообщением: «сообщение содержит заголовок контекста обратного вызова со ссылкой на конечную точку для AddressingVersion ' Addressing200408 (гиперссылка «http://schemas.xmlsoap.org/ws/2004/08/ адресация» http://schemas.xmlsoap.org/ws/2004/08/addressing)'.</span><span class="sxs-lookup"><span data-stu-id="44ac7-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for AddressingVersion 'Addressing200408 ( HYPERLINK "http://schemas.xmlsoap.org/ws/2004/08/addressing" http://schemas.xmlsoap.org/ws/2004/08/addressing)'.</span></span> <span data-ttu-id="44ac7-116">Контекст обратного вызова может быть передан только в случае, если параметр AddressingVersion установлен в значение 'WSAddressing10'».</span><span class="sxs-lookup"><span data-stu-id="44ac7-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'."</span></span>  
  
 <span data-ttu-id="44ac7-117">В следующем примере выполняется размещение службы рабочего процесса, с помощью которой создается обратный вызов <xref:System.ServiceModel.Endpoint> с помощью привязки <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 <span data-ttu-id="44ac7-118">Рабочий процесс, реализующий эту службу рабочего процесса, инициализирует корреляцию обратного вызова со своим действием <xref:System.ServiceModel.Activities.Send> и ссылается на эту конечную точку обратного вызова из действия <xref:System.ServiceModel.Activities.Receive>, для которого выполнена корреляция с действием <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="44ac7-119">В следующем примере представлен рабочий процесс, который возвращается из метода `GetWF1`.</span><span class="sxs-lookup"><span data-stu-id="44ac7-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")                          
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="44ac7-120">Вторая служба рабочего процесса размещается с использованием предоставленной системой контекстной привязки.</span><span class="sxs-lookup"><span data-stu-id="44ac7-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 <span data-ttu-id="44ac7-121">Рабочий процесс, реализующий эту службу рабочего процесса, начинается с действия <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="44ac7-122">Это действие получения инициализирует корреляцию обратного вызова для этой службы, откладывает выполнение на определенный период времени для моделирования долгосрочных работ, а затем выполняет обратный вызов в первую службу с использованием контекста обратного вызова, переданного в первом вызове в службу.</span><span class="sxs-lookup"><span data-stu-id="44ac7-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="44ac7-123">В следующем примере представлен рабочий процесс, который возвращается из вызова `GetWF2`.</span><span class="sxs-lookup"><span data-stu-id="44ac7-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="44ac7-124">Обратите внимание, что в действии <xref:System.ServiceModel.Activities.Send> имеется адрес местозаполнителя `http://www.contoso.com`; фактический адрес, используемый во время выполнения, предоставляется обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="44ac7-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="44ac7-125">При вызове метода `StartOrder` в первом рабочем процессе отображается следующий результат, в котором показан ход выполнения с двумя рабочими процессами.</span><span class="sxs-lookup"><span data-stu-id="44ac7-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
```Output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.   
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 <span data-ttu-id="44ac7-126">В этом примере оба рабочих процесса явно управляют корреляцией с помощью объекта <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="44ac7-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="44ac7-127">Поскольку в этих образцах имеется только одна корреляция, настройки управления <xref:System.ServiceModel.Activities.CorrelationHandle>, заданные по умолчанию, не требуют изменений.</span><span class="sxs-lookup"><span data-stu-id="44ac7-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ac7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="44ac7-128">See Also</span></span>  
 [<span data-ttu-id="44ac7-129">Сохраняемый дуплекс &#91; Образцы WF &#93;</span><span class="sxs-lookup"><span data-stu-id="44ac7-129">Durable Duplex &#91;WF Samples&#93;</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md)
