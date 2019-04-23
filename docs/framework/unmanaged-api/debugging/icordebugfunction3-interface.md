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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088864"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="0949e-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="0949e-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="0949e-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="0949e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0949e-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0949e-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0949e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0949e-105">Methods</span></span>  
  
|<span data-ttu-id="0949e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0949e-106">Method</span></span>|<span data-ttu-id="0949e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0949e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0949e-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="0949e-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="0949e-109">Получает указатель интерфейса на [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0949e-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0949e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0949e-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0949e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0949e-111">Requirements</span></span>  
 <span data-ttu-id="0949e-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0949e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0949e-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0949e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0949e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0949e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0949e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0949e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0949e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0949e-116">See also</span></span>

- [<span data-ttu-id="0949e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0949e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0949e-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="0949e-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="0949e-119">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="0949e-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
