---
title: Метод ICorDebugNativeFrame2::IsChild
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503c12da9e98fbd43f3904aad25c5d10655cec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994647"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="97155-102">Метод ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="97155-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="97155-103">Определяет, является ли текущий кадр дочерним.</span><span class="sxs-lookup"><span data-stu-id="97155-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97155-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97155-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97155-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97155-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="97155-106">[out] Логическое значение, указывающее, является ли текущий кадр дочерним.</span><span class="sxs-lookup"><span data-stu-id="97155-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97155-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="97155-107">Return Value</span></span>  
 <span data-ttu-id="97155-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="97155-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="97155-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97155-109">HRESULT</span></span>|<span data-ttu-id="97155-110">Описание</span><span class="sxs-lookup"><span data-stu-id="97155-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97155-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="97155-111">S_OK</span></span>|<span data-ttu-id="97155-112">Состояние дочернего был успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="97155-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="97155-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97155-113">E_FAIL</span></span>|<span data-ttu-id="97155-114">Состояние дочернего не могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="97155-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="97155-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="97155-115">E_INVALIDARG</span></span>|<span data-ttu-id="97155-116">Параметр `pIsChild` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="97155-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="97155-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="97155-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97155-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="97155-118">Remarks</span></span>  
 <span data-ttu-id="97155-119">`IsChild` Возвращает метод `true` Если объект кадра, для которого вызван метод является потомком другого кадра.</span><span class="sxs-lookup"><span data-stu-id="97155-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="97155-120">Если это так, используйте [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) метод для проверки, является ли кадр родительской.</span><span class="sxs-lookup"><span data-stu-id="97155-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97155-121">Требования</span><span class="sxs-lookup"><span data-stu-id="97155-121">Requirements</span></span>  
 <span data-ttu-id="97155-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97155-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97155-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97155-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97155-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97155-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97155-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97155-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97155-126">См. также</span><span class="sxs-lookup"><span data-stu-id="97155-126">See also</span></span>

- [<span data-ttu-id="97155-127">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="97155-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="97155-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="97155-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="97155-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="97155-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
