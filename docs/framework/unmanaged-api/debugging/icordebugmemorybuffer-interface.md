---
title: Интерфейс ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 019fc3db0f09dc9e5cb22ba3cf012605bf865d6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574863"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="ec696-102">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="ec696-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="ec696-103">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="ec696-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec696-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ec696-104">Methods</span></span>  
  
|<span data-ttu-id="ec696-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ec696-105">Method</span></span>|<span data-ttu-id="ec696-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="ec696-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec696-107">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="ec696-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="ec696-108">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="ec696-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="ec696-109">Метод GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="ec696-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="ec696-110">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="ec696-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec696-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec696-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec696-112">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ec696-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ec696-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ec696-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec696-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ec696-114">Requirements</span></span>  
 <span data-ttu-id="ec696-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec696-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec696-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec696-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec696-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec696-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec696-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec696-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec696-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ec696-119">See also</span></span>
- [<span data-ttu-id="ec696-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ec696-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ec696-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="ec696-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
