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
ms.openlocfilehash: 22ae1d24040a8ee5000e0ff2fbeb2b45e08050df
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784343"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="0e89a-102">Интерфейс ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="0e89a-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="0e89a-103">Реализует методы ICorDebugEnum и перечисляет Икордебугбреакпоинт массивы.</span><span class="sxs-lookup"><span data-stu-id="0e89a-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e89a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0e89a-104">Methods</span></span>  
  
|<span data-ttu-id="0e89a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0e89a-105">Method</span></span>|<span data-ttu-id="0e89a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0e89a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e89a-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0e89a-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="0e89a-108">Возвращает указанное число экземпляров `ICorDebugBreakpoint` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="0e89a-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e89a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0e89a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e89a-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0e89a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e89a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0e89a-111">Requirements</span></span>  
 <span data-ttu-id="0e89a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e89a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e89a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e89a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e89a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e89a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e89a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e89a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e89a-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e89a-116">See also</span></span>

- [<span data-ttu-id="0e89a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0e89a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
