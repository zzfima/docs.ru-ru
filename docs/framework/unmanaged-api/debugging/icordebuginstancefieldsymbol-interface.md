---
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e5f63df9354df6a4d142c2f6ae12f9a0d5600fb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910144"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="89615-102">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="89615-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="89615-103">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="89615-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89615-104">Методы</span><span class="sxs-lookup"><span data-stu-id="89615-104">Methods</span></span>  
  
|<span data-ttu-id="89615-105">Метод</span><span class="sxs-lookup"><span data-stu-id="89615-105">Method</span></span>|<span data-ttu-id="89615-106">Описание</span><span class="sxs-lookup"><span data-stu-id="89615-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89615-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="89615-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="89615-108">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="89615-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="89615-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="89615-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="89615-110">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="89615-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="89615-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="89615-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="89615-112">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="89615-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89615-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="89615-113">Remarks</span></span>  
 <span data-ttu-id="89615-114">Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="89615-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89615-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89615-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="89615-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="89615-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89615-117">Требования</span><span class="sxs-lookup"><span data-stu-id="89615-117">Requirements</span></span>  
 <span data-ttu-id="89615-118">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89615-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89615-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="89615-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89615-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="89615-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89615-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89615-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89615-122">См. также</span><span class="sxs-lookup"><span data-stu-id="89615-122">See also</span></span>

- [<span data-ttu-id="89615-123">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="89615-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="89615-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="89615-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="89615-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="89615-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
