---
title: "Интерфейс ICorDebugFunction3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction3
api_location: mscordbi.dll
api_type: COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfe0c420c1c9b8074b7cb769e592f8cb2f5916e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="a6f22-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="a6f22-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="a6f22-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="a6f22-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a6f22-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="a6f22-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6f22-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a6f22-105">Methods</span></span>  
  
|<span data-ttu-id="a6f22-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a6f22-106">Method</span></span>|<span data-ttu-id="a6f22-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a6f22-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6f22-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="a6f22-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="a6f22-109">Возвращает указатель интерфейса [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий промежуточный язык из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="a6f22-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6f22-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6f22-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f22-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a6f22-111">Requirements</span></span>  
 <span data-ttu-id="a6f22-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f22-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f22-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6f22-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6f22-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f22-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f22-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f22-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f22-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a6f22-116">See Also</span></span>  
 [<span data-ttu-id="a6f22-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a6f22-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a6f22-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="a6f22-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="a6f22-119">ReJIT: Практические руководства</span><span class="sxs-lookup"><span data-stu-id="a6f22-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
