---
title: Интерфейс ICorDebugCode3
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: f2f75c3c54c0fa2d55dc0179c05e4edea6e36738
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777819"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="2e542-102">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="2e542-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="2e542-103">Предоставляет метод, который расширяет "ICorDebugCode" и "ICorDebugCode2" для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="2e542-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e542-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2e542-104">Methods</span></span>  
  
|<span data-ttu-id="2e542-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2e542-105">Method</span></span>|<span data-ttu-id="2e542-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2e542-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e542-107">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="2e542-107">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="2e542-108">Для указанного смещения IL получает машинные смещения, в которых должна быть помещена точка останова, чтобы отладчик мог получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="2e542-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e542-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="2e542-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e542-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="2e542-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e542-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2e542-111">Requirements</span></span>  
 <span data-ttu-id="2e542-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e542-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e542-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e542-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e542-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e542-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e542-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e542-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e542-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e542-116">See also</span></span>

- [<span data-ttu-id="2e542-117">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="2e542-117">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="2e542-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2e542-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
