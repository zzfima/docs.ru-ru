---
title: Метод ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7b9602f490900fd5c923abf195b3b0707959832
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554042"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="01120-102">Метод ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="01120-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="01120-103">Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса узла, чтобы изменить ограничения виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="01120-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01120-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01120-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01120-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01120-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="01120-106">[in] Указатель на [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) объект, который позволяет сборщику мусора запросить узла, чтобы изменить ограничения виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="01120-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01120-107">Требования</span><span class="sxs-lookup"><span data-stu-id="01120-107">Requirements</span></span>  
 <span data-ttu-id="01120-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01120-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01120-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01120-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01120-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01120-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01120-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01120-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01120-112">См. также</span><span class="sxs-lookup"><span data-stu-id="01120-112">See also</span></span>
- [<span data-ttu-id="01120-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="01120-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
