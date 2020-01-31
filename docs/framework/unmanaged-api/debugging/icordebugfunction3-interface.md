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
ms.openlocfilehash: 7ef983c2f0785cb97baf8ba1ad3483b46c08af9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788659"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="1d128-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="1d128-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="1d128-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="1d128-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1d128-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="1d128-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d128-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1d128-105">Methods</span></span>  
  
|<span data-ttu-id="1d128-106">Метод</span><span class="sxs-lookup"><span data-stu-id="1d128-106">Method</span></span>|<span data-ttu-id="1d128-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1d128-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d128-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="1d128-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="1d128-109">Возвращает указатель интерфейса на [икордебугилкоде](icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="1d128-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d128-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="1d128-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d128-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1d128-111">Requirements</span></span>  
 <span data-ttu-id="1d128-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d128-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d128-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d128-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d128-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d128-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d128-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d128-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d128-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d128-116">See also</span></span>

- [<span data-ttu-id="1d128-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1d128-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1d128-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="1d128-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="1d128-119">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="1d128-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
