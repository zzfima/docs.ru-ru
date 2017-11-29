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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 16140f71875357e3a07ac4a5a9134d4ae04e0f43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="request-reply-correlation"></a><span data-ttu-id="05fda-102">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="05fda-102">Request-Reply Correlation</span></span>
<span data-ttu-id="05fda-103">Корреляция запросов и ответов используется с <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары для реализации двусторонней операции в службе рабочего процесса и с <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пары, вызывающей двустороннюю операцию в другой веб- Служба.</span><span class="sxs-lookup"><span data-stu-id="05fda-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="05fda-104">При вызове двусторонней операции в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служба может быть либо традиционной, основанной на коде службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], либо службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05fda-104">When invoking a two-way operation in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, the service can be either a traditional imperative code-based [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service or it can be a workflow service.</span></span> <span data-ttu-id="05fda-105">Чтобы использовать корреляцию «запрос-ответ», необходимо использовать двустороннюю привязку, например <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="05fda-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="05fda-106">Шаги инициализации корреляции, связанные с вызовом или реализацией двусторонней операции, похожи и описаны в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="05fda-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="05fda-107">Использование корреляции в двусторонней операции с действиями Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="05fda-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="05fda-108">Объект <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары используется для реализации двусторонней операции в службе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="05fda-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="05fda-109">Среда выполнения использует корреляцию «запрос-ответ» для обеспечения отправки ответа нужному вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="05fda-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="05fda-110">Если рабочий процесс размещен при помощи объекта <xref:System.ServiceModel.Activities.WorkflowServiceHost>, как бывает со службами рабочего процесса, то достаточно инициализации корреляции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05fda-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="05fda-111">В этом сценарии <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> рабочим процессом используется пара и специальная конфигурация корреляции не требуется.</span><span class="sxs-lookup"><span data-stu-id="05fda-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="05fda-112">Явная инициализация корреляции «запрос-ответ»</span><span class="sxs-lookup"><span data-stu-id="05fda-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="05fda-113">Если параллельно работают другие двусторонние операции, корреляция должна быть явно настроена.</span><span class="sxs-lookup"><span data-stu-id="05fda-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="05fda-114">Это можно сделать, указав <xref:System.ServiceModel.Activities.CorrelationHandle> и <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, либо путем заключения <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> внутри <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="05fda-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="05fda-115">В этом примере настраивается корреляция запросов и ответов на <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пары.</span><span class="sxs-lookup"><span data-stu-id="05fda-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
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
  
 <span data-ttu-id="05fda-116">Вместо явной настройки корреляции можно использовать действие <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="05fda-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="05fda-117"><xref:System.ServiceModel.Activities.CorrelationScope> предоставляет явный объект <xref:System.ServiceModel.Activities.CorrelationHandle> содержащимся в нем действиям обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="05fda-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="05fda-118">В этом примере <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> пара содержится внутри <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="05fda-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="05fda-119">Явная настройка корреляции не требуется.</span><span class="sxs-lookup"><span data-stu-id="05fda-119">No explicit correlation configuration is required.</span></span>  
  
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
  
 <span data-ttu-id="05fda-120">Если требуются дополнительные корреляции, их можно настроить с помощью свойства <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> соответствующих действий по обмену сообщениями, использующих нужные типы `CorrelationInitializer`.</span><span class="sxs-lookup"><span data-stu-id="05fda-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="05fda-121">Использование корреляции в двусторонней операции с действиями Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="05fda-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="05fda-122">Хотя <xref:System.ServiceModel.Activities.Receive> действия может использоваться только в службе рабочего процесса, размещенной на <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> пары могут использоваться в любой рабочий процесс, необходимо вызвать метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="05fda-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="05fda-123">Если рабочий процесс размещен при помощи <xref:System.ServiceModel.Activities.WorkflowServiceHost>, то действует по умолчанию корреляция, описанная в предыдущем разделе; в противном случае корреляцию необходимо настроить либо явно при помощи желаемого <xref:System.ServiceModel.Activities.CorrelationInitializer> и <xref:System.ServiceModel.Activities.CorrelationHandle>, либо при помощи неявного управления обработкой <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="05fda-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="05fda-124">При использовании **добавить ссылку на службу** в службе с двусторонними операциями формируются действия, которые упаковывают <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> явно связать действие, которое внутренне корреляция запросов и ответов указано.</span><span class="sxs-lookup"><span data-stu-id="05fda-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
