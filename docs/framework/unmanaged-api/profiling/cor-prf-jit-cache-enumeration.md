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
ms.openlocfilehash: 57d6ba77081536eb2bce0bf62d43ac080b2f5554
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447344"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="26c13-102">Перечисление COR_PRF_JIT_CACHE</span><span class="sxs-lookup"><span data-stu-id="26c13-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="26c13-103">Указывает результат кэшированной функции поиска.</span><span class="sxs-lookup"><span data-stu-id="26c13-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26c13-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span><span class="sxs-lookup"><span data-stu-id="26c13-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c13-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26c13-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="26c13-106">Члены</span><span class="sxs-lookup"><span data-stu-id="26c13-106">Members</span></span>  
  
|<span data-ttu-id="26c13-107">Член</span><span class="sxs-lookup"><span data-stu-id="26c13-107">Member</span></span>|<span data-ttu-id="26c13-108">Описание</span><span class="sxs-lookup"><span data-stu-id="26c13-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="26c13-109">The search found the function.</span><span class="sxs-lookup"><span data-stu-id="26c13-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="26c13-110">The search did not find the function.</span><span class="sxs-lookup"><span data-stu-id="26c13-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26c13-111">Требования</span><span class="sxs-lookup"><span data-stu-id="26c13-111">Requirements</span></span>  
 <span data-ttu-id="26c13-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26c13-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c13-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26c13-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26c13-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26c13-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26c13-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c13-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c13-116">См. также</span><span class="sxs-lookup"><span data-stu-id="26c13-116">See also</span></span>

- [<span data-ttu-id="26c13-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="26c13-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
