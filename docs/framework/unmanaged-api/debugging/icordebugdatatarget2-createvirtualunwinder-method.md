---
title: Метод ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c8befed8bc810344b2a3344212a6a4a854300e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763826"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="95c2b-102">Метод ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="95c2b-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="95c2b-103">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="95c2b-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95c2b-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="95c2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95c2b-105">Parameters</span></span>  
 <span data-ttu-id="95c2b-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="95c2b-106">nativeThreadID</span></span>  
 <span data-ttu-id="95c2b-107">[входной] Идентификатор собственного потока, стек которого должен быть очищен.</span><span class="sxs-lookup"><span data-stu-id="95c2b-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="95c2b-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="95c2b-108">contextFlags</span></span>  
 <span data-ttu-id="95c2b-109">[входной] Флаги, указывающие, какие части контекста определены в `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="95c2b-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="95c2b-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="95c2b-110">cbContext</span></span>  
 <span data-ttu-id="95c2b-111">[входной] Размер `initialContext`.</span><span class="sxs-lookup"><span data-stu-id="95c2b-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="95c2b-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="95c2b-112">initialContext</span></span>  
 <span data-ttu-id="95c2b-113">[входной] Данные в контексте.</span><span class="sxs-lookup"><span data-stu-id="95c2b-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="95c2b-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="95c2b-114">ppUnwinder</span></span>  
 <span data-ttu-id="95c2b-115">[выходной] Указатель на адрес объекта интерфейса ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="95c2b-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95c2b-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95c2b-116">Return Value</span></span>  
 <span data-ttu-id="95c2b-117">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="95c2b-117">`S_OK` if successful.</span></span> <span data-ttu-id="95c2b-118">Любое другое значение `HRESULT` указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="95c2b-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="95c2b-119">Любое ошибочное `HRESULT` , полученное процессом mscordbi считается неустранимым и приводит к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) методам возвращать `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="95c2b-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95c2b-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="95c2b-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95c2b-121">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="95c2b-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c2b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="95c2b-122">Requirements</span></span>  
 <span data-ttu-id="95c2b-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c2b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c2b-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95c2b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95c2b-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95c2b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95c2b-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c2b-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c2b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="95c2b-127">See also</span></span>

- [<span data-ttu-id="95c2b-128">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="95c2b-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="95c2b-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="95c2b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
