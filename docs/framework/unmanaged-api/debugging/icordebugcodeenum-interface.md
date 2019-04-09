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
ms.openlocfilehash: 6f36ce2fbf57c72102550069989c94b5cc19e58c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186658"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="7b4ea-102">Интерфейс ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="7b4ea-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="7b4ea-103">Реализует методы «ICorDebugEnum» и выполняет перечисление массивов «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="7b4ea-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b4ea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7b4ea-104">Methods</span></span>  
  
|<span data-ttu-id="7b4ea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7b4ea-105">Method</span></span>|<span data-ttu-id="7b4ea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7b4ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b4ea-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="7b4ea-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="7b4ea-108">Возвращает заданное число `ICorDebugCode` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="7b4ea-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b4ea-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b4ea-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b4ea-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7b4ea-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b4ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7b4ea-111">Requirements</span></span>  
 <span data-ttu-id="7b4ea-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b4ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b4ea-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b4ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b4ea-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b4ea-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7b4ea-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7b4ea-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b4ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7b4ea-116">See also</span></span>

- [<span data-ttu-id="7b4ea-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7b4ea-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
