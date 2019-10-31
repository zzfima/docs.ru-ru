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
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139134"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="d3acf-102">Структура StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="d3acf-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="d3acf-103">Обеспечивает простой контекст, который может использоваться вместо полной структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="d3acf-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3acf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3acf-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d3acf-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d3acf-105">Members</span></span>  
  
|<span data-ttu-id="d3acf-106">Член</span><span class="sxs-lookup"><span data-stu-id="d3acf-106">Member</span></span>|<span data-ttu-id="d3acf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d3acf-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="d3acf-108">Указатель стека или ввод указателя стека (ESP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="d3acf-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="d3acf-109">Смещение кадра или регистр EBP на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="d3acf-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="d3acf-110">Указатель инструкции или ввод указателя инструкции (EIP) на платформах x86.</span><span class="sxs-lookup"><span data-stu-id="d3acf-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3acf-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d3acf-111">Remarks</span></span>  
 <span data-ttu-id="d3acf-112">Так как функции трассировки стека обычно должны возвращать только адрес, Смещение фрейма и адрес стека, при необходимости можно использовать структуру `SimpleContext` вместо большой структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="d3acf-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3acf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d3acf-113">Requirements</span></span>  
 <span data-ttu-id="d3acf-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3acf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3acf-115">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="d3acf-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="d3acf-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3acf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3acf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d3acf-117">See also</span></span>

- [<span data-ttu-id="d3acf-118">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="d3acf-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d3acf-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="d3acf-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
