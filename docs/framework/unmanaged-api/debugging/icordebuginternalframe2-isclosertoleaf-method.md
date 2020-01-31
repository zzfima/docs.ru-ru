---
title: Метод ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 5dd93dcc29ace6573e313f732c45af0dfbb900e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782210"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="ba2aa-102">Метод ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="ba2aa-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="ba2aa-103">Проверяет, находится ли внутренний кадр `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba2aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba2aa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba2aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba2aa-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="ba2aa-106">окне Указатель на объект сравнения `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="ba2aa-107">[out] `true`, если внутренний кадр `this` находится ближе к конечному объекту, чем кадр, заданный `pFrameToCompare`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba2aa-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba2aa-108">Return Value</span></span>  
 <span data-ttu-id="ba2aa-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ba2aa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba2aa-110">HRESULT</span></span>|<span data-ttu-id="ba2aa-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ba2aa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba2aa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba2aa-112">S_OK</span></span>|<span data-ttu-id="ba2aa-113">Сравнение успешно выполнено.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="ba2aa-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba2aa-114">E_FAIL</span></span>|<span data-ttu-id="ba2aa-115">Не удалось выполнить сравнение.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="ba2aa-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ba2aa-116">E_INVALIDARG</span></span>|<span data-ttu-id="ba2aa-117">`pFrameToCompare` или `pIsCloser` равно null.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba2aa-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="ba2aa-118">Remarks</span></span>  
 <span data-ttu-id="ba2aa-119">`IsCloserToLeaf` можно использовать для реализации политики для поверх внутренних кадров с другими кадрами в стеке.</span><span class="sxs-lookup"><span data-stu-id="ba2aa-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba2aa-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ba2aa-120">Requirements</span></span>  
 <span data-ttu-id="ba2aa-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba2aa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba2aa-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba2aa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba2aa-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba2aa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba2aa-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba2aa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba2aa-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba2aa-125">See also</span></span>

- [<span data-ttu-id="ba2aa-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="ba2aa-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="ba2aa-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ba2aa-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ba2aa-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="ba2aa-128">Debugging</span></span>](index.md)
