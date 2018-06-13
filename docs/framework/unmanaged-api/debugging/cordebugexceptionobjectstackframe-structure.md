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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48b15429d40d3a69db52615592fc1697f385d319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403735"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="c3ac4-102">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="c3ac4-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="c3ac4-103">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ac4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3ac4-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="c3ac4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c3ac4-105">Members</span></span>  
  
|<span data-ttu-id="c3ac4-106">Член</span><span class="sxs-lookup"><span data-stu-id="c3ac4-106">Member</span></span>|<span data-ttu-id="c3ac4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c3ac4-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="c3ac4-108">Указатель на объект ICorDebugModule для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="c3ac4-109">Значение указателя инструкций (EIP и RIP) для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="c3ac4-110">Токен метода для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="c3ac4-111">Значение, указывающее, является ли рамка последнего кадра внешнего исключения.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3ac4-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3ac4-112">Remarks</span></span>  
 <span data-ttu-id="c3ac4-113">Вызывающий объект должен освободить указатель на объект ICorDebugModule, когда он больше нет используется.</span><span class="sxs-lookup"><span data-stu-id="c3ac4-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ac4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c3ac4-114">Requirements</span></span>  
 <span data-ttu-id="c3ac4-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3ac4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ac4-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3ac4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3ac4-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3ac4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3ac4-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ac4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ac4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c3ac4-119">See Also</span></span>  
 [<span data-ttu-id="c3ac4-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="c3ac4-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="c3ac4-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="c3ac4-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
