---
title: Метод IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 1ae50fb3ff15097f9a6ca5839f3832bcfc58d3f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134854"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="8d349-102">Метод IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="8d349-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="8d349-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="8d349-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8d349-104">Начиная с .NET Framework 4,5 можно задать размер сегмента и максимальный размер поколения 0 для значений, превышающих `DWORD`, с помощью метода [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8d349-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d349-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d349-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d349-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d349-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="8d349-107">окне Размер сегмента, используемого системой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8d349-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8d349-108">окне Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="8d349-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d349-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="8d349-109">Remarks</span></span>  
 <span data-ttu-id="8d349-110">Метод `SetGCStartupLimits` может быть вызван только один раз.</span><span class="sxs-lookup"><span data-stu-id="8d349-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="8d349-111">Эти значения нельзя изменить позже.</span><span class="sxs-lookup"><span data-stu-id="8d349-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d349-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8d349-112">Requirements</span></span>  
 <span data-ttu-id="8d349-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d349-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d349-114">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="8d349-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8d349-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d349-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d349-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d349-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d349-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8d349-117">See also</span></span>

- [<span data-ttu-id="8d349-118">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="8d349-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
