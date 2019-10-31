---
title: Интерфейс ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096143"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="c03a7-102">Интерфейс ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c03a7-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="c03a7-103">Реализует методы ICorDebugEnum и перечисляет массивы объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="c03a7-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c03a7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c03a7-104">Methods</span></span>  
  
|<span data-ttu-id="c03a7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c03a7-105">Method</span></span>|<span data-ttu-id="c03a7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c03a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c03a7-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="c03a7-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="c03a7-108">Возвращает RVA указанного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="c03a7-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c03a7-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c03a7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c03a7-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c03a7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c03a7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c03a7-111">Requirements</span></span>  
 <span data-ttu-id="c03a7-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c03a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c03a7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c03a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c03a7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c03a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c03a7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c03a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c03a7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c03a7-116">See also</span></span>

- [<span data-ttu-id="c03a7-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c03a7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
