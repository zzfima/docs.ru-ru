---
title: Перечисление CorDebugJITCompilerFlagsDeprecated
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f15a4557be0dc633fb9ecda5916896e340f00da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136894"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="0bbde-102">Перечисление CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="0bbde-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="0bbde-103">Это перечисление устарело.</span><span class="sxs-lookup"><span data-stu-id="0bbde-103">This enumeration is obsolete.</span></span> <span data-ttu-id="0bbde-104">Используйте `CORDEBUG_JIT_DEFAULT` членом [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисления вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0bbde-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbde-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bbde-105">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="0bbde-106">Участники</span><span class="sxs-lookup"><span data-stu-id="0bbde-106">Members</span></span>  
  
|<span data-ttu-id="0bbde-107">Член</span><span class="sxs-lookup"><span data-stu-id="0bbde-107">Member</span></span>|<span data-ttu-id="0bbde-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0bbde-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="0bbde-109">Взамен рекомендуется использовать `CORDEBUG_JIT_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="0bbde-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bbde-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0bbde-110">Requirements</span></span>  
 <span data-ttu-id="0bbde-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bbde-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbde-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bbde-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bbde-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bbde-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bbde-114">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0bbde-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbde-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0bbde-115">See also</span></span>

- [<span data-ttu-id="0bbde-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0bbde-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
