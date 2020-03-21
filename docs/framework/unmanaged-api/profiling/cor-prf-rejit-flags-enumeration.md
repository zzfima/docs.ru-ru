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
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177100"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="a295d-102">Перечисление COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a295d-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="a295d-103">Содержит значения, указывающие на то, как должен вести себя [API ICorProfilerInfo10::RequestReJITInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API.</span><span class="sxs-lookup"><span data-stu-id="a295d-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a295d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a295d-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a295d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="a295d-105">Members</span></span>  
  
|<span data-ttu-id="a295d-106">Участник</span><span class="sxs-lookup"><span data-stu-id="a295d-106">Member</span></span>|<span data-ttu-id="a295d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a295d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="a295d-108">Методы ReJITted будут заблокированы от встроенного в другие методы.</span><span class="sxs-lookup"><span data-stu-id="a295d-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="a295d-109">Получайте `GetFunctionParameters` обратные вызовы для любых методов, которые встраиваем в строку запрошенные методы, которые должны быть reJITted.</span><span class="sxs-lookup"><span data-stu-id="a295d-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="a295d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a295d-110">Requirements</span></span>  
 <span data-ttu-id="a295d-111">**Платформы:** Смотрите [операционные системы, поддерживаемые .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="a295d-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="a295d-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a295d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a295d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a295d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a295d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a295d-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a295d-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a295d-115">See also</span></span>

- [<span data-ttu-id="a295d-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="a295d-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
