---
title: Размещение в управляемом приложении
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e81a8eb27725edeccf3e5c7489109ba47b70dec
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="47215-102">Размещение в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="47215-102">Hosting in a Managed Application</span></span>
<span data-ttu-id="47215-103">Службы[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно разместить в любом приложении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47215-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services can be hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="47215-104">Резидентное размещение служб - самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="47215-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="47215-105">Однако это и наименее надежный вариант размещения, так как управляемые приложения не предоставляют дополнительные функции размещения и управления, как другие варианты размещения в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], такие как службы IIS и службы Windows.</span><span class="sxs-lookup"><span data-stu-id="47215-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="47215-106">Для создания резидентной службы необходимо создать и открыть экземпляр узла службы <xref:System.ServiceModel.ServiceHost>, который запускает службу, ожидающую сообщений.</span><span class="sxs-lookup"><span data-stu-id="47215-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="47215-107"> [Как: размещение службы WCF в управляемом приложении](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="47215-107"> [How to: Host a WCF Service in a Managed Application](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="47215-108">Полный пример определения контракта, реализации контракта и размещения службы внутри управляемого приложения в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md) и [резидентной](../../../../docs/framework/wcf/samples/self-host.md).</span><span class="sxs-lookup"><span data-stu-id="47215-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) and the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md).</span></span>  
  
 <span data-ttu-id="47215-109">В следующих разделах описаны стандартные сценарии, использующие этот вариант размещения.</span><span class="sxs-lookup"><span data-stu-id="47215-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="47215-110">Консольные приложения</span><span class="sxs-lookup"><span data-stu-id="47215-110">Console Applications</span></span>  
 <span data-ttu-id="47215-111">Одним из стандартных сценариев, обеспечиваемых резидентным размещением, является выполнение служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в консольных приложениях.</span><span class="sxs-lookup"><span data-stu-id="47215-111">Common scenarios that self-hosting enables are [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running inside console applications.</span></span> <span data-ttu-id="47215-112">Размещение службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] внутри консольного приложения, как правило, целесообразно на этапе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="47215-112">Hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="47215-113">В этом случае приложение легко отлаживать, удобно получать данные трассировки, чтобы узнать, что происходит внутри приложения, и удобно копировать приложение в другие расположения.</span><span class="sxs-lookup"><span data-stu-id="47215-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="47215-114">Функционально насыщенные клиентские приложения</span><span class="sxs-lookup"><span data-stu-id="47215-114">Rich Client Applications</span></span>  
 <span data-ttu-id="47215-115">Других стандартных сценариев, обеспечиваемых резидентным размещением насыщенных клиентских приложений, например те, на основе Windows Presentation Foundation (WPF) или Windows Forms (WinForms).</span><span class="sxs-lookup"><span data-stu-id="47215-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on Windows Presentation Foundation (WPF) or Windows Forms (WinForms).</span></span> <span data-ttu-id="47215-116">Кроме того, этот вариант размещения упрощает взаимодействие функционально насыщенных клиентских приложений, таких как приложения [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и WinForms, с внешними системами.</span><span class="sxs-lookup"><span data-stu-id="47215-116">This hosting option also makes it easy for rich client applications, such as [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="47215-117">Например, одноранговый клиент для совместной работы может использовать в качестве пользовательского интерфейса [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и размещать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , позволяющую другим клиентам подключаться к нему и обмениваться с ним информацией.</span><span class="sxs-lookup"><span data-stu-id="47215-117">For example, a peer-to-peer collaboration client that uses [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] for its user interface and also hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47215-118">См. также</span><span class="sxs-lookup"><span data-stu-id="47215-118">See Also</span></span>  
 [<span data-ttu-id="47215-119">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="47215-119">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="47215-120">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="47215-120">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
