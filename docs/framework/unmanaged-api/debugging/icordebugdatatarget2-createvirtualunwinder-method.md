---
title: Метод ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a983561f34bee96f5de1e05d608bff930c7ec8c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750243"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="a5f5a-102">Метод ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="a5f5a-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="a5f5a-103">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="a5f5a-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5f5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5f5a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5f5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5f5a-105">Parameters</span></span>  
 <span data-ttu-id="a5f5a-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="a5f5a-106">nativeThreadID</span></span>  
 <span data-ttu-id="a5f5a-107">[входной] Идентификатор собственного потока, стек которого должен быть очищен.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="a5f5a-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="a5f5a-108">contextFlags</span></span>  
 <span data-ttu-id="a5f5a-109">[входной] Флаги, указывающие, какие части контекста определены в `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="a5f5a-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="a5f5a-110">cbContext</span></span>  
 <span data-ttu-id="a5f5a-111">[входной] Размер `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="a5f5a-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="a5f5a-112">initialContext</span></span>  
 <span data-ttu-id="a5f5a-113">[входной] Данные в контексте.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="a5f5a-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="a5f5a-114">ppUnwinder</span></span>  
 <span data-ttu-id="a5f5a-115">[выходной] Указатель на адрес объекта интерфейса ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5f5a-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5f5a-116">Return Value</span></span>  
 <span data-ttu-id="a5f5a-117">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-117">`S_OK` if successful.</span></span> <span data-ttu-id="a5f5a-118">Любое другое значение `HRESULT` указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="a5f5a-119">Любое ошибочное `HRESULT` , полученное процессом mscordbi считается неустранимым и приводит к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) методам возвращать `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5f5a-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="a5f5a-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5f5a-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a5f5a-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5f5a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a5f5a-122">Requirements</span></span>  
 <span data-ttu-id="a5f5a-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5f5a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5f5a-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5f5a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5f5a-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5f5a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5f5a-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5f5a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f5a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a5f5a-127">See also</span></span>

- [<span data-ttu-id="a5f5a-128">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a5f5a-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a5f5a-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a5f5a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
