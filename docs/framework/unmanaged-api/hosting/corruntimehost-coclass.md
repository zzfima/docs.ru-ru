---
title: "Кокласс CorRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23bee1a79dfb54a696495fdb61a7ba9ba4b4c143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="8b3c3-102">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8b3c3-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="8b3c3-103">Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8b3c3-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b3c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b3c3-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="8b3c3-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="8b3c3-105">Interfaces</span></span>  
  
|<span data-ttu-id="8b3c3-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="8b3c3-106">Interface</span></span>|<span data-ttu-id="8b3c3-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8b3c3-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="8b3c3-108">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b3c3-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="8b3c3-109">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b3c3-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="8b3c3-110">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8b3c3-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="8b3c3-111">Предоставляет методы, позволяющие хост для запуска и остановки среда явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и перечисления всех доменов, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="8b3c3-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="8b3c3-112">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="8b3c3-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="8b3c3-113">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="8b3c3-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="8b3c3-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="8b3c3-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="8b3c3-115">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="8b3c3-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="8b3c3-116">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="8b3c3-116">"IValidator"</span></span>|<span data-ttu-id="8b3c3-117">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="8b3c3-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b3c3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8b3c3-118">Requirements</span></span>  
 <span data-ttu-id="8b3c3-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b3c3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b3c3-120">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8b3c3-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8b3c3-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b3c3-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b3c3-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b3c3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3c3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8b3c3-123">See Also</span></span>  
 [<span data-ttu-id="8b3c3-124">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="8b3c3-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
