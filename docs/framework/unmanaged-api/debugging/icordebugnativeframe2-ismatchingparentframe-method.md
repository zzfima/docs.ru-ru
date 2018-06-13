---
title: Метод ICorDebugNativeFrame2::IsMatchingParentFrame
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39c0ea69a0922f5e0d25c98c21ec17a872b2f421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418874"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="0d5df-102">Метод ICorDebugNativeFrame2::IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="0d5df-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="0d5df-103">Определяет, является ли указанный кадр родительским для текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="0d5df-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d5df-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d5df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d5df-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="0d5df-106">[in] Указатель на объект frame, которую следует оценить состояние родительского.</span><span class="sxs-lookup"><span data-stu-id="0d5df-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="0d5df-107">[out] `true` Если `pPotentialParentFrame` является родительским для текущего кадра; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="0d5df-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d5df-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d5df-108">Return Value</span></span>  
 <span data-ttu-id="0d5df-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="0d5df-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0d5df-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d5df-110">HRESULT</span></span>|<span data-ttu-id="0d5df-111">Описание</span><span class="sxs-lookup"><span data-stu-id="0d5df-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d5df-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d5df-112">S_OK</span></span>|<span data-ttu-id="0d5df-113">Состояние родительского был успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0d5df-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="0d5df-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d5df-114">E_FAIL</span></span>|<span data-ttu-id="0d5df-115">Не удалось вернуть состояние родительского.</span><span class="sxs-lookup"><span data-stu-id="0d5df-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="0d5df-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d5df-116">E_INVALIDARG</span></span>|<span data-ttu-id="0d5df-117">`pPotentialParentFrame` или `pIsParent` равно null.</span><span class="sxs-lookup"><span data-stu-id="0d5df-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0d5df-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="0d5df-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d5df-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d5df-119">Remarks</span></span>  
 <span data-ttu-id="0d5df-120">`IsMatchingParentFrame` Возвращает `true` того, является ли объект кадра, передается методу родительский объект кадра, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="0d5df-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="0d5df-121">Если вызвать метод для кадра, который не является дочерним для указанного кадра, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="0d5df-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5df-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0d5df-122">Requirements</span></span>  
 <span data-ttu-id="0d5df-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d5df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5df-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d5df-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d5df-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d5df-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d5df-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5df-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5df-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0d5df-127">See Also</span></span>  
 [<span data-ttu-id="0d5df-128">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="0d5df-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="0d5df-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0d5df-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0d5df-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="0d5df-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
