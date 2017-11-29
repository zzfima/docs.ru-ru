---
title: "Кокласс CorRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="1add0-102">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="1add0-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="1add0-103">Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="1add0-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1add0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1add0-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1add0-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1add0-105">Interfaces</span></span>  
  
|<span data-ttu-id="1add0-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="1add0-106">Interface</span></span>|<span data-ttu-id="1add0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1add0-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1add0-108">Icorconfiguration-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1add0-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="1add0-109">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1add0-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="1add0-110">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1add0-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="1add0-111">Предоставляет методы, позволяющие хост для запуска и остановки среда явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и перечисления всех доменов, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="1add0-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="1add0-112">Idebuggerinfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1add0-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="1add0-113">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="1add0-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="1add0-114">Igchost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1add0-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="1add0-115">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="1add0-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="1add0-116">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="1add0-116">"IValidator"</span></span>|<span data-ttu-id="1add0-117">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="1add0-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1add0-118">Требования</span><span class="sxs-lookup"><span data-stu-id="1add0-118">Requirements</span></span>  
 <span data-ttu-id="1add0-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1add0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1add0-120">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="1add0-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1add0-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1add0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1add0-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1add0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1add0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1add0-123">See Also</span></span>  
 [<span data-ttu-id="1add0-124">Размещение компонентных классов</span><span class="sxs-lookup"><span data-stu-id="1add0-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
