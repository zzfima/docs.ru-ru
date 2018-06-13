---
title: Интерфейс ICorDebugILFrame3
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be45022701f72e15e83b7ca28cd110ef58c809b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415601"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="7e862-102">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="7e862-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="7e862-103">Предоставляет метод, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="7e862-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="7e862-104">`ICorDebugILFrame3` является логическим расширением ICorDebugILFrame и ICorDebugILFrame2 интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7e862-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e862-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7e862-105">Methods</span></span>  
  
|<span data-ttu-id="7e862-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7e862-106">Method</span></span>|<span data-ttu-id="7e862-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7e862-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e862-108">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="7e862-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="7e862-109">Возвращает объект ICorDebugValue, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="7e862-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e862-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e862-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e862-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7e862-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e862-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7e862-112">Requirements</span></span>  
 <span data-ttu-id="7e862-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e862-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e862-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e862-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e862-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e862-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e862-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e862-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e862-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7e862-117">See Also</span></span>  
 [<span data-ttu-id="7e862-118">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="7e862-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="7e862-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7e862-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
