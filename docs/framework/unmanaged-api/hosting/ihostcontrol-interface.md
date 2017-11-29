---
title: "Интерфейс IHostControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e72ad562a73faf5682204c2ae2583b71cb3c05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="e717d-102">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="e717d-102">IHostControl Interface</span></span>
<span data-ttu-id="e717d-103">Предоставляет методы для настройки загрузки сборок, а также для определения интерфейсов размещения, поддерживаемых основным приложением.</span><span class="sxs-lookup"><span data-stu-id="e717d-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e717d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e717d-104">Methods</span></span>  
  
|<span data-ttu-id="e717d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e717d-105">Method</span></span>|<span data-ttu-id="e717d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e717d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e717d-107">Gethostmanager-метод</span><span class="sxs-lookup"><span data-stu-id="e717d-107">GetHostManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="e717d-108">Возвращает указатель на интерфейс для реализации интерфейса с заданным `IID`.</span><span class="sxs-lookup"><span data-stu-id="e717d-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="e717d-109">SetAppDomainManager-метод</span><span class="sxs-lookup"><span data-stu-id="e717d-109">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="e717d-110">Уведомляет узел, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="e717d-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e717d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e717d-111">Requirements</span></span>  
 <span data-ttu-id="e717d-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e717d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e717d-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e717d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e717d-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e717d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e717d-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e717d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e717d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e717d-116">See Also</span></span>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="e717d-117">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e717d-117">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="e717d-118">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e717d-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e717d-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e717d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
