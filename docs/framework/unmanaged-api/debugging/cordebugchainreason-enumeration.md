---
title: Перечисление CorDebugChainReason
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e46118e97a4b888a16f12cf6705d2b7e67bbf7ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740362"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="8fe70-102">Перечисление CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="8fe70-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="8fe70-103">Указывает причину или причины запуска цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8fe70-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fe70-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="8fe70-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8fe70-105">Members</span></span>  
  
|<span data-ttu-id="8fe70-106">Член</span><span class="sxs-lookup"><span data-stu-id="8fe70-106">Member</span></span>|<span data-ttu-id="8fe70-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8fe70-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="8fe70-108">Цепочки вызовов не инициированы.</span><span class="sxs-lookup"><span data-stu-id="8fe70-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="8fe70-109">Цепочка была инициирована конструктором.</span><span class="sxs-lookup"><span data-stu-id="8fe70-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="8fe70-110">Цепочка была инициирована фильтром исключений.</span><span class="sxs-lookup"><span data-stu-id="8fe70-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="8fe70-111">Цепочка была инициирована кодом, который принудительно обеспечивает безопасность.</span><span class="sxs-lookup"><span data-stu-id="8fe70-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="8fe70-112">Цепочка была инициирована контекстной политикой.</span><span class="sxs-lookup"><span data-stu-id="8fe70-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="8fe70-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8fe70-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="8fe70-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8fe70-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="8fe70-115">Цепочка была инициирована началом выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="8fe70-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="8fe70-116">Цепочка была инициирована входом в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8fe70-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="8fe70-117">Цепочка была инициирована входом в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="8fe70-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="8fe70-118">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8fe70-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="8fe70-119">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8fe70-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="8fe70-120">Цепочка была инициирована оценкой функции.</span><span class="sxs-lookup"><span data-stu-id="8fe70-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fe70-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fe70-121">Remarks</span></span>  
 <span data-ttu-id="8fe70-122">Используйте [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) метод для выяснения причины инициирования цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8fe70-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe70-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8fe70-123">Requirements</span></span>  
 <span data-ttu-id="8fe70-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fe70-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe70-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fe70-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fe70-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fe70-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fe70-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe70-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe70-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8fe70-128">See also</span></span>

- [<span data-ttu-id="8fe70-129">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="8fe70-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
