---
title: "Перечисление CorDebugJITCompilerFlagsDeprecated"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4cb7836ec572a5c9df4e6a52fce1cefd02d647f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="fed3a-102">Перечисление CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="fed3a-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="fed3a-103">Это перечисление устарело.</span><span class="sxs-lookup"><span data-stu-id="fed3a-103">This enumeration is obsolete.</span></span> <span data-ttu-id="fed3a-104">Используйте `CORDEBUG_JIT_DEFAULT` членом [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисления вместо него.</span><span class="sxs-lookup"><span data-stu-id="fed3a-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed3a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed3a-105">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="fed3a-106">Участники</span><span class="sxs-lookup"><span data-stu-id="fed3a-106">Members</span></span>  
  
|<span data-ttu-id="fed3a-107">Член</span><span class="sxs-lookup"><span data-stu-id="fed3a-107">Member</span></span>|<span data-ttu-id="fed3a-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="fed3a-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="fed3a-109">Взамен рекомендуется использовать `CORDEBUG_JIT_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="fed3a-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fed3a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fed3a-110">Requirements</span></span>  
 <span data-ttu-id="fed3a-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fed3a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed3a-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed3a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed3a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed3a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed3a-114">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fed3a-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed3a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fed3a-115">See Also</span></span>  
 [<span data-ttu-id="fed3a-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="fed3a-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
