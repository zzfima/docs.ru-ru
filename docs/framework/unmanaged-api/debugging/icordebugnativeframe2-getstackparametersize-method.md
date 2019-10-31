---
title: Метод ICorDebugNativeFrame2::GetStackParameterSize
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 4dd9760c347bbc23f3e8225c1ff748c6b7b8bfe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096528"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="d75be-102">Метод ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="d75be-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="d75be-103">Возвращает совокупный размер параметров в стеке в операционных системах x86.</span><span class="sxs-lookup"><span data-stu-id="d75be-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d75be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d75be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d75be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d75be-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="d75be-106">заполняет Указатель на совокупный размер параметров в стеке.</span><span class="sxs-lookup"><span data-stu-id="d75be-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d75be-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d75be-107">Return Value</span></span>  
 <span data-ttu-id="d75be-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="d75be-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d75be-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d75be-109">HRESULT</span></span>|<span data-ttu-id="d75be-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d75be-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d75be-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d75be-111">S_OK</span></span>|<span data-ttu-id="d75be-112">Размер стека успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d75be-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="d75be-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d75be-113">S_FALSE</span></span>|<span data-ttu-id="d75be-114">`GetStackParameterSize` был вызван на платформе, отличной от x86.</span><span class="sxs-lookup"><span data-stu-id="d75be-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="d75be-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d75be-115">E_FAIL</span></span>|<span data-ttu-id="d75be-116">`The size of the parameters could not be returned`</span><span class="sxs-lookup"><span data-stu-id="d75be-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="d75be-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d75be-117">E_INVALIDARG</span></span>|<span data-ttu-id="d75be-118">`pSize` `null`.</span><span class="sxs-lookup"><span data-stu-id="d75be-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d75be-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="d75be-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d75be-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="d75be-120">Remarks</span></span>  
 <span data-ttu-id="d75be-121">Методы [икордебугстакквалк](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) не настраивают указатель стека для параметров, помещаемых в стек.</span><span class="sxs-lookup"><span data-stu-id="d75be-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="d75be-122">Вместо этого можно использовать значение, возвращаемое `GetStackParameterSize`, чтобы настроить указатель стека на заполнение собственного, неуправляемого кода, который будет корректироваться для параметров.</span><span class="sxs-lookup"><span data-stu-id="d75be-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d75be-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d75be-123">Requirements</span></span>  
 <span data-ttu-id="d75be-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d75be-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d75be-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d75be-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d75be-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d75be-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d75be-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d75be-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75be-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d75be-128">See also</span></span>

- [<span data-ttu-id="d75be-129">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="d75be-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="d75be-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d75be-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d75be-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="d75be-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
