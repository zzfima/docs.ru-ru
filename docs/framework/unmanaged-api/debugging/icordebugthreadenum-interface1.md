---
title: Интерфейс ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7edf103e397c6e3e1577b5ed4bc8fc0df264b843
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137999"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="43bfd-102">Интерфейс ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="43bfd-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="43bfd-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="43bfd-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43bfd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="43bfd-104">Methods</span></span>  
  
|<span data-ttu-id="43bfd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="43bfd-105">Method</span></span>|<span data-ttu-id="43bfd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="43bfd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43bfd-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="43bfd-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-next-method.md)|<span data-ttu-id="43bfd-108">Возвращает заданное число `ICorDebugThread` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="43bfd-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43bfd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="43bfd-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43bfd-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="43bfd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43bfd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="43bfd-111">Requirements</span></span>  
 <span data-ttu-id="43bfd-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43bfd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43bfd-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43bfd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43bfd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43bfd-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="43bfd-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="43bfd-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43bfd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="43bfd-116">See also</span></span>

- [<span data-ttu-id="43bfd-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="43bfd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
