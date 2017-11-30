---
title: "Структура CorDebugExceptionObjectStackFrame"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionObjectStackFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionObjectStackFrame
helpviewer_keywords: CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf166f606aa2c0e0900356395c36bd6875897e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="df2ce-102">Структура CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="df2ce-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="df2ce-103">Представляет сведения о кадре стека из объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="df2ce-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df2ce-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="df2ce-105">Члены</span><span class="sxs-lookup"><span data-stu-id="df2ce-105">Members</span></span>  
  
|<span data-ttu-id="df2ce-106">Член</span><span class="sxs-lookup"><span data-stu-id="df2ce-106">Member</span></span>|<span data-ttu-id="df2ce-107">Описание</span><span class="sxs-lookup"><span data-stu-id="df2ce-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="df2ce-108">Указатель на объект ICorDebugModule для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="df2ce-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="df2ce-109">Значение указателя инструкций (EIP и RIP) для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="df2ce-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="df2ce-110">Токен метода для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="df2ce-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="df2ce-111">Значение, указывающее, является ли рамка последнего кадра внешнего исключения.</span><span class="sxs-lookup"><span data-stu-id="df2ce-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df2ce-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="df2ce-112">Remarks</span></span>  
 <span data-ttu-id="df2ce-113">Вызывающий объект должен освободить указатель на объект ICorDebugModule, когда он больше нет используется.</span><span class="sxs-lookup"><span data-stu-id="df2ce-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df2ce-114">Требования</span><span class="sxs-lookup"><span data-stu-id="df2ce-114">Requirements</span></span>  
 <span data-ttu-id="df2ce-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2ce-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df2ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df2ce-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df2ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df2ce-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2ce-119">См. также</span><span class="sxs-lookup"><span data-stu-id="df2ce-119">See Also</span></span>  
 [<span data-ttu-id="df2ce-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="df2ce-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="df2ce-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="df2ce-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
