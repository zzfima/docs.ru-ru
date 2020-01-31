---
title: Интерфейс ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: 168ba2945608a5b26432c5a0f583e5d406f6ce9b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782830"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="9b5fb-102">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9b5fb-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="9b5fb-103">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b5fb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9b5fb-104">Methods</span></span>  
  
|<span data-ttu-id="9b5fb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9b5fb-105">Method</span></span>|<span data-ttu-id="9b5fb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9b5fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b5fb-107">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="9b5fb-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="9b5fb-108">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="9b5fb-109">Метод GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="9b5fb-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="9b5fb-110">Получает указатель собственного интерфейса для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="9b5fb-111">Метод GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="9b5fb-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="9b5fb-112">Получает указатель стека для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b5fb-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="9b5fb-113">Remarks</span></span>  
 <span data-ttu-id="9b5fb-114">Интерфейс `ICorDebugExceptionDebugEvent` реализуется с помощью следующих типов событий:</span><span class="sxs-lookup"><span data-stu-id="9b5fb-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="9b5fb-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9b5fb-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9b5fb-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9b5fb-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9b5fb-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="9b5fb-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="9b5fb-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="9b5fb-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="9b5fb-119">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9b5fb-120">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9b5fb-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b5fb-121">Требования</span><span class="sxs-lookup"><span data-stu-id="9b5fb-121">Requirements</span></span>  
 <span data-ttu-id="9b5fb-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b5fb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b5fb-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b5fb-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b5fb-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b5fb-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b5fb-125">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b5fb-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5fb-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b5fb-126">See also</span></span>

- [<span data-ttu-id="9b5fb-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9b5fb-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9b5fb-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="9b5fb-128">Debugging</span></span>](index.md)
