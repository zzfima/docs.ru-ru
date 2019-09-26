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
ms.openlocfilehash: fce803544b393ac2c441779183cbf49d4c39bdae
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273980"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="71413-102">Перечисление CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="71413-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="71413-103">Указывает причину или причины запуска цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="71413-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71413-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71413-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="71413-105">Участники</span><span class="sxs-lookup"><span data-stu-id="71413-105">Members</span></span>  
  
|<span data-ttu-id="71413-106">Член</span><span class="sxs-lookup"><span data-stu-id="71413-106">Member</span></span>|<span data-ttu-id="71413-107">Описание</span><span class="sxs-lookup"><span data-stu-id="71413-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="71413-108">Цепочки вызовов не инициированы.</span><span class="sxs-lookup"><span data-stu-id="71413-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="71413-109">Цепочка была инициирована конструктором.</span><span class="sxs-lookup"><span data-stu-id="71413-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="71413-110">Цепочка была инициирована фильтром исключений.</span><span class="sxs-lookup"><span data-stu-id="71413-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="71413-111">Цепочка была инициирована кодом, который принудительно обеспечивает безопасность.</span><span class="sxs-lookup"><span data-stu-id="71413-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="71413-112">Цепочка была инициирована контекстной политикой.</span><span class="sxs-lookup"><span data-stu-id="71413-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="71413-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="71413-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="71413-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="71413-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="71413-115">Цепочка была инициирована началом выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="71413-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="71413-116">Цепочка была инициирована входом в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="71413-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="71413-117">Цепочка была инициирована входом в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="71413-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="71413-118">Не используется.</span><span class="sxs-lookup"><span data-stu-id="71413-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="71413-119">Не используется.</span><span class="sxs-lookup"><span data-stu-id="71413-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="71413-120">Цепочка была инициирована оценкой функции.</span><span class="sxs-lookup"><span data-stu-id="71413-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71413-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="71413-121">Remarks</span></span>  
 <span data-ttu-id="71413-122">Используйте метод [ICorDebugChain::-Reason](icordebugchain-getreason-method.md) , чтобы определить причины инициации цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="71413-122">Use the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71413-123">Требования</span><span class="sxs-lookup"><span data-stu-id="71413-123">Requirements</span></span>  
 <span data-ttu-id="71413-124">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71413-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71413-125">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="71413-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71413-126">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="71413-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71413-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71413-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71413-128">См. также</span><span class="sxs-lookup"><span data-stu-id="71413-128">See also</span></span>

- [<span data-ttu-id="71413-129">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="71413-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
