---
title: Кокласс CorRuntimeHost
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
ms.openlocfilehash: 7c81a39acee31986421c810e2814a4f7e6c4d970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597532"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="26669-102">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="26669-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="26669-103">Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="26669-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26669-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26669-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="26669-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="26669-105">Interfaces</span></span>  
  
|<span data-ttu-id="26669-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="26669-106">Interface</span></span>|<span data-ttu-id="26669-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="26669-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="26669-108">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="26669-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="26669-109">Предоставляет методы для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="26669-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="26669-110">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="26669-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="26669-111">Предоставляет методы, позволяющие узел для запуска и остановки среда CLR явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и для перечисления всех доменов, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="26669-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="26669-112">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="26669-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="26669-113">Предоставляет методы для получения сведений о состоянии служб отладки.</span><span class="sxs-lookup"><span data-stu-id="26669-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="26669-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="26669-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="26669-115">Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="26669-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="26669-116">«IValidator»</span><span class="sxs-lookup"><span data-stu-id="26669-116">"IValidator"</span></span>|<span data-ttu-id="26669-117">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="26669-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26669-118">Требования</span><span class="sxs-lookup"><span data-stu-id="26669-118">Requirements</span></span>  
 <span data-ttu-id="26669-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26669-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26669-120">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="26669-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="26669-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26669-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26669-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26669-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26669-123">См. также</span><span class="sxs-lookup"><span data-stu-id="26669-123">See also</span></span>
- [<span data-ttu-id="26669-124">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="26669-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
