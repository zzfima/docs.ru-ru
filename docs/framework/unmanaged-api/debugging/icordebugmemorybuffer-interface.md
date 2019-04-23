---
title: Интерфейс ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072913"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="fabfe-102">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="fabfe-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="fabfe-103">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="fabfe-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fabfe-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fabfe-104">Methods</span></span>  
  
|<span data-ttu-id="fabfe-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fabfe-105">Method</span></span>|<span data-ttu-id="fabfe-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fabfe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fabfe-107">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="fabfe-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="fabfe-108">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="fabfe-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="fabfe-109">Метод GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="fabfe-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="fabfe-110">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="fabfe-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fabfe-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fabfe-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fabfe-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fabfe-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="fabfe-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fabfe-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fabfe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fabfe-114">Requirements</span></span>  
 <span data-ttu-id="fabfe-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fabfe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabfe-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fabfe-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fabfe-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fabfe-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fabfe-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fabfe-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabfe-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fabfe-119">See also</span></span>

- [<span data-ttu-id="fabfe-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fabfe-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fabfe-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="fabfe-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
