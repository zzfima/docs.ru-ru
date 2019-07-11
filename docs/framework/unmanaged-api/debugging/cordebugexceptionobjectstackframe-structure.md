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
ms.openlocfilehash: 5cd2add7e96a8edaff8509563ae1846e80132001
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740099"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="b89e9-102">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="b89e9-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="b89e9-103">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="b89e9-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b89e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b89e9-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="b89e9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b89e9-105">Members</span></span>  
  
|<span data-ttu-id="b89e9-106">Член</span><span class="sxs-lookup"><span data-stu-id="b89e9-106">Member</span></span>|<span data-ttu-id="b89e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b89e9-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="b89e9-108">Указатель на объект ICorDebugModule для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="b89e9-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="b89e9-109">Значение указателя инструкций (EIP/зарезервированного IP-адреса) для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="b89e9-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="b89e9-110">Токен метода для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="b89e9-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="b89e9-111">Значение, указывающее, является ли кадр в последнем фрейме внешнего исключения.</span><span class="sxs-lookup"><span data-stu-id="b89e9-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b89e9-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b89e9-112">Remarks</span></span>  
 <span data-ttu-id="b89e9-113">Вызывающий объект должен освободить указатель на объект ICorDebugModule, когда он больше не используется.</span><span class="sxs-lookup"><span data-stu-id="b89e9-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b89e9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b89e9-114">Requirements</span></span>  
 <span data-ttu-id="b89e9-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b89e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b89e9-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b89e9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b89e9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b89e9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b89e9-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b89e9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89e9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b89e9-119">See also</span></span>

- [<span data-ttu-id="b89e9-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b89e9-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="b89e9-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="b89e9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
