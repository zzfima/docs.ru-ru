---
title: Интерфейс ICorDebugInternalFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4082c4204b85aba97651419db15ba8eb4c3d54e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415166"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="84876-102">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="84876-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="84876-103">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно объектов ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="84876-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84876-104">Методы</span><span class="sxs-lookup"><span data-stu-id="84876-104">Methods</span></span>  
  
|<span data-ttu-id="84876-105">Метод</span><span class="sxs-lookup"><span data-stu-id="84876-105">Method</span></span>|<span data-ttu-id="84876-106">Описание</span><span class="sxs-lookup"><span data-stu-id="84876-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84876-107">Метод GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="84876-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="84876-108">Возвращает адрес внутреннего кадра стека.</span><span class="sxs-lookup"><span data-stu-id="84876-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="84876-109">Метод IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="84876-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="84876-110">Проверяет, является ли `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="84876-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84876-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="84876-111">Remarks</span></span>  
 <span data-ttu-id="84876-112">Этот интерфейс расширяет интерфейс ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="84876-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84876-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="84876-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84876-114">Требования</span><span class="sxs-lookup"><span data-stu-id="84876-114">Requirements</span></span>  
 <span data-ttu-id="84876-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84876-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84876-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84876-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84876-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84876-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84876-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84876-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84876-119">См. также</span><span class="sxs-lookup"><span data-stu-id="84876-119">See Also</span></span>  
 [<span data-ttu-id="84876-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84876-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="84876-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="84876-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
