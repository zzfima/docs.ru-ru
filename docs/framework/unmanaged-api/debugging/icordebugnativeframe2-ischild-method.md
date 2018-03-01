---
title: "Метод ICorDebugNativeFrame2::IsChild"
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
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 267bc2fcd03786bfceb218dd0218ffa7006f8fa7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="fe0e1-102">Метод ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="fe0e1-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="fe0e1-103">Определяет, является ли текущий кадр является дочерней рамкой.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe0e1-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe0e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe0e1-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="fe0e1-106">[out] Логическое значение, указывающее, имеет ли текущий кадр является дочерней рамкой.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe0e1-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe0e1-107">Return Value</span></span>  
 <span data-ttu-id="fe0e1-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fe0e1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe0e1-109">HRESULT</span></span>|<span data-ttu-id="fe0e1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fe0e1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe0e1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe0e1-111">S_OK</span></span>|<span data-ttu-id="fe0e1-112">Состояние дочерних был успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="fe0e1-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe0e1-113">E_FAIL</span></span>|<span data-ttu-id="fe0e1-114">Не удалось вернуть состояние дочерних.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="fe0e1-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fe0e1-115">E_INVALIDARG</span></span>|<span data-ttu-id="fe0e1-116">Параметр `pIsChild` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="fe0e1-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="fe0e1-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe0e1-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe0e1-118">Remarks</span></span>  
 <span data-ttu-id="fe0e1-119">`IsChild` Возвращает `true` Если объект кадра, для которого вызван метод является дочерним другого кадра.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="fe0e1-120">Если это так, используйте [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) метод для проверки, является ли рамка его родителя.</span><span class="sxs-lookup"><span data-stu-id="fe0e1-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe0e1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fe0e1-121">Requirements</span></span>  
 <span data-ttu-id="fe0e1-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe0e1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe0e1-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe0e1-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe0e1-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe0e1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe0e1-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe0e1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0e1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fe0e1-126">See Also</span></span>  
 [<span data-ttu-id="fe0e1-127">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="fe0e1-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="fe0e1-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fe0e1-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fe0e1-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="fe0e1-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
