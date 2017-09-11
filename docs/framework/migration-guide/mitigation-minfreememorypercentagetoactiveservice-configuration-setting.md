---
title: "Устранение рисков: параметр конфигурации minFreeMemoryPercentageToActiveService"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a><span data-ttu-id="ae190-102">Устранение рисков: параметр конфигурации minFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="ae190-102">Mitigation: minFreeMemoryPercentageToActiveService Configuration Setting</span></span>
<span data-ttu-id="ae190-103">В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] возникает исключение, если объем доступной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span><span class="sxs-lookup"><span data-stu-id="ae190-103">In the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], an exception is thrown if the available memory on the web server is less than the percentage specified by the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) configuration setting.</span></span> <span data-ttu-id="ae190-104">В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ae190-104">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], this setting was ignored.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ae190-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="ae190-105">Impact</span></span>  
 <span data-ttu-id="ae190-106">В большинстве случаев соблюдение параметра [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) желательно: благодаря этому повышается стабильность системы за счет предотвращения исключений <xref:System.OutOfMemoryException>, которые могут возникнуть при запуске службы Windows Communication Foundation (WCF) в системе с ограниченной памятью.</span><span class="sxs-lookup"><span data-stu-id="ae190-106">In most cases, the impact of observing the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting is desirable: It improves system stability by preventing the <xref:System.OutOfMemoryException> exceptions that can occur when a Windows Communication Foundation (WCF) service is started on a system that has constrained memory.</span></span>  
  
 <span data-ttu-id="ae190-107">Однако в некоторых случаях служба, которая ранее успешно запускалась, может перестать запускаться.</span><span class="sxs-lookup"><span data-stu-id="ae190-107">However, in some cases, a service that previously started successfully may be unable to start.</span></span> <span data-ttu-id="ae190-108">В этом случае появляется подробное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ae190-108">In that case, a detailed error message appears:</span></span>  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a><span data-ttu-id="ae190-109">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="ae190-109">Mitigation</span></span>  
 <span data-ttu-id="ae190-110">Чтобы вернуться к прежнему поведению, где параметр [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) игнорировался, измените файл web.config следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ae190-110">To revert to the previous behavior where the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting was ignored, modify the web.config file as follows:</span></span>  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae190-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ae190-111">See Also</span></span>  
 [<span data-ttu-id="ae190-112">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ae190-112">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

