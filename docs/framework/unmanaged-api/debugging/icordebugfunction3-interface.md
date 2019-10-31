---
title: Интерфейс ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: fc50fd7180aaf5c1cff2147268d34921eec39e8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137762"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="44c8a-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="44c8a-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="44c8a-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="44c8a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="44c8a-104">Логически расширяет интерфейс ICorDebugFunction, чтобы предоставить доступ к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="44c8a-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44c8a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="44c8a-105">Methods</span></span>  
  
|<span data-ttu-id="44c8a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="44c8a-106">Method</span></span>|<span data-ttu-id="44c8a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="44c8a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44c8a-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="44c8a-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="44c8a-109">Возвращает указатель интерфейса на [икордебугилкоде](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="44c8a-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44c8a-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="44c8a-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c8a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="44c8a-111">Requirements</span></span>  
 <span data-ttu-id="44c8a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c8a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c8a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44c8a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44c8a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44c8a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44c8a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c8a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c8a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="44c8a-116">See also</span></span>

- [<span data-ttu-id="44c8a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="44c8a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="44c8a-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="44c8a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="44c8a-119">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="44c8a-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
