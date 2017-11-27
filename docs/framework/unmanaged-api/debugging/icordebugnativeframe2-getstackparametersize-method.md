---
title: "Метод ICorDebugNativeFrame2::GetStackParameterSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.GetStackParameterSize Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c265cb564718b362b1354189e59dc217b2866b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="b5d60-102">Метод ICorDebugNativeFrame2::GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="b5d60-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="b5d60-103">Возвращает общий размер параметров в стеке в x86 операционных систем.</span><span class="sxs-lookup"><span data-stu-id="b5d60-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5d60-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5d60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5d60-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b5d60-106">[out] Указатель на общий размер параметров в стеке.</span><span class="sxs-lookup"><span data-stu-id="b5d60-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5d60-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5d60-107">Return Value</span></span>  
 <span data-ttu-id="b5d60-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b5d60-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b5d60-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5d60-109">HRESULT</span></span>|<span data-ttu-id="b5d60-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b5d60-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5d60-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5d60-111">S_OK</span></span>|<span data-ttu-id="b5d60-112">Размер стека успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b5d60-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="b5d60-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b5d60-113">S_FALSE</span></span>|<span data-ttu-id="b5d60-114">`GetStackParameterSize`был вызван на платформе без x86.</span><span class="sxs-lookup"><span data-stu-id="b5d60-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="b5d60-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5d60-115">E_FAIL</span></span>|<span data-ttu-id="b5d60-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="b5d60-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="b5d60-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b5d60-117">E_INVALIDARG</span></span>|<span data-ttu-id="b5d60-118">`pSize`— `null`.</span><span class="sxs-lookup"><span data-stu-id="b5d60-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b5d60-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="b5d60-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5d60-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5d60-120">Remarks</span></span>  
 <span data-ttu-id="b5d60-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) методы настраивают указатель стека для параметров, переданных в стеке.</span><span class="sxs-lookup"><span data-stu-id="b5d60-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="b5d60-122">Вместо этого можно использовать значение, возвращаемое `GetStackParameterSize` корректировать указатель стека для собственного средства очистки, которое выполняет настройку параметров.</span><span class="sxs-lookup"><span data-stu-id="b5d60-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5d60-123">Требования</span><span class="sxs-lookup"><span data-stu-id="b5d60-123">Requirements</span></span>  
 <span data-ttu-id="b5d60-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5d60-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5d60-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5d60-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5d60-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5d60-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5d60-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5d60-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d60-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b5d60-128">See Also</span></span>  
 [<span data-ttu-id="b5d60-129">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="b5d60-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="b5d60-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b5d60-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b5d60-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="b5d60-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
