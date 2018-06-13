---
title: Интерфейс ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cedbbf2067a94aa73e40bd4651fc97b72aa9afef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416306"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="0b0a8-102">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0b0a8-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="0b0a8-103">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b0a8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0b0a8-104">Methods</span></span>  
  
|<span data-ttu-id="0b0a8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0b0a8-105">Method</span></span>|<span data-ttu-id="0b0a8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0a8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b0a8-107">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="0b0a8-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="0b0a8-108">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="0b0a8-109">Метод GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="0b0a8-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="0b0a8-110">Получает указатель собственного интерфейса для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="0b0a8-111">Метод GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="0b0a8-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="0b0a8-112">Получает указатель стека для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b0a8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b0a8-113">Remarks</span></span>  
 <span data-ttu-id="0b0a8-114">Интерфейс `ICorDebugExceptionDebugEvent` реализуется с помощью следующих типов событий:</span><span class="sxs-lookup"><span data-stu-id="0b0a8-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
-   [<span data-ttu-id="0b0a8-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0b0a8-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="0b0a8-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0b0a8-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="0b0a8-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="0b0a8-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
-   [<span data-ttu-id="0b0a8-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="0b0a8-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="0b0a8-119">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0b0a8-120">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0b0a8-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b0a8-121">Требования</span><span class="sxs-lookup"><span data-stu-id="0b0a8-121">Requirements</span></span>  
 <span data-ttu-id="0b0a8-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b0a8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b0a8-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b0a8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b0a8-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b0a8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b0a8-125">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b0a8-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0a8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b0a8-126">See Also</span></span>  
 [<span data-ttu-id="0b0a8-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0b0a8-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0b0a8-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="0b0a8-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
