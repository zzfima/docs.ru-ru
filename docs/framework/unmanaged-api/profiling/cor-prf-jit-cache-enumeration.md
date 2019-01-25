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
ms.openlocfilehash: 6aaa334c83aff18886c0c2db4462d6baaa4cd70f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687418"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="06962-102">Перечисление COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="06962-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="06962-103">Указывает результат кэшированной функции поиска.</span><span class="sxs-lookup"><span data-stu-id="06962-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06962-104">`COR_PRF_CACHED_FUNCTION_FOUND` имеет нулевое значение, поэтому `COR_PRF_JIT_CACHE` нельзя использовать в качестве логического суррогат.</span><span class="sxs-lookup"><span data-stu-id="06962-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06962-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06962-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="06962-106">Участники</span><span class="sxs-lookup"><span data-stu-id="06962-106">Members</span></span>  
  
|<span data-ttu-id="06962-107">Член</span><span class="sxs-lookup"><span data-stu-id="06962-107">Member</span></span>|<span data-ttu-id="06962-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="06962-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="06962-109">Найденное функции.</span><span class="sxs-lookup"><span data-stu-id="06962-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="06962-110">Поиск не удалось найти функцию.</span><span class="sxs-lookup"><span data-stu-id="06962-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06962-111">Требования</span><span class="sxs-lookup"><span data-stu-id="06962-111">Requirements</span></span>  
 <span data-ttu-id="06962-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06962-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06962-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06962-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06962-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06962-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06962-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06962-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06962-116">См. также</span><span class="sxs-lookup"><span data-stu-id="06962-116">See also</span></span>
- [<span data-ttu-id="06962-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="06962-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
