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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febfe7df52a0c1f44cb156faf2da310d317e01a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411329"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="7bbde-102">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="7bbde-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="7bbde-103">Предоставляет метод, который расширяет возможности «ICorDebugCode» и «ICorDebugCode2» для предоставления сведений об управляемом возвращаемом значении.</span><span class="sxs-lookup"><span data-stu-id="7bbde-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bbde-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7bbde-104">Methods</span></span>  
  
|<span data-ttu-id="7bbde-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7bbde-105">Method</span></span>|<span data-ttu-id="7bbde-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7bbde-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bbde-107">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="7bbde-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="7bbde-108">Для заданного смещения IL возвращает собственные смещения, где разместить точку останова, чтобы отладчик можно получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="7bbde-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bbde-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bbde-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bbde-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7bbde-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bbde-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7bbde-111">Requirements</span></span>  
 <span data-ttu-id="7bbde-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bbde-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bbde-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bbde-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bbde-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bbde-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bbde-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bbde-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbde-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7bbde-116">See Also</span></span>  
    
    
    
 [<span data-ttu-id="7bbde-117">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="7bbde-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 [<span data-ttu-id="7bbde-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7bbde-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
