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
ms.openlocfilehash: 48c2a394126aca3a10b38ab2ba2df945f53e45d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438276"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="af96e-102">Метод ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="af96e-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="af96e-103">Задает интерфейс обратного вызова, используемый сборщиком мусора запрашивать основное приложение для изменения ограничений на объем виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="af96e-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af96e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af96e-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af96e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af96e-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="af96e-106">[in] Указатель на [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) объектом, который позволяет сборщику мусора запрашивать основное приложение для изменения ограничений на объем виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="af96e-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af96e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="af96e-107">Requirements</span></span>  
 <span data-ttu-id="af96e-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af96e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af96e-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af96e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af96e-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af96e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af96e-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af96e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af96e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="af96e-112">See Also</span></span>  
 [<span data-ttu-id="af96e-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="af96e-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
