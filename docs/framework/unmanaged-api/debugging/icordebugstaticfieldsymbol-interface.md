---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103900"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="d1a33-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="d1a33-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="d1a33-103">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="d1a33-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1a33-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d1a33-104">Methods</span></span>  
  
|<span data-ttu-id="d1a33-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d1a33-105">Method</span></span>|<span data-ttu-id="d1a33-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d1a33-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1a33-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="d1a33-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="d1a33-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="d1a33-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="d1a33-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="d1a33-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="d1a33-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="d1a33-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="d1a33-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="d1a33-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="d1a33-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="d1a33-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1a33-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1a33-113">Remarks</span></span>  
 <span data-ttu-id="d1a33-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="d1a33-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1a33-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d1a33-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d1a33-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d1a33-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a33-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d1a33-117">Requirements</span></span>  
 <span data-ttu-id="d1a33-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a33-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a33-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1a33-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1a33-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1a33-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1a33-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a33-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a33-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d1a33-122">See also</span></span>

- [<span data-ttu-id="d1a33-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="d1a33-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d1a33-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d1a33-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d1a33-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="d1a33-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
