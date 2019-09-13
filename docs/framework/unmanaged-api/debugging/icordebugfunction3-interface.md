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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3eebdf56796fe599ec6ff62d7008d1af3be796e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926836"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="5b6dd-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="5b6dd-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="5b6dd-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="5b6dd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5b6dd-104">Логически расширяет интерфейс ICorDebugFunction, чтобы предоставить доступ к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="5b6dd-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b6dd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5b6dd-105">Methods</span></span>  
  
|<span data-ttu-id="5b6dd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5b6dd-106">Method</span></span>|<span data-ttu-id="5b6dd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5b6dd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b6dd-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="5b6dd-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="5b6dd-109">Возвращает указатель интерфейса на [икордебугилкоде](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="5b6dd-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b6dd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b6dd-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6dd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5b6dd-111">Requirements</span></span>  
 <span data-ttu-id="5b6dd-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b6dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6dd-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5b6dd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b6dd-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="5b6dd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b6dd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6dd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5b6dd-116">See also</span></span>

- [<span data-ttu-id="5b6dd-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5b6dd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5b6dd-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="5b6dd-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5b6dd-119">ReJIT Руководство</span><span class="sxs-lookup"><span data-stu-id="5b6dd-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
