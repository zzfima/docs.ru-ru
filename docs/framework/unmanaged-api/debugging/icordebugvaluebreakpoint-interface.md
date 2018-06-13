---
title: ICorDebugValueBreakpoint интерфейс1
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
ms.openlocfilehash: fbb0479ee9d14b534e419c74560f4da527884246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419056"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="1b0b3-102">ICorDebugValueBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="1b0b3-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="1b0b3-103">Расширяет интерфейс ICorDebugBreakpoint для предоставления доступа к определенным значениям.</span><span class="sxs-lookup"><span data-stu-id="1b0b3-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b0b3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1b0b3-104">Methods</span></span>  
  
|<span data-ttu-id="1b0b3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1b0b3-105">Method</span></span>|<span data-ttu-id="1b0b3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1b0b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b0b3-107">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="1b0b3-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="1b0b3-108">Получает указатель на интерфейс ICorDebugValue объекта, который представляет значение объекта, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="1b0b3-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b0b3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b0b3-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0b3-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="1b0b3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b0b3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1b0b3-111">Requirements</span></span>  
 <span data-ttu-id="1b0b3-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b0b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b0b3-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b0b3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b0b3-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b0b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b0b3-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b0b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0b3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1b0b3-116">See Also</span></span>  
 [<span data-ttu-id="1b0b3-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b0b3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
