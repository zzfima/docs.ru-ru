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
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088864"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="df230-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="df230-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="df230-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="df230-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="df230-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="df230-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df230-105">Методы</span><span class="sxs-lookup"><span data-stu-id="df230-105">Methods</span></span>  
  
|<span data-ttu-id="df230-106">Метод</span><span class="sxs-lookup"><span data-stu-id="df230-106">Method</span></span>|<span data-ttu-id="df230-107">Описание</span><span class="sxs-lookup"><span data-stu-id="df230-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df230-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="df230-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="df230-109">Получает указатель интерфейса на [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="df230-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df230-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="df230-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df230-111">Требования</span><span class="sxs-lookup"><span data-stu-id="df230-111">Requirements</span></span>  
 <span data-ttu-id="df230-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df230-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df230-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df230-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df230-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df230-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="df230-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="df230-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df230-116">См. также</span><span class="sxs-lookup"><span data-stu-id="df230-116">See also</span></span>

- [<span data-ttu-id="df230-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="df230-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="df230-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="df230-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="df230-119">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="df230-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
