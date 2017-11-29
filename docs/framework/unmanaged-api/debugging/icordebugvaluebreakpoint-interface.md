---
title: "ICorDebugValueBreakpoint интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValueBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValueBreakpoint
helpviewer_keywords: ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 04ce1827bbc70fc4f1406f802c3a382858b08699
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="d7fbe-102">ICorDebugValueBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="d7fbe-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="d7fbe-103">Расширяет интерфейс ICorDebugBreakpoint для предоставления доступа к определенным значениям.</span><span class="sxs-lookup"><span data-stu-id="d7fbe-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7fbe-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d7fbe-104">Methods</span></span>  
  
|<span data-ttu-id="d7fbe-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d7fbe-105">Method</span></span>|<span data-ttu-id="d7fbe-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d7fbe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7fbe-107">GetValue-метод</span><span class="sxs-lookup"><span data-stu-id="d7fbe-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="d7fbe-108">Получает указатель на интерфейс ICorDebugValue объекта, который представляет значение объекта, на которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="d7fbe-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7fbe-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7fbe-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7fbe-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d7fbe-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7fbe-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d7fbe-111">Requirements</span></span>  
 <span data-ttu-id="d7fbe-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7fbe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7fbe-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7fbe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7fbe-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7fbe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7fbe-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7fbe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fbe-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d7fbe-116">See Also</span></span>  
 [<span data-ttu-id="d7fbe-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d7fbe-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
