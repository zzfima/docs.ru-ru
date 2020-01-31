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
ms.openlocfilehash: 127022fb8e9f9559ccb0f0c877d25db67eea3037
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784014"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="d6904-102">Интерфейс ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="d6904-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="d6904-103">Реализует методы "ICorDebugEnum" и перечисляет массивы ICorDebugCode.</span><span class="sxs-lookup"><span data-stu-id="d6904-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6904-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d6904-104">Methods</span></span>  
  
|<span data-ttu-id="d6904-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d6904-105">Method</span></span>|<span data-ttu-id="d6904-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d6904-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6904-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="d6904-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="d6904-108">Возвращает указанное число экземпляров `ICorDebugCode` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="d6904-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6904-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d6904-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6904-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d6904-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6904-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d6904-111">Requirements</span></span>  
 <span data-ttu-id="d6904-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6904-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6904-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6904-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6904-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6904-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6904-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6904-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6904-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6904-116">See also</span></span>

- [<span data-ttu-id="d6904-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d6904-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
