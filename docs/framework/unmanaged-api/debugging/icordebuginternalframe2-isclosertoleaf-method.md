---
title: "Метод ICorDebugInternalFrame2::IsCloserToLeaf"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60e63800ade5fb0d4a222d80ebfe43c3d84c2815
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="c5679-102">Метод ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="c5679-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="c5679-103">Проверяет, является ли `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="c5679-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5679-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5679-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5679-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5679-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="c5679-106">[in] Указатель на сравнении `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="c5679-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="c5679-107">[out] `true` Если `this` внутреннего фрейма ближе к конечному объекту, чем кадр, определяемый `pFrameToCompare`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="c5679-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5679-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5679-108">Return Value</span></span>  
 <span data-ttu-id="c5679-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c5679-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c5679-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5679-110">HRESULT</span></span>|<span data-ttu-id="c5679-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c5679-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5679-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5679-112">S_OK</span></span>|<span data-ttu-id="c5679-113">Сравнение успешно выполнено.</span><span class="sxs-lookup"><span data-stu-id="c5679-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="c5679-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5679-114">E_FAIL</span></span>|<span data-ttu-id="c5679-115">Не удалось выполнить сравнение.</span><span class="sxs-lookup"><span data-stu-id="c5679-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="c5679-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c5679-116">E_INVALIDARG</span></span>|<span data-ttu-id="c5679-117">`pFrameToCompare` или `pIsCloser` равно null.</span><span class="sxs-lookup"><span data-stu-id="c5679-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5679-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5679-118">Remarks</span></span>  
 <span data-ttu-id="c5679-119">`IsCloserToLeaf`можно использовать для реализации политики чередования внутренних кадров с другими кадрами в стеке.</span><span class="sxs-lookup"><span data-stu-id="c5679-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5679-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c5679-120">Requirements</span></span>  
 <span data-ttu-id="c5679-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5679-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5679-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5679-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5679-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5679-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5679-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5679-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5679-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c5679-125">See Also</span></span>  
 [<span data-ttu-id="c5679-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="c5679-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="c5679-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c5679-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c5679-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="c5679-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
