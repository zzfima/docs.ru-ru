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
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132699"
---
# <a name="getcachepath-function"></a><span data-ttu-id="01edc-102">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="01edc-102">GetCachePath Function</span></span>
<span data-ttu-id="01edc-103">Возвращает путь к кэшированной сборке с использованием указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="01edc-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01edc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01edc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="01edc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01edc-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="01edc-106">окне Значение [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) , указывающее источник кэшированной сборки.</span><span class="sxs-lookup"><span data-stu-id="01edc-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="01edc-107">заполняет Возвращаемый указатель на путь.</span><span class="sxs-lookup"><span data-stu-id="01edc-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="01edc-108">[вход, выход] Запрошенная максимальная длина `pwzCachePath`и, при возврате, фактической длины `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="01edc-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01edc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="01edc-109">Requirements</span></span>  
 <span data-ttu-id="01edc-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01edc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01edc-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="01edc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="01edc-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01edc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01edc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="01edc-113">See also</span></span>

- [<span data-ttu-id="01edc-114">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="01edc-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="01edc-115">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="01edc-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
