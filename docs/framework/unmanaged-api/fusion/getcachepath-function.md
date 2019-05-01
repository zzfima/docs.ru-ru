---
title: Функция GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985898"
---
# <a name="getcachepath-function"></a><span data-ttu-id="00137-102">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="00137-102">GetCachePath Function</span></span>
<span data-ttu-id="00137-103">Получает путь к кэшированную сборку, используя указанные флаги.</span><span class="sxs-lookup"><span data-stu-id="00137-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00137-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00137-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="00137-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00137-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="00137-106">[in] [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) значение, указывающее источник кэшированную сборку.</span><span class="sxs-lookup"><span data-stu-id="00137-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="00137-107">[out] Возвращаемый указатель на путь.</span><span class="sxs-lookup"><span data-stu-id="00137-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="00137-108">[in, out] Запрошенный максимальную длину `pwzCachePath`и по возвращении фактическую длину `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="00137-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00137-109">Требования</span><span class="sxs-lookup"><span data-stu-id="00137-109">Requirements</span></span>  
 <span data-ttu-id="00137-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00137-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00137-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="00137-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="00137-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00137-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00137-113">См. также</span><span class="sxs-lookup"><span data-stu-id="00137-113">See also</span></span>

- [<span data-ttu-id="00137-114">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="00137-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="00137-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="00137-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
