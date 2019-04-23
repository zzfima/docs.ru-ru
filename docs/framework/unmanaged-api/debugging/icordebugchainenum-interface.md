---
title: Интерфейс ICorDebugChainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d8a64b7dcaf4758cba217be06fa7d09f6c76920
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072960"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="7da13-102">Интерфейс ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="7da13-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="7da13-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugChain.</span><span class="sxs-lookup"><span data-stu-id="7da13-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7da13-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7da13-104">Methods</span></span>  
  
|<span data-ttu-id="7da13-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7da13-105">Method</span></span>|<span data-ttu-id="7da13-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7da13-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7da13-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="7da13-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="7da13-108">Возвращает заданное число `ICorDebugChain` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="7da13-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da13-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7da13-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7da13-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7da13-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da13-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7da13-111">Requirements</span></span>  
 <span data-ttu-id="7da13-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da13-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da13-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7da13-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7da13-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7da13-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7da13-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da13-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da13-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7da13-116">See also</span></span>

- [<span data-ttu-id="7da13-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7da13-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
