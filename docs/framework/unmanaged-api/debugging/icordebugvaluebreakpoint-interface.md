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
ms.openlocfilehash: f77268e069d322d0f491f78b154cf63b691e3e38
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966815"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="6b61f-102">Интерфейс ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b61f-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="6b61f-103">Расширяет интерфейс Икордебугбреакпоинт для предоставления доступа к конкретным значениям.</span><span class="sxs-lookup"><span data-stu-id="6b61f-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b61f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6b61f-104">Methods</span></span>  
  
|<span data-ttu-id="6b61f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6b61f-105">Method</span></span>|<span data-ttu-id="6b61f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6b61f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b61f-107">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="6b61f-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="6b61f-108">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий значение объекта, для которого задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="6b61f-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b61f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b61f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b61f-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6b61f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b61f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b61f-111">Requirements</span></span>  
 <span data-ttu-id="6b61f-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b61f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b61f-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6b61f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b61f-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="6b61f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b61f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b61f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b61f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6b61f-116">See also</span></span>

- [<span data-ttu-id="6b61f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6b61f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
