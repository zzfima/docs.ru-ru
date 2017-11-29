---
title: "Использование ServiceThrottlingBehavior для управления производительностью службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01f3815c095012d10fdfd56893125135c35f8009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a><span data-ttu-id="45280-102">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="45280-102">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>
<span data-ttu-id="45280-103">Класс <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> представляет свойства, которые можно использовать для ограничения количества экземпляров или сеансов, создаваемых на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="45280-103">The <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class exposes properties that you can use to limit how many instances or sessions are created at the application level.</span></span> <span data-ttu-id="45280-104">С помощью этого поведения можно точно настроить производительность приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45280-104">Using this behavior, you can fine-tune the performance of your [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a><span data-ttu-id="45280-105">Управление экземплярами службы и одновременными вызовами</span><span class="sxs-lookup"><span data-stu-id="45280-105">Controlling Service Instances and Concurrent Calls</span></span>  
 <span data-ttu-id="45280-106">С помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> задайте максимальное количество одновременно обрабатываемых сообщений в классе <xref:System.ServiceModel.ServiceHost>, а с помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> задайте максимальное количество объектов <xref:System.ServiceModel.InstanceContext> в службе.</span><span class="sxs-lookup"><span data-stu-id="45280-106">Use the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> property to specify the maximum number of messages actively processing across a <xref:System.ServiceModel.ServiceHost> class, and the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> property to specify the maximum number of <xref:System.ServiceModel.InstanceContext> objects in the service.</span></span>  
  
 <span data-ttu-id="45280-107">Поскольку определение параметров для этих свойств обычно производится после реальные знания и опыт эксплуатации приложения для загрузки параметров для <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> свойства обычно задается в файле конфигурации приложения с помощью [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="45280-107">Because determining the settings for these properties usually takes place after real-world experience running the application against loads, the settings for the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> properties is typically specified in an application configuration file using the [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) element.</span></span>  
  
 <span data-ttu-id="45280-108">В следующем примере кода показано использование класса <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> из файла конфигурации приложения, который, в качестве упрощенного примера, задает для свойств <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> значение 1.</span><span class="sxs-lookup"><span data-stu-id="45280-108">The following code example shows the use of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class from an application configuration file that sets the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> properties to 1 as a trivial example.</span></span> <span data-ttu-id="45280-109">Фактические условия определяют оптимальные параметры для каждого конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="45280-109">Real-world experience determines the optimal settings for any particular application.</span></span>  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 <span data-ttu-id="45280-110">Точное поведение времени выполнения зависит от значений свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> и <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>, которые управляют количеством сообщений, которые могут обрабатываться в операции одновременно, и временем существования службы <xref:System.ServiceModel.InstanceContext> относительно сеансов входящих каналов, соответственно.</span><span class="sxs-lookup"><span data-stu-id="45280-110">The exact run-time behavior depends upon the values of the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> and <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> properties, which control how many messages can execute inside an operation at once and the lifetimes of the service <xref:System.ServiceModel.InstanceContext> relative to incoming channel sessions, respectively.</span></span>  
  
 <span data-ttu-id="45280-111">Дополнительные сведения см. в разделах <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span><span class="sxs-lookup"><span data-stu-id="45280-111">For details, see <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45280-112">См. также</span><span class="sxs-lookup"><span data-stu-id="45280-112">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
