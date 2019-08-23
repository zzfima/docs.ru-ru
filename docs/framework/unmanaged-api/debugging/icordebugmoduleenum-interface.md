---
title: Интерфейс ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 682fe190126d4f40013678d996804e9f3481bc02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965088"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="ee994-102">Интерфейс ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="ee994-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="ee994-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugModule массивы.</span><span class="sxs-lookup"><span data-stu-id="ee994-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee994-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ee994-104">Methods</span></span>  
  
|<span data-ttu-id="ee994-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ee994-105">Method</span></span>|<span data-ttu-id="ee994-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ee994-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee994-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="ee994-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="ee994-108">Возвращает указанное количество `ICorDebugModule` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ee994-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee994-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee994-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee994-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ee994-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee994-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ee994-111">Requirements</span></span>  
 <span data-ttu-id="ee994-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee994-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee994-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ee994-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee994-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="ee994-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee994-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee994-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee994-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ee994-116">See also</span></span>

- [<span data-ttu-id="ee994-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ee994-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
