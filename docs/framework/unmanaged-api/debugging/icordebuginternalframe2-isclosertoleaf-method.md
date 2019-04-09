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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120904"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="f3fc8-102">Метод ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="f3fc8-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="f3fc8-103">Проверяет ли `this` ближе к конечному объекту, чем указанный объект ICorDebugFrame внутренний фрейм.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3fc8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3fc8-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3fc8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3fc8-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="f3fc8-106">[in] Указатель на сравнение `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="f3fc8-107">[out] `true` Если `this` внутренний фрейм находится ближе к конечному объекту, чем кадр, определяемый `pFrameToCompare`; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3fc8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f3fc8-108">Return Value</span></span>  
 <span data-ttu-id="f3fc8-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f3fc8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3fc8-110">HRESULT</span></span>|<span data-ttu-id="f3fc8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f3fc8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3fc8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3fc8-112">S_OK</span></span>|<span data-ttu-id="f3fc8-113">Сравнение успешно выполнено.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="f3fc8-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3fc8-114">E_FAIL</span></span>|<span data-ttu-id="f3fc8-115">Не удается выполнить сравнение.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="f3fc8-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f3fc8-116">E_INVALIDARG</span></span>|`pFrameToCompare` <span data-ttu-id="f3fc8-117">или `pIsCloser` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-117">or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3fc8-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3fc8-118">Remarks</span></span>  
 `IsCloserToLeaf` <span data-ttu-id="f3fc8-119">можно использовать для реализации политики чередования внутренних кадров с другими фреймы в стеке.</span><span class="sxs-lookup"><span data-stu-id="f3fc8-119">can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3fc8-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f3fc8-120">Requirements</span></span>  
 <span data-ttu-id="f3fc8-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3fc8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3fc8-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3fc8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3fc8-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3fc8-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f3fc8-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f3fc8-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f3fc8-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f3fc8-125">See also</span></span>

- [<span data-ttu-id="f3fc8-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="f3fc8-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="f3fc8-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f3fc8-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f3fc8-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="f3fc8-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
