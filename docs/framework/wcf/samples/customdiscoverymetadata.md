---
title: Метаданные CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 3e3a173d99f2ba0a2fb33dfd8f91908f03e3e871
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501053"
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="bb7e5-102">Метаданные CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="bb7e5-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="bb7e5-103">В этом образце показано, как вставить пользовательские метаданные XML в метаданные обнаружения для конечной точки, которая предоставляется службой и поддерживает обнаружение.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="bb7e5-104">Затем в образце показано, как клиент может найти службу и извлечь эти пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="bb7e5-105">Этот образец состоит из двух проектов: служба и клиент.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="bb7e5-106">Служба</span><span class="sxs-lookup"><span data-stu-id="bb7e5-106">Service</span></span>  
 <span data-ttu-id="bb7e5-107">В методе `main` образца показано, что объект типа <xref:System.Xml.Linq.XElement> заполняется нужными полями и добавляется в объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="bb7e5-108">Этот объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> добавляется в определенную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="bb7e5-109">Когда выполняется обнаружение этой конечной точки, метаданные обнаружения содержат пользовательские данные, добавленные здесь.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="bb7e5-110">Клиент</span><span class="sxs-lookup"><span data-stu-id="bb7e5-110">Client</span></span>  
 <span data-ttu-id="bb7e5-111">В образце показано, как метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> вызывается в объекте <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="bb7e5-112">Затем в результирующем объекте <xref:System.ServiceModel.Discovery.FindResponse> запрашиваются подходящие и ожидаемые XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="bb7e5-113">Затем эти элементы выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bb7e5-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="bb7e5-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="bb7e5-115">Загрузите решение проекта в среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="bb7e5-116">Сначала запустите приложение службы, созданное в каталоге [основной каталог решения]\service\bin\debug, а затем запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug</span><span class="sxs-lookup"><span data-stu-id="bb7e5-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="bb7e5-117">Заметьте, что служба становится доступной, клиент находит службу и выводит метаданные, опубликованные в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb7e5-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bb7e5-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="bb7e5-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bb7e5-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bb7e5-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="bb7e5-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="bb7e5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="bb7e5-122">See Also</span></span>
