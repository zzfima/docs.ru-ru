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
ms.openlocfilehash: 3b4f85072b9dcf87d696b979fa6cbf4e59393f82
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453043"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="0f2ee-102">Перечисление COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0f2ee-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="0f2ee-103">Содержит значения, указывающие поведение API [ICorProfilerInfo10:: рекуестрежитвисинлинерс](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0f2ee-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f2ee-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0f2ee-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0f2ee-105">Members</span></span>  
  
|<span data-ttu-id="0f2ee-106">Участник</span><span class="sxs-lookup"><span data-stu-id="0f2ee-106">Member</span></span>|<span data-ttu-id="0f2ee-107">Description</span><span class="sxs-lookup"><span data-stu-id="0f2ee-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="0f2ee-108">Методы Режиттед будут заблокированы из встроенных в другие методы.</span><span class="sxs-lookup"><span data-stu-id="0f2ee-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="0f2ee-109">Получение обратных вызовов `GetFunctionParameters` для любых методов, которые подставляемые методы Режиттед.</span><span class="sxs-lookup"><span data-stu-id="0f2ee-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="0f2ee-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0f2ee-110">Requirements</span></span>  
 <span data-ttu-id="0f2ee-111">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0f2ee-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="0f2ee-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f2ee-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f2ee-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f2ee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f2ee-114">**.NET Framework версии:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2ee-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0f2ee-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f2ee-115">See also</span></span>

- [<span data-ttu-id="0f2ee-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="0f2ee-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
