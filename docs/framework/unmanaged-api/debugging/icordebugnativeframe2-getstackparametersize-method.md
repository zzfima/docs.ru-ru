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
ms.openlocfilehash: 8a5f0f767a7057064e285bf6ac9dcefc86eb9d79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757199"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="2269a-102">Метод ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="2269a-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="2269a-103">Возвращает общий размер параметров в стеке в x86 операционных систем.</span><span class="sxs-lookup"><span data-stu-id="2269a-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2269a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2269a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="2269a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2269a-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="2269a-106">[out] Указатель на общий размер параметров в стеке.</span><span class="sxs-lookup"><span data-stu-id="2269a-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2269a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2269a-107">Return Value</span></span>  
 <span data-ttu-id="2269a-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="2269a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2269a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2269a-109">HRESULT</span></span>|<span data-ttu-id="2269a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2269a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2269a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2269a-111">S_OK</span></span>|<span data-ttu-id="2269a-112">Размер стека успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2269a-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="2269a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2269a-113">S_FALSE</span></span>|<span data-ttu-id="2269a-114">`GetStackParameterSize` был вызван на платформе без — x86.</span><span class="sxs-lookup"><span data-stu-id="2269a-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="2269a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2269a-115">E_FAIL</span></span>|<span data-ttu-id="2269a-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="2269a-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="2269a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2269a-117">E_INVALIDARG</span></span>|<span data-ttu-id="2269a-118">`pSize` — `null`.</span><span class="sxs-lookup"><span data-stu-id="2269a-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2269a-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="2269a-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2269a-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="2269a-120">Remarks</span></span>  
 <span data-ttu-id="2269a-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) методы настраивают указатель стека для параметров, которые передаются в стеке.</span><span class="sxs-lookup"><span data-stu-id="2269a-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="2269a-122">Вместо этого можно использовать значение, возвращенное `GetStackParameterSize` корректировать указатель стека для собственного средства очистки, которое выполняет настройку параметров.</span><span class="sxs-lookup"><span data-stu-id="2269a-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2269a-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2269a-123">Requirements</span></span>  
 <span data-ttu-id="2269a-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2269a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2269a-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2269a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2269a-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2269a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2269a-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2269a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2269a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2269a-128">See also</span></span>

- [<span data-ttu-id="2269a-129">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="2269a-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="2269a-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2269a-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2269a-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="2269a-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
