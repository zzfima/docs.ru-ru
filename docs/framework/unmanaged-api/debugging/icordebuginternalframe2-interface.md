---
title: "Интерфейс ICorDebugInternalFrame2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2
helpviewer_keywords: ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b612cb2fb8b2a84555ccf36a8537ebecff673d47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="5ae38-102">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="5ae38-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="5ae38-103">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно объектов ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="5ae38-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ae38-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5ae38-104">Methods</span></span>  
  
|<span data-ttu-id="5ae38-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5ae38-105">Method</span></span>|<span data-ttu-id="5ae38-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5ae38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ae38-107">Метод GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="5ae38-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="5ae38-108">Возвращает адрес внутреннего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="5ae38-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="5ae38-109">Метод IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="5ae38-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="5ae38-110">Проверяет, является ли `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="5ae38-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ae38-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ae38-111">Remarks</span></span>  
 <span data-ttu-id="5ae38-112">Этот интерфейс расширяет интерфейс ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="5ae38-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ae38-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5ae38-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae38-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5ae38-114">Requirements</span></span>  
 <span data-ttu-id="5ae38-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae38-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ae38-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ae38-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ae38-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ae38-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ae38-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae38-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae38-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5ae38-119">See Also</span></span>  
 [<span data-ttu-id="5ae38-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5ae38-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5ae38-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="5ae38-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
