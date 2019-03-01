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
ms.openlocfilehash: 57a36f1d15ad251781b4d9843086a966fa2d4585
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982132"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="ee151-102">Интерфейс ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="ee151-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="ee151-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugChain.</span><span class="sxs-lookup"><span data-stu-id="ee151-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee151-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ee151-104">Methods</span></span>  
  
|<span data-ttu-id="ee151-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ee151-105">Method</span></span>|<span data-ttu-id="ee151-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="ee151-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee151-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="ee151-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="ee151-108">Возвращает заданное число `ICorDebugChain` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ee151-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee151-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee151-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee151-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ee151-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee151-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ee151-111">Requirements</span></span>  
 <span data-ttu-id="ee151-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee151-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee151-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee151-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee151-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee151-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee151-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee151-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee151-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ee151-116">See also</span></span>
- [<span data-ttu-id="ee151-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ee151-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
