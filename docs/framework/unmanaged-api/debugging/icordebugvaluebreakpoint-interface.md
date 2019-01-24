---
title: Интерфейс1 ICorDebugValueBreakpoint
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
ms.openlocfilehash: 58e6807b0546eadc4baacc276fa1ba7bda4e3aba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557764"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="69b00-102">Интерфейс1 ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="69b00-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="69b00-103">Расширяет интерфейс ICorDebugBreakpoint для предоставления доступа к указанным значениям.</span><span class="sxs-lookup"><span data-stu-id="69b00-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69b00-104">Методы</span><span class="sxs-lookup"><span data-stu-id="69b00-104">Methods</span></span>  
  
|<span data-ttu-id="69b00-105">Метод</span><span class="sxs-lookup"><span data-stu-id="69b00-105">Method</span></span>|<span data-ttu-id="69b00-106">Описание</span><span class="sxs-lookup"><span data-stu-id="69b00-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69b00-107">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="69b00-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="69b00-108">Получает указатель на интерфейс ICorDebugValue объект, представляющий значение объекта, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="69b00-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69b00-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="69b00-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69b00-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="69b00-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69b00-111">Требования</span><span class="sxs-lookup"><span data-stu-id="69b00-111">Requirements</span></span>  
 <span data-ttu-id="69b00-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69b00-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69b00-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69b00-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69b00-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69b00-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69b00-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69b00-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b00-116">См. также</span><span class="sxs-lookup"><span data-stu-id="69b00-116">See also</span></span>
- [<span data-ttu-id="69b00-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="69b00-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
