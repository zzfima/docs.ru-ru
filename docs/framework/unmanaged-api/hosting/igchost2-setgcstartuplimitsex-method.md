---
title: Метод IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763221"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="6e314-102">Метод IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="6e314-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="6e314-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="6e314-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e314-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e314-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e314-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e314-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="6e314-106">[in] Размер сегмента, используемой системой сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="6e314-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="6e314-107">[in] Максимальный размер поколения 0.</span><span class="sxs-lookup"><span data-stu-id="6e314-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e314-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e314-108">Remarks</span></span>  
 <span data-ttu-id="6e314-109">Значения, `SetGCStartupLimitsEx` множества могут быть заданы только в том случае, перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="6e314-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="6e314-110">Эти значения нельзя изменить позже.</span><span class="sxs-lookup"><span data-stu-id="6e314-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e314-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6e314-111">Requirements</span></span>  
 <span data-ttu-id="6e314-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e314-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e314-113">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="6e314-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6e314-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e314-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e314-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e314-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e314-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6e314-116">See also</span></span>

- [<span data-ttu-id="6e314-117">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="6e314-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
