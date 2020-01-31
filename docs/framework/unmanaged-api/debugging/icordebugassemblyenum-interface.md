---
title: Интерфейс ICorDebugAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: 1893f1f08d727606fecda7669719760179bb76f9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778059"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="46c1e-102">Интерфейс ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="46c1e-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="46c1e-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugAssembly массивы.</span><span class="sxs-lookup"><span data-stu-id="46c1e-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46c1e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="46c1e-104">Methods</span></span>  
  
|<span data-ttu-id="46c1e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="46c1e-105">Method</span></span>|<span data-ttu-id="46c1e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="46c1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46c1e-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="46c1e-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="46c1e-108">Возвращает указанное число экземпляров `ICorDebugAssembly` в перечислении, начиная с текущей положения.</span><span class="sxs-lookup"><span data-stu-id="46c1e-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46c1e-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="46c1e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46c1e-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="46c1e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c1e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="46c1e-111">Requirements</span></span>  
 <span data-ttu-id="46c1e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c1e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c1e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46c1e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46c1e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46c1e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c1e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c1e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c1e-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="46c1e-116">See also</span></span>

- [<span data-ttu-id="46c1e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="46c1e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
