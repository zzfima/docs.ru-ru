---
title: Интерфейс ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167750"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="05155-102">Интерфейс ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="05155-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="05155-103">Расширяет интерфейс ICorDebugBreakpoint для предоставления доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="05155-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05155-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05155-104">Methods</span></span>  
  
|<span data-ttu-id="05155-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05155-105">Method</span></span>|<span data-ttu-id="05155-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05155-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05155-107">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="05155-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="05155-108">Получает указатель на интерфейс ICorDebugValue объект, представляющий значение объекта, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="05155-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05155-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="05155-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05155-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="05155-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05155-111">Требования</span><span class="sxs-lookup"><span data-stu-id="05155-111">Requirements</span></span>  
 <span data-ttu-id="05155-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05155-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05155-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05155-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05155-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05155-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="05155-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="05155-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05155-116">См. также</span><span class="sxs-lookup"><span data-stu-id="05155-116">See also</span></span>

- [<span data-ttu-id="05155-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05155-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
