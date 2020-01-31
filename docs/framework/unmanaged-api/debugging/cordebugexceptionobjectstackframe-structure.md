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
ms.openlocfilehash: 2845c15d67e287d6efb0cd0a9c940b69de3a1c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789366"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="917b6-102">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="917b6-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="917b6-103">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="917b6-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="917b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="917b6-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="917b6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="917b6-105">Members</span></span>  
  
|<span data-ttu-id="917b6-106">Член</span><span class="sxs-lookup"><span data-stu-id="917b6-106">Member</span></span>|<span data-ttu-id="917b6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="917b6-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="917b6-108">Указатель на объект ICorDebugModule для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="917b6-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="917b6-109">Значение указателя инструкций (EIP/RIP) для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="917b6-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="917b6-110">Токен метода для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="917b6-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="917b6-111">Значение, указывающее, является ли кадр последним кадром во внешнем исключении.</span><span class="sxs-lookup"><span data-stu-id="917b6-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="917b6-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="917b6-112">Remarks</span></span>  
 <span data-ttu-id="917b6-113">Вызывающая сторона должна освободить указатель на объект ICorDebugModule, когда он больше не используется.</span><span class="sxs-lookup"><span data-stu-id="917b6-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="917b6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="917b6-114">Requirements</span></span>  
 <span data-ttu-id="917b6-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="917b6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="917b6-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="917b6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="917b6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="917b6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="917b6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="917b6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917b6-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="917b6-119">See also</span></span>

- [<span data-ttu-id="917b6-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="917b6-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="917b6-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="917b6-121">Debugging</span></span>](index.md)
