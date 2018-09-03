---
title: Метаданные CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 181910db3f1dd6da892f6ae2ddcbf7bd5859ff17
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465581"
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="e6ac6-102">Метаданные CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="e6ac6-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="e6ac6-103">В этом образце показано, как вставить пользовательские метаданные XML в метаданные обнаружения для конечной точки, которая предоставляется службой и поддерживает обнаружение.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="e6ac6-104">Затем в образце показано, как клиент может найти службу и извлечь эти пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="e6ac6-105">Этот образец состоит из двух проектов: служба и клиент.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="e6ac6-106">Служба</span><span class="sxs-lookup"><span data-stu-id="e6ac6-106">Service</span></span>  
 <span data-ttu-id="e6ac6-107">В методе `main` образца показано, что объект типа <xref:System.Xml.Linq.XElement> заполняется нужными полями и добавляется в объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="e6ac6-108">Этот объект <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> добавляется в определенную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="e6ac6-109">Когда выполняется обнаружение этой конечной точки, метаданные обнаружения содержат пользовательские данные, добавленные здесь.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="e6ac6-110">Клиент</span><span class="sxs-lookup"><span data-stu-id="e6ac6-110">Client</span></span>  
 <span data-ttu-id="e6ac6-111">В образце показано, как метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> вызывается в объекте <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="e6ac6-112">Затем в результирующем объекте <xref:System.ServiceModel.Discovery.FindResponse> запрашиваются подходящие и ожидаемые XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="e6ac6-113">Затем эти элементы выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e6ac6-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="e6ac6-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="e6ac6-115">Загрузите решение проекта в среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="e6ac6-116">Сначала запустите приложение службы, созданное в каталоге [основной каталог решения]\service\bin\debug, а затем запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug</span><span class="sxs-lookup"><span data-stu-id="e6ac6-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="e6ac6-117">Заметьте, что служба становится доступной, клиент находит службу и выводит метаданные, опубликованные в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6ac6-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6ac6-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e6ac6-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e6ac6-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6ac6-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e6ac6-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="e6ac6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e6ac6-122">See Also</span></span>
