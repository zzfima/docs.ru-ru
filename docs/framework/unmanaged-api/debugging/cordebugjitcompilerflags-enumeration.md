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
ms.openlocfilehash: 39bc1316bb7d8e2aba3390499437aadf263dac07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739849"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="5239c-102">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="5239c-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="5239c-103">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="5239c-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5239c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5239c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5239c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5239c-105">Members</span></span>  
  
|<span data-ttu-id="5239c-106">Член</span><span class="sxs-lookup"><span data-stu-id="5239c-106">Member</span></span>|<span data-ttu-id="5239c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5239c-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="5239c-108">Указывает, что компилятор должен отслеживать данные компиляции и позволяет выполнять оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="5239c-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="5239c-109">Указывает, что компилятор должен отслеживать данные компиляции, но отключает синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="5239c-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="5239c-110">Указывает, что компилятор должен отслеживать данные компиляции, отключает синхронизацию и позволяет изменить и продолжить технологий.</span><span class="sxs-lookup"><span data-stu-id="5239c-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5239c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5239c-111">Requirements</span></span>  
 <span data-ttu-id="5239c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5239c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5239c-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5239c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5239c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5239c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5239c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5239c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5239c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5239c-116">See also</span></span>

- [<span data-ttu-id="5239c-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="5239c-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
