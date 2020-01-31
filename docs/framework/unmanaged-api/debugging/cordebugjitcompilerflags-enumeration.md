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
ms.openlocfilehash: 65d7e830b82cc1780826517fe8cff1da0a7d6188
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793894"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="b00bc-102">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="b00bc-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="b00bc-103">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="b00bc-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b00bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b00bc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b00bc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b00bc-105">Members</span></span>  
  
|<span data-ttu-id="b00bc-106">Член</span><span class="sxs-lookup"><span data-stu-id="b00bc-106">Member</span></span>|<span data-ttu-id="b00bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b00bc-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="b00bc-108">Указывает, что компилятор должен отслеживанить данные компиляции и допускает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="b00bc-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="b00bc-109">Указывает, что компилятор должен отслеживаниь данных компиляции, но отключает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="b00bc-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="b00bc-110">Указывает, что компилятор должен выполнять трассировку данных компиляции, отключать оптимизации и включать технологии "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="b00bc-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b00bc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b00bc-111">Requirements</span></span>  
 <span data-ttu-id="b00bc-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b00bc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b00bc-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b00bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b00bc-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b00bc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b00bc-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b00bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00bc-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b00bc-116">See also</span></span>

- [<span data-ttu-id="b00bc-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b00bc-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
