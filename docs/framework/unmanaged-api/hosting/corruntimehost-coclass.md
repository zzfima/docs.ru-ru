---
title: Компонентный класс CorRuntimeHost
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218567"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="ea795-102">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ea795-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="ea795-103">Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="ea795-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea795-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea795-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="ea795-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="ea795-105">Interfaces</span></span>  
  
|<span data-ttu-id="ea795-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="ea795-106">Interface</span></span>|<span data-ttu-id="ea795-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ea795-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ea795-108">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea795-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="ea795-109">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ea795-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="ea795-110">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ea795-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="ea795-111">Предоставляет методы, позволяющие узел для запуска и остановки среда CLR явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и для перечисления всех доменов, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="ea795-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="ea795-112">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="ea795-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="ea795-113">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="ea795-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="ea795-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="ea795-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="ea795-115">Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="ea795-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="ea795-116">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="ea795-116">"IValidator"</span></span>|<span data-ttu-id="ea795-117">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="ea795-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea795-118">Требования</span><span class="sxs-lookup"><span data-stu-id="ea795-118">Requirements</span></span>  
 <span data-ttu-id="ea795-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea795-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea795-120">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="ea795-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ea795-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea795-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ea795-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ea795-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea795-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ea795-123">See also</span></span>

- [<span data-ttu-id="ea795-124">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="ea795-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
