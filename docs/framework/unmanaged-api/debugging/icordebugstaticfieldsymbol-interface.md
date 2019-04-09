---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103900"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="94bc8-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="94bc8-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="94bc8-103">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="94bc8-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94bc8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="94bc8-104">Methods</span></span>  
  
|<span data-ttu-id="94bc8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="94bc8-105">Method</span></span>|<span data-ttu-id="94bc8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="94bc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94bc8-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="94bc8-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="94bc8-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="94bc8-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="94bc8-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="94bc8-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="94bc8-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="94bc8-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="94bc8-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="94bc8-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="94bc8-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="94bc8-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94bc8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="94bc8-113">Remarks</span></span>  
 <span data-ttu-id="94bc8-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="94bc8-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94bc8-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="94bc8-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="94bc8-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="94bc8-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94bc8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="94bc8-117">Requirements</span></span>  
 <span data-ttu-id="94bc8-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94bc8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94bc8-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94bc8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94bc8-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94bc8-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="94bc8-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="94bc8-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94bc8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="94bc8-122">See also</span></span>

- [<span data-ttu-id="94bc8-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="94bc8-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="94bc8-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="94bc8-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94bc8-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="94bc8-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
