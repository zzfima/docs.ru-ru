---
title: Перечисление CorDebugJITCompilerFlags
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66a8ba59d221bb3fa2e815a1cbcfa79c474666cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105473"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="5fe4f-102">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="5fe4f-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="5fe4f-103">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="5fe4f-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fe4f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5fe4f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5fe4f-105">Members</span></span>  
  
|<span data-ttu-id="5fe4f-106">Член</span><span class="sxs-lookup"><span data-stu-id="5fe4f-106">Member</span></span>|<span data-ttu-id="5fe4f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5fe4f-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="5fe4f-108">Указывает, что компилятор должен отслеживать данные компиляции и позволяет выполнять оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="5fe4f-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="5fe4f-109">Указывает, что компилятор должен отслеживать данные компиляции, но отключает синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="5fe4f-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="5fe4f-110">Указывает, что компилятор должен отслеживать данные компиляции, отключает синхронизацию и позволяет изменить и продолжить технологий.</span><span class="sxs-lookup"><span data-stu-id="5fe4f-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fe4f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5fe4f-111">Requirements</span></span>  
 <span data-ttu-id="5fe4f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe4f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe4f-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fe4f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fe4f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fe4f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5fe4f-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5fe4f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fe4f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5fe4f-116">See also</span></span>

- [<span data-ttu-id="5fe4f-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="5fe4f-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
