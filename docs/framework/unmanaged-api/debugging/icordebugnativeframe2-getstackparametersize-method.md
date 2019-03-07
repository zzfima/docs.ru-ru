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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4baa58159760af12afca5b84cb6b1b66e46093
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485542"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="499d3-102">Метод ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="499d3-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="499d3-103">Возвращает общий размер параметров в стеке в x86 операционных систем.</span><span class="sxs-lookup"><span data-stu-id="499d3-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="499d3-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="499d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="499d3-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="499d3-106">[out] Указатель на общий размер параметров в стеке.</span><span class="sxs-lookup"><span data-stu-id="499d3-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="499d3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="499d3-107">Return Value</span></span>  
 <span data-ttu-id="499d3-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="499d3-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="499d3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="499d3-109">HRESULT</span></span>|<span data-ttu-id="499d3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="499d3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="499d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="499d3-111">S_OK</span></span>|<span data-ttu-id="499d3-112">Размер стека успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="499d3-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="499d3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="499d3-113">S_FALSE</span></span>|<span data-ttu-id="499d3-114">`GetStackParameterSize` был вызван на платформе без — x86.</span><span class="sxs-lookup"><span data-stu-id="499d3-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="499d3-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="499d3-115">E_FAIL</span></span>|<span data-ttu-id="499d3-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="499d3-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="499d3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="499d3-117">E_INVALIDARG</span></span>|<span data-ttu-id="499d3-118">`pSize` — `null`.</span><span class="sxs-lookup"><span data-stu-id="499d3-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="499d3-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="499d3-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="499d3-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="499d3-120">Remarks</span></span>  
 <span data-ttu-id="499d3-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) методы настраивают указатель стека для параметров, которые передаются в стеке.</span><span class="sxs-lookup"><span data-stu-id="499d3-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="499d3-122">Вместо этого можно использовать значение, возвращенное `GetStackParameterSize` корректировать указатель стека для собственного средства очистки, которое выполняет настройку параметров.</span><span class="sxs-lookup"><span data-stu-id="499d3-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499d3-123">Требования</span><span class="sxs-lookup"><span data-stu-id="499d3-123">Requirements</span></span>  
 <span data-ttu-id="499d3-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499d3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499d3-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="499d3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="499d3-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="499d3-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="499d3-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499d3-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499d3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="499d3-128">See also</span></span>
- [<span data-ttu-id="499d3-129">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="499d3-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="499d3-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="499d3-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="499d3-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="499d3-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
