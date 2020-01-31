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
ms.openlocfilehash: 39b90ba35510a5eda7b34e0a80b0e889e5804ca7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778229"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="63b14-102">Перечисление CorDebugJITCompilerFlagsDeprecated</span><span class="sxs-lookup"><span data-stu-id="63b14-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="63b14-103">Это перечисление устарело.</span><span class="sxs-lookup"><span data-stu-id="63b14-103">This enumeration is obsolete.</span></span> <span data-ttu-id="63b14-104">Вместо этого используйте элемент `CORDEBUG_JIT_DEFAULT` перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="63b14-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b14-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63b14-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="63b14-106">Участники</span><span class="sxs-lookup"><span data-stu-id="63b14-106">Members</span></span>  
  
|<span data-ttu-id="63b14-107">Член</span><span class="sxs-lookup"><span data-stu-id="63b14-107">Member</span></span>|<span data-ttu-id="63b14-108">Описание</span><span class="sxs-lookup"><span data-stu-id="63b14-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="63b14-109">Взамен рекомендуется использовать `CORDEBUG_JIT_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="63b14-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63b14-110">Требования</span><span class="sxs-lookup"><span data-stu-id="63b14-110">Requirements</span></span>  
 <span data-ttu-id="63b14-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63b14-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63b14-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63b14-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63b14-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63b14-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63b14-114">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="63b14-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b14-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="63b14-115">See also</span></span>

- [<span data-ttu-id="63b14-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="63b14-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
