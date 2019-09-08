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
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796907"
---
# <a name="getcachepath-function"></a><span data-ttu-id="b4f2f-102">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="b4f2f-102">GetCachePath Function</span></span>
<span data-ttu-id="b4f2f-103">Возвращает путь к кэшированной сборке с использованием указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="b4f2f-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4f2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4f2f-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="b4f2f-106">окне Значение [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) , указывающее источник кэшированной сборки.</span><span class="sxs-lookup"><span data-stu-id="b4f2f-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="b4f2f-107">заполняет Возвращаемый указатель на путь.</span><span class="sxs-lookup"><span data-stu-id="b4f2f-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="b4f2f-108">[вход, выход] Запрошенная максимальная длина `pwzCachePath`и при возврате фактической `pwzCachePath`длины.</span><span class="sxs-lookup"><span data-stu-id="b4f2f-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f2f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b4f2f-109">Requirements</span></span>  
 <span data-ttu-id="b4f2f-110">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f2f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f2f-111">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b4f2f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b4f2f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f2f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f2f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b4f2f-113">See also</span></span>

- [<span data-ttu-id="b4f2f-114">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b4f2f-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="b4f2f-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="b4f2f-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
