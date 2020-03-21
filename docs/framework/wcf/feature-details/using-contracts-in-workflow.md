---
title: Использование контрактов в рабочих процессах
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: 9f967d75a8e9d24fcfac8b7376a3d4840fba52f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184276"
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="3669f-102">Использование контрактов в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="3669f-102">Using Contracts in Workflow</span></span>
<span data-ttu-id="3669f-103">При реализации службы выполняется определение числа контрактов, описывающих службу и данные, которые она отправляет и получает.</span><span class="sxs-lookup"><span data-stu-id="3669f-103">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="3669f-104">Данные представлены как контракты данных и контракты на сообщения; как WCF, так и службы рабочего процесса используют определения контрактов данных и контрактов сообщений как часть описаний службы.</span><span class="sxs-lookup"><span data-stu-id="3669f-104">The data is represented as data contracts and message contracts; both WCF and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="3669f-105">Служба сама предоставляет метаданные (в форме WSDL) для описания операций службы.</span><span class="sxs-lookup"><span data-stu-id="3669f-105">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="3669f-106">В WCF контракты службы и операций определяют службу и операции, которые она поддерживает.</span><span class="sxs-lookup"><span data-stu-id="3669f-106">In WCF, service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="3669f-107">Однако в службе Workflow Service эти контракты являются частью самого бизнес-процесса, они представляются в метаданных процессом, называемым выводом контракта.</span><span class="sxs-lookup"><span data-stu-id="3669f-107">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="3669f-108">Вывод контракта</span><span class="sxs-lookup"><span data-stu-id="3669f-108">Contract Inference</span></span>  
 <span data-ttu-id="3669f-109">При размещении службы рабочего процесса с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost> просматривается определение рабочего процесса и формируется контракт на основе набора действий по отправке и получению сообщений, обнаруженных в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="3669f-109">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="3669f-110">В частности, для создания контракта используются следующие действия и свойства:</span><span class="sxs-lookup"><span data-stu-id="3669f-110">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="3669f-111"><xref:System.ServiceModel.Activities.Receive> Действие</span><span class="sxs-lookup"><span data-stu-id="3669f-111"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <span data-ttu-id="3669f-112"><xref:System.ServiceModel.Activities.SendReply> Действие</span><span class="sxs-lookup"><span data-stu-id="3669f-112"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <span data-ttu-id="3669f-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Действие</span><span class="sxs-lookup"><span data-stu-id="3669f-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="3669f-114">Конечным результатом вывода контракта является описание службы, использующее структуры данных, аналогичные структурам данных служб WCF и контрактов операций.</span><span class="sxs-lookup"><span data-stu-id="3669f-114">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="3669f-115">Затем эти сведения используются для предоставления WSDL для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3669f-115">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3669f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3669f-116">See also</span></span>

- [<span data-ttu-id="3669f-117">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="3669f-117">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="3669f-118">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="3669f-118">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
- [<span data-ttu-id="3669f-119">Как создать службу рабочего процесса с помощью действий обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="3669f-119">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [<span data-ttu-id="3669f-120">Как создать службу рабочего процесса, которая использует существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="3669f-120">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
