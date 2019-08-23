---
title: Интерфейс ICorDebugBreakpointEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8192bd7ccaebab78158f11adb79509031132ecd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937017"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="f67a3-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="f67a3-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="f67a3-103">Реализует методы ICorDebugEnum и перечисляет Икордебугбреакпоинт массивы.</span><span class="sxs-lookup"><span data-stu-id="f67a3-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f67a3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f67a3-104">Methods</span></span>  
  
|<span data-ttu-id="f67a3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f67a3-105">Method</span></span>|<span data-ttu-id="f67a3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f67a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f67a3-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f67a3-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="f67a3-108">Возвращает указанное количество `ICorDebugBreakpoint` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="f67a3-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f67a3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f67a3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f67a3-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f67a3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f67a3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f67a3-111">Requirements</span></span>  
 <span data-ttu-id="f67a3-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f67a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f67a3-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f67a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f67a3-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f67a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f67a3-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f67a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f67a3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f67a3-116">See also</span></span>

- [<span data-ttu-id="f67a3-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f67a3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
