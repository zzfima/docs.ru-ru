---
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 41258b0eeed5fbf8ab86546f74073f8eeaa3085c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777523"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="64d0a-102">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="64d0a-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="64d0a-103">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64d0a-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64d0a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="64d0a-104">Methods</span></span>  
  
|<span data-ttu-id="64d0a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="64d0a-105">Method</span></span>|<span data-ttu-id="64d0a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="64d0a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64d0a-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="64d0a-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="64d0a-108">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64d0a-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="64d0a-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="64d0a-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="64d0a-110">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="64d0a-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="64d0a-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="64d0a-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="64d0a-112">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="64d0a-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64d0a-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="64d0a-113">Remarks</span></span>  
 <span data-ttu-id="64d0a-114">Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64d0a-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64d0a-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="64d0a-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="64d0a-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="64d0a-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d0a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="64d0a-117">Requirements</span></span>  
 <span data-ttu-id="64d0a-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64d0a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d0a-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64d0a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64d0a-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64d0a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64d0a-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d0a-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d0a-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="64d0a-122">See also</span></span>

- [<span data-ttu-id="64d0a-123">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="64d0a-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="64d0a-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64d0a-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="64d0a-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="64d0a-125">Debugging</span></span>](index.md)
