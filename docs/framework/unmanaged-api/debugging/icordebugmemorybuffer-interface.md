---
title: Интерфейс ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: fa1bbca1e771cbc2b3475891862875b97b9e7f90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793141"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="54089-102">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="54089-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="54089-103">Представляет буфер в памяти.</span><span class="sxs-lookup"><span data-stu-id="54089-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54089-104">Методы</span><span class="sxs-lookup"><span data-stu-id="54089-104">Methods</span></span>  
  
|<span data-ttu-id="54089-105">Метод</span><span class="sxs-lookup"><span data-stu-id="54089-105">Method</span></span>|<span data-ttu-id="54089-106">Описание</span><span class="sxs-lookup"><span data-stu-id="54089-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54089-107">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="54089-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="54089-108">Возвращает размер буфера памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="54089-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="54089-109">Метод GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="54089-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="54089-110">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="54089-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54089-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="54089-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54089-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="54089-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="54089-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="54089-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54089-114">Требования</span><span class="sxs-lookup"><span data-stu-id="54089-114">Requirements</span></span>  
 <span data-ttu-id="54089-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54089-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54089-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54089-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54089-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54089-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54089-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54089-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54089-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="54089-119">See also</span></span>

- [<span data-ttu-id="54089-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="54089-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="54089-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="54089-121">Debugging</span></span>](index.md)
