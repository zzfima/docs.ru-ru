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
ms.openlocfilehash: d78f81093e61c40eaec334f957d8583eeb593f5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134816"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="7469f-102">Метод IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="7469f-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="7469f-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="7469f-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7469f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7469f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7469f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7469f-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="7469f-106">окне Размер сегмента, используемого системой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7469f-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="7469f-107">окне Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="7469f-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7469f-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="7469f-108">Remarks</span></span>  
 <span data-ttu-id="7469f-109">Значения, которые `SetGCStartupLimitsEx` наборы, можно указать только перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="7469f-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="7469f-110">Эти значения нельзя изменить позже.</span><span class="sxs-lookup"><span data-stu-id="7469f-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7469f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7469f-111">Requirements</span></span>  
 <span data-ttu-id="7469f-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7469f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7469f-113">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="7469f-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7469f-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7469f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7469f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7469f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7469f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7469f-116">See also</span></span>

- [<span data-ttu-id="7469f-117">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="7469f-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
