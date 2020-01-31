---
title: Перечисление COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867130"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="4e39e-102">Перечисление COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="4e39e-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="4e39e-103">Содержит постоянные значения, которые указывают специальные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="4e39e-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e39e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e39e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="4e39e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4e39e-105">Members</span></span>  
  
|<span data-ttu-id="4e39e-106">Член</span><span class="sxs-lookup"><span data-stu-id="4e39e-106">Member</span></span>|<span data-ttu-id="4e39e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4e39e-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="4e39e-108">Идентификатор по умолчанию, используемый [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) для модуля, который еще не присоединен к сборке.</span><span class="sxs-lookup"><span data-stu-id="4e39e-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="4e39e-109">Идентификатор класса по умолчанию для глобальных констант, которые не принадлежат классу.</span><span class="sxs-lookup"><span data-stu-id="4e39e-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="4e39e-110">Идентификатор модуля по умолчанию для глобальных объектов, которые не принадлежат модулю.</span><span class="sxs-lookup"><span data-stu-id="4e39e-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e39e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4e39e-111">Requirements</span></span>  
 <span data-ttu-id="4e39e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e39e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e39e-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e39e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e39e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e39e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e39e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e39e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e39e-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e39e-116">See also</span></span>

- [<span data-ttu-id="4e39e-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="4e39e-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
