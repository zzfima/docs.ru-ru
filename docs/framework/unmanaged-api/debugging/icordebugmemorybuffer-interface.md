---
title: Интерфейс ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072913"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="26a3b-102">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="26a3b-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="26a3b-103">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="26a3b-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26a3b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="26a3b-104">Methods</span></span>  
  
|<span data-ttu-id="26a3b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="26a3b-105">Method</span></span>|<span data-ttu-id="26a3b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="26a3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26a3b-107">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="26a3b-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="26a3b-108">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="26a3b-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="26a3b-109">Метод GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="26a3b-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="26a3b-110">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="26a3b-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26a3b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="26a3b-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26a3b-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="26a3b-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="26a3b-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="26a3b-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a3b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="26a3b-114">Requirements</span></span>  
 <span data-ttu-id="26a3b-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a3b-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26a3b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26a3b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a3b-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="26a3b-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="26a3b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26a3b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="26a3b-119">See also</span></span>

- [<span data-ttu-id="26a3b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="26a3b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="26a3b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="26a3b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
