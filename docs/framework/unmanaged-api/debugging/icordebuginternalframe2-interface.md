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
ms.openlocfilehash: 2377773b471b387376f0284522ebe29d6b003ae3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910111"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="68126-102">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="68126-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="68126-103">Предоставляет сведения о внутренних кадрах, включая адрес стека и расположение по отношению к объектам ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="68126-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68126-104">Методы</span><span class="sxs-lookup"><span data-stu-id="68126-104">Methods</span></span>  
  
|<span data-ttu-id="68126-105">Метод</span><span class="sxs-lookup"><span data-stu-id="68126-105">Method</span></span>|<span data-ttu-id="68126-106">Описание</span><span class="sxs-lookup"><span data-stu-id="68126-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68126-107">Метод GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="68126-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="68126-108">Возвращает адрес стека внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="68126-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="68126-109">Метод IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="68126-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="68126-110">Проверяет, находится `this` ли внутренний кадр ближе к конечному объекту, чем указанный объект ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="68126-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68126-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="68126-111">Remarks</span></span>  
 <span data-ttu-id="68126-112">Этот интерфейс расширяет интерфейс ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="68126-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68126-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="68126-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68126-114">Требования</span><span class="sxs-lookup"><span data-stu-id="68126-114">Requirements</span></span>  
 <span data-ttu-id="68126-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68126-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68126-116">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="68126-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68126-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="68126-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68126-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68126-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68126-119">См. также</span><span class="sxs-lookup"><span data-stu-id="68126-119">See also</span></span>

- [<span data-ttu-id="68126-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="68126-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="68126-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="68126-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
