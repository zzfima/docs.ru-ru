---
title: Перечисление COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974114"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="0fd2a-102">Перечисление COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0fd2a-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="0fd2a-103">Содержит значения, указывающие поведение API [ICorProfilerInfo10:: рекуестрежитвисинлинерс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0fd2a-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fd2a-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0fd2a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0fd2a-105">Members</span></span>  
  
|<span data-ttu-id="0fd2a-106">Член</span><span class="sxs-lookup"><span data-stu-id="0fd2a-106">Member</span></span>|<span data-ttu-id="0fd2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="0fd2a-108">Методы Режиттед будут заблокированы из встроенных в другие методы.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="0fd2a-109">Получение `GetFunctionParameters` обратных вызовов для всех методов, которые подставляемые методы режиттед.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="0fd2a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0fd2a-110">Requirements</span></span>  
 <span data-ttu-id="0fd2a-111">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="0fd2a-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="0fd2a-112">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="0fd2a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fd2a-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="0fd2a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fd2a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fd2a-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0fd2a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd2a-115">See also</span></span>

- [<span data-ttu-id="0fd2a-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="0fd2a-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
