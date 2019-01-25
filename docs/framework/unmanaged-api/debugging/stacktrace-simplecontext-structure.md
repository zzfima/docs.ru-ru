---
title: Структура StackTrace_SimpleContext
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 510ef77f217cdd6e3441e3d6684d431fc31307fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698925"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="e2ac5-102">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="e2ac5-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="e2ac5-103">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="e2ac5-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ac5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2ac5-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e2ac5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e2ac5-105">Members</span></span>  
  
|<span data-ttu-id="e2ac5-106">Член</span><span class="sxs-lookup"><span data-stu-id="e2ac5-106">Member</span></span>|<span data-ttu-id="e2ac5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e2ac5-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="e2ac5-108">Указатель стека или указатель стека ввод (ESP) на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="e2ac5-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="e2ac5-109">Смещение кадра или регистр EBP на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="e2ac5-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="e2ac5-110">Указатель инструкций или указатель инструкции ввод (EIP) на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="e2ac5-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ac5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2ac5-111">Remarks</span></span>  
 <span data-ttu-id="e2ac5-112">Так как функции трассировки стека обычно нужно вернуть только адрес, смещение кадров и адрес в стеке, при необходимости можно использовать `SimpleContext` структуры вместо большой `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="e2ac5-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ac5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e2ac5-113">Requirements</span></span>  
 <span data-ttu-id="e2ac5-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ac5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ac5-115">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="e2ac5-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e2ac5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ac5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ac5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e2ac5-117">See also</span></span>
- [<span data-ttu-id="e2ac5-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e2ac5-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="e2ac5-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="e2ac5-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
