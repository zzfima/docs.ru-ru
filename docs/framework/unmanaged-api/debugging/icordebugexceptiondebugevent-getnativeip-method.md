---
title: Метод ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0069f301df9908a584608c7d20e5348de47361c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501608"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="7e6d8-102">Метод ICorDebugExceptionDebugEvent::GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="7e6d8-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="7e6d8-103">Получает собственный указатель инструкции для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e6d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e6d8-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e6d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e6d8-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="7e6d8-106">[out] Указатель на указатель инструкции для этого события отладки исключения.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="7e6d8-107">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="7e6d8-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e6d8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e6d8-108">Remarks</span></span>  
 <span data-ttu-id="7e6d8-109">Смысл этого указателя инструкции стека зависит от типа события, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7e6d8-110">Тип события.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-110">Event type</span></span>|<span data-ttu-id="7e6d8-111">Смысл значения `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="7e6d8-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="7e6d8-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7e6d8-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e6d8-113">Адрес инструкции со сбоем.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="7e6d8-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7e6d8-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e6d8-115">Указывает адрес кода в фрейме [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) метод, где возобновляться, если исключение не было вызвано.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="7e6d8-116">Исключение может вызывать или не вызывать другой код, например блок catch предложения `try/catch/finally`, выполняемый в этом фрейме.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="7e6d8-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="7e6d8-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e6d8-118">Адрес кода, где `catch` будет запускаться выполнение обработчика в фрейме, указанном [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="7e6d8-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="7e6d8-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7e6d8-120">`pIP` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="7e6d8-121">Тип события доступен из [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e6d8-122">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="7e6d8-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e6d8-123">Требования</span><span class="sxs-lookup"><span data-stu-id="7e6d8-123">Requirements</span></span>  
 <span data-ttu-id="7e6d8-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e6d8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e6d8-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e6d8-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e6d8-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e6d8-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e6d8-127">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e6d8-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6d8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7e6d8-128">See also</span></span>
- [<span data-ttu-id="7e6d8-129">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7e6d8-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="7e6d8-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7e6d8-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
