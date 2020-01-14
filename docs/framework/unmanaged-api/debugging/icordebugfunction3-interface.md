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
ms.openlocfilehash: b74008e0a183d46d82c5262209d582537fd155c7
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938086"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="bb488-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="bb488-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="bb488-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="bb488-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="bb488-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="bb488-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb488-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bb488-105">Methods</span></span>  
  
|<span data-ttu-id="bb488-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bb488-106">Method</span></span>|<span data-ttu-id="bb488-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bb488-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb488-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="bb488-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="bb488-109">Возвращает указатель интерфейса на [икордебугилкоде](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="bb488-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb488-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="bb488-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb488-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bb488-111">Requirements</span></span>  
 <span data-ttu-id="bb488-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb488-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb488-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb488-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb488-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb488-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb488-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb488-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb488-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb488-116">See also</span></span>

- [<span data-ttu-id="bb488-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bb488-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bb488-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="bb488-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="bb488-119">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="bb488-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
