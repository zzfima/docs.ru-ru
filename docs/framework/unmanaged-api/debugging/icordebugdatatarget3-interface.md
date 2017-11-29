---
title: "Интерфейс ICorDebugDataTarget3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1ab94e792265916e29ed24239e25cb5d57d1313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="9eca2-102">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="9eca2-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="9eca2-103">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="9eca2-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="9eca2-104">Метод</span><span class="sxs-lookup"><span data-stu-id="9eca2-104">Method</span></span>  
  
|<span data-ttu-id="9eca2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9eca2-105">Method</span></span>|<span data-ttu-id="9eca2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9eca2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9eca2-107">Метод GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="9eca2-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="9eca2-108">Возвращает список модулей, загруженных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="9eca2-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9eca2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9eca2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9eca2-110">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9eca2-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9eca2-111">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9eca2-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eca2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9eca2-112">Requirements</span></span>  
 <span data-ttu-id="9eca2-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eca2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eca2-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9eca2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9eca2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9eca2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9eca2-116">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eca2-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eca2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9eca2-117">See Also</span></span>  
 [<span data-ttu-id="9eca2-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9eca2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9eca2-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="9eca2-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
