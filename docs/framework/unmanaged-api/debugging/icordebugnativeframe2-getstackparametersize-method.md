---
title: "Метод ICorDebugNativeFrame2::GetStackParameterSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="e1cb4-102">Метод ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="e1cb4-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="e1cb4-103">Возвращает общий размер параметров в стеке в x86 операционных систем.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1cb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1cb4-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1cb4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1cb4-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="e1cb4-106">[out] Указатель на общий размер параметров в стеке.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1cb4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e1cb4-107">Return Value</span></span>  
 <span data-ttu-id="e1cb4-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e1cb4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1cb4-109">HRESULT</span></span>|<span data-ttu-id="e1cb4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e1cb4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1cb4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1cb4-111">S_OK</span></span>|<span data-ttu-id="e1cb4-112">Размер стека успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="e1cb4-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e1cb4-113">S_FALSE</span></span>|<span data-ttu-id="e1cb4-114">`GetStackParameterSize`был вызван на платформе без x86.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="e1cb4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1cb4-115">E_FAIL</span></span>|<span data-ttu-id="e1cb4-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="e1cb4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e1cb4-117">E_INVALIDARG</span></span>|<span data-ttu-id="e1cb4-118">`pSize`— `null`.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e1cb4-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="e1cb4-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1cb4-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1cb4-120">Remarks</span></span>  
 <span data-ttu-id="e1cb4-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) методы настраивают указатель стека для параметров, переданных в стеке.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="e1cb4-122">Вместо этого можно использовать значение, возвращаемое `GetStackParameterSize` корректировать указатель стека для собственного средства очистки, которое выполняет настройку параметров.</span><span class="sxs-lookup"><span data-stu-id="e1cb4-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1cb4-123">Требования</span><span class="sxs-lookup"><span data-stu-id="e1cb4-123">Requirements</span></span>  
 <span data-ttu-id="e1cb4-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1cb4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1cb4-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1cb4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1cb4-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1cb4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1cb4-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1cb4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1cb4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e1cb4-128">See Also</span></span>  
 [<span data-ttu-id="e1cb4-129">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="e1cb4-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="e1cb4-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e1cb4-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e1cb4-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="e1cb4-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
