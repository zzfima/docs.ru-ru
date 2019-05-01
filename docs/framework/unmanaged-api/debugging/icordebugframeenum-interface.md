---
title: Интерфейс ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd24dfa6771ca450e79b4b932735968ecc51fc90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995791"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="05579-102">Интерфейс ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="05579-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="05579-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="05579-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05579-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05579-104">Methods</span></span>  
  
|<span data-ttu-id="05579-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05579-105">Method</span></span>|<span data-ttu-id="05579-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05579-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05579-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="05579-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="05579-108">Возвращает заданное число `ICorDebugFrame` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="05579-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05579-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="05579-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05579-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="05579-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05579-111">Требования</span><span class="sxs-lookup"><span data-stu-id="05579-111">Requirements</span></span>  
 <span data-ttu-id="05579-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05579-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05579-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05579-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05579-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05579-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05579-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05579-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05579-116">См. также</span><span class="sxs-lookup"><span data-stu-id="05579-116">See also</span></span>

- [<span data-ttu-id="05579-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05579-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
