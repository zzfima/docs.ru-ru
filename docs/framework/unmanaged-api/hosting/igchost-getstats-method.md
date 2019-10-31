---
title: Метод IGCHost::GetStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134887"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="6e7e3-102">Метод IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="6e7e3-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="6e7e3-103">Возвращает статистику текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e7e3-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7e3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e7e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e7e3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e7e3-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="6e7e3-106">[вход, выход] Указатель на структуру [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) , содержащую статистику по текущему состоянию системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e7e3-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e7e3-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6e7e3-107">Remarks</span></span>  
 <span data-ttu-id="6e7e3-108">Статистика может использоваться системой интеллектуального распределения, чтобы помочь системе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6e7e3-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="6e7e3-109">Например, система распределения может определить, что после проверки статистики потребуется добавить память или принудительно выполнить сбор.</span><span class="sxs-lookup"><span data-stu-id="6e7e3-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e7e3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6e7e3-110">Requirements</span></span>  
 <span data-ttu-id="6e7e3-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e7e3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e7e3-112">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="6e7e3-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6e7e3-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6e7e3-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e7e3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e7e3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7e3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6e7e3-115">See also</span></span>

- [<span data-ttu-id="6e7e3-116">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="6e7e3-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
