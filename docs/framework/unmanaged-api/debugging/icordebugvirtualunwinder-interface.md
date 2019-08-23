---
title: Интерфейс ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f78417d613023bb4fb7325560c0c06abe0874aba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967941"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="f41ed-102">Интерфейс ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="f41ed-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="f41ed-103">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="f41ed-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f41ed-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f41ed-104">Methods</span></span>  
  
|<span data-ttu-id="f41ed-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f41ed-105">Method</span></span>|<span data-ttu-id="f41ed-106">name</span><span class="sxs-lookup"><span data-stu-id="f41ed-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="f41ed-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="f41ed-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="f41ed-108">Получает текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="f41ed-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="f41ed-109">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f41ed-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="f41ed-110">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f41ed-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f41ed-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f41ed-111">Remarks</span></span>  
 <span data-ttu-id="f41ed-112">Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.</span><span class="sxs-lookup"><span data-stu-id="f41ed-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f41ed-113">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f41ed-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f41ed-114">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f41ed-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41ed-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f41ed-115">Requirements</span></span>  
 <span data-ttu-id="f41ed-116">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f41ed-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41ed-117">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f41ed-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f41ed-118">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f41ed-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f41ed-119">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f41ed-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41ed-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f41ed-120">See also</span></span>

- [<span data-ttu-id="f41ed-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f41ed-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f41ed-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="f41ed-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
