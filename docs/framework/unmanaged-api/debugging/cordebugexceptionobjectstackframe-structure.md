---
title: Структура CorDebugExceptionObjectStackFrame
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: faa2082d31c5fa47b87e2238017066b477fdc191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132178"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="61d8a-102">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="61d8a-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="61d8a-103">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="61d8a-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61d8a-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="61d8a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="61d8a-105">Members</span></span>  
  
|<span data-ttu-id="61d8a-106">Член</span><span class="sxs-lookup"><span data-stu-id="61d8a-106">Member</span></span>|<span data-ttu-id="61d8a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="61d8a-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="61d8a-108">Указатель на объект ICorDebugModule для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="61d8a-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="61d8a-109">Значение указателя инструкций (EIP/RIP) для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="61d8a-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="61d8a-110">Токен метода для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="61d8a-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="61d8a-111">Значение, указывающее, является ли кадр последним кадром во внешнем исключении.</span><span class="sxs-lookup"><span data-stu-id="61d8a-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d8a-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="61d8a-112">Remarks</span></span>  
 <span data-ttu-id="61d8a-113">Вызывающая сторона должна освободить указатель на объект ICorDebugModule, когда он больше не используется.</span><span class="sxs-lookup"><span data-stu-id="61d8a-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61d8a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="61d8a-114">Requirements</span></span>  
 <span data-ttu-id="61d8a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61d8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61d8a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61d8a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61d8a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61d8a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61d8a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61d8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d8a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="61d8a-119">See also</span></span>

- [<span data-ttu-id="61d8a-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="61d8a-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="61d8a-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="61d8a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
