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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199496"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="b68c5-102">Перечисление COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="b68c5-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="b68c5-103">Содержит постоянные значения, которые указывают специальные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="b68c5-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b68c5-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="b68c5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b68c5-105">Members</span></span>  
  
|<span data-ttu-id="b68c5-106">Член</span><span class="sxs-lookup"><span data-stu-id="b68c5-106">Member</span></span>|<span data-ttu-id="b68c5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b68c5-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="b68c5-108">Идентификатор по умолчанию, используемый [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) для модуля, который еще не присоединена к сборке.</span><span class="sxs-lookup"><span data-stu-id="b68c5-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="b68c5-109">Идентификатор класса по умолчанию для глобальных констант, которые не принадлежат к классу.</span><span class="sxs-lookup"><span data-stu-id="b68c5-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="b68c5-110">Идентификатор модуля по умолчанию для глобальных объектов, не принадлежащие к модулю.</span><span class="sxs-lookup"><span data-stu-id="b68c5-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b68c5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b68c5-111">Requirements</span></span>  
 <span data-ttu-id="b68c5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b68c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b68c5-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b68c5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b68c5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b68c5-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b68c5-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b68c5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b68c5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b68c5-116">See also</span></span>

- [<span data-ttu-id="b68c5-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="b68c5-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
