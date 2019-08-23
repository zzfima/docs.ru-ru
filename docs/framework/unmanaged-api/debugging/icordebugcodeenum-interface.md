---
title: Интерфейс ICorDebugCodeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a771100ad4d63173fdb3b1ddea5ae3d67fbbc7c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960679"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="a1d31-102">Интерфейс ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="a1d31-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="a1d31-103">Реализует методы "ICorDebugEnum" и перечисляет массивы ICorDebugCode.</span><span class="sxs-lookup"><span data-stu-id="a1d31-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1d31-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a1d31-104">Methods</span></span>  
  
|<span data-ttu-id="a1d31-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a1d31-105">Method</span></span>|<span data-ttu-id="a1d31-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a1d31-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1d31-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="a1d31-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="a1d31-108">Возвращает указанное количество `ICorDebugCode` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a1d31-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1d31-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1d31-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1d31-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a1d31-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d31-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a1d31-111">Requirements</span></span>  
 <span data-ttu-id="a1d31-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1d31-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d31-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a1d31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1d31-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a1d31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1d31-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d31-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a1d31-116">See also</span></span>

- [<span data-ttu-id="a1d31-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a1d31-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
