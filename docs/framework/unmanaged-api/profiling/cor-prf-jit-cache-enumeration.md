---
title: Перечисление COR_PRF_JIT_CACHE
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144798"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="db00f-102">Перечисление COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="db00f-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="db00f-103">Указывает результат кэшированной функции поиска.</span><span class="sxs-lookup"><span data-stu-id="db00f-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="db00f-104">имеет нулевое значение, поэтому `COR_PRF_JIT_CACHE` нельзя использовать в качестве логического суррогат.</span><span class="sxs-lookup"><span data-stu-id="db00f-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db00f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db00f-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="db00f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="db00f-106">Members</span></span>  
  
|<span data-ttu-id="db00f-107">Член</span><span class="sxs-lookup"><span data-stu-id="db00f-107">Member</span></span>|<span data-ttu-id="db00f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="db00f-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="db00f-109">Найденное функции.</span><span class="sxs-lookup"><span data-stu-id="db00f-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="db00f-110">Поиск не удалось найти функцию.</span><span class="sxs-lookup"><span data-stu-id="db00f-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db00f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="db00f-111">Requirements</span></span>  
 <span data-ttu-id="db00f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db00f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db00f-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db00f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db00f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db00f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="db00f-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="db00f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db00f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="db00f-116">See also</span></span>

- [<span data-ttu-id="db00f-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="db00f-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
