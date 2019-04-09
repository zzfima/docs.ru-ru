---
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5c0759989e069169c7e68b71206d9a50b04ad63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111492"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="b1b45-102">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b1b45-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="b1b45-103">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b1b45-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1b45-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b1b45-104">Methods</span></span>  
  
|<span data-ttu-id="b1b45-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b1b45-105">Method</span></span>|<span data-ttu-id="b1b45-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b1b45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1b45-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="b1b45-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="b1b45-108">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b1b45-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="b1b45-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="b1b45-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="b1b45-110">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="b1b45-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="b1b45-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="b1b45-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="b1b45-112">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="b1b45-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b45-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1b45-113">Remarks</span></span>  
 <span data-ttu-id="b1b45-114">Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b1b45-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1b45-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b1b45-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b1b45-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b1b45-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b45-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b1b45-117">Requirements</span></span>  
 <span data-ttu-id="b1b45-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b45-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b45-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1b45-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1b45-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1b45-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1b45-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b1b45-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1b45-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b45-122">See also</span></span>

- [<span data-ttu-id="b1b45-123">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="b1b45-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="b1b45-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b1b45-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b1b45-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="b1b45-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
