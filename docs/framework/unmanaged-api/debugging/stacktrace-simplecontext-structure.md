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
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986535"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="31891-102">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="31891-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="31891-103">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="31891-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31891-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31891-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="31891-105">Участники</span><span class="sxs-lookup"><span data-stu-id="31891-105">Members</span></span>  
  
|<span data-ttu-id="31891-106">Член</span><span class="sxs-lookup"><span data-stu-id="31891-106">Member</span></span>|<span data-ttu-id="31891-107">Описание</span><span class="sxs-lookup"><span data-stu-id="31891-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="31891-108">Указатель стека или указатель стека ввод (ESP) на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="31891-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="31891-109">Смещение кадра или регистр EBP на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="31891-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="31891-110">Указатель инструкций или указатель инструкции ввод (EIP) на x86 платформ.</span><span class="sxs-lookup"><span data-stu-id="31891-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31891-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="31891-111">Remarks</span></span>  
 <span data-ttu-id="31891-112">Так как функции трассировки стека обычно нужно вернуть только адрес, смещение кадров и адрес в стеке, при необходимости можно использовать `SimpleContext` структуры вместо большой `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="31891-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31891-113">Требования</span><span class="sxs-lookup"><span data-stu-id="31891-113">Requirements</span></span>  
 <span data-ttu-id="31891-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31891-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31891-115">**Заголовок.** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="31891-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="31891-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31891-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31891-117">См. также</span><span class="sxs-lookup"><span data-stu-id="31891-117">See also</span></span>

- [<span data-ttu-id="31891-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="31891-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="31891-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="31891-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
