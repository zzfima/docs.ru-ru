---
title: Метод ICorDebugStackWalk::GetFrame
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 548a8a7743c02be5734b677010627f847c5bc4b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421991"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="65103-102">Метод ICorDebugStackWalk::GetFrame</span><span class="sxs-lookup"><span data-stu-id="65103-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="65103-103">Получает текущий кадр [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="65103-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65103-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65103-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65103-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65103-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="65103-106">[in] Указатель на адрес объекта созданного кадра, который представляет текущий кадр стека.</span><span class="sxs-lookup"><span data-stu-id="65103-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65103-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65103-107">Return Value</span></span>  
 <span data-ttu-id="65103-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="65103-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65103-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65103-109">HRESULT</span></span>|<span data-ttu-id="65103-110">Описание</span><span class="sxs-lookup"><span data-stu-id="65103-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65103-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="65103-111">S_OK</span></span>|<span data-ttu-id="65103-112">Среда выполнения успешно возвращен текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="65103-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="65103-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65103-113">E_FAIL</span></span>|<span data-ttu-id="65103-114">Текущий кадр не возвращен.</span><span class="sxs-lookup"><span data-stu-id="65103-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="65103-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="65103-115">S_FALSE</span></span>|<span data-ttu-id="65103-116">Текущий кадр является собственным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="65103-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="65103-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="65103-117">E_INVALIDARG</span></span>|<span data-ttu-id="65103-118">Параметр `pFrame` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="65103-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="65103-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="65103-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="65103-120">Указатель кадра уже находится в конце стека; Таким образом может осуществляться без дополнительных кадров.</span><span class="sxs-lookup"><span data-stu-id="65103-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="65103-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="65103-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65103-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="65103-122">Remarks</span></span>  
 <span data-ttu-id="65103-123">`ICorDebugStackWalk` Возвращает только фактические кадры стека.</span><span class="sxs-lookup"><span data-stu-id="65103-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="65103-124">Используйте [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) метод для возврата внутренних кадрах.</span><span class="sxs-lookup"><span data-stu-id="65103-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="65103-125">(Внутренние кадры — это структуры данных, переданные в стек средой выполнения для хранения временных данных.)</span><span class="sxs-lookup"><span data-stu-id="65103-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65103-126">Требования</span><span class="sxs-lookup"><span data-stu-id="65103-126">Requirements</span></span>  
 <span data-ttu-id="65103-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65103-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65103-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65103-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65103-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65103-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65103-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65103-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65103-131">См. также</span><span class="sxs-lookup"><span data-stu-id="65103-131">See Also</span></span>  
 [<span data-ttu-id="65103-132">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="65103-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="65103-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="65103-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="65103-134">Отладка</span><span class="sxs-lookup"><span data-stu-id="65103-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
