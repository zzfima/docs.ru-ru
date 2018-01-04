---
title: "Метод ICorDebugThread3::CreateStackWalk"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.CreateStackWalk Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3b587a69c7acc3115c282eac065d304dc892b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="bb721-102">Метод ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="bb721-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="bb721-103">Создает [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объект потока, стек которого требуется очистить.</span><span class="sxs-lookup"><span data-stu-id="bb721-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb721-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb721-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb721-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb721-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="bb721-106">[out] Указатель на адрес [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объект потока, стек которого требуется очистить.</span><span class="sxs-lookup"><span data-stu-id="bb721-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb721-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb721-107">Return Value</span></span>  
 <span data-ttu-id="bb721-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="bb721-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bb721-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb721-109">HRESULT</span></span>|<span data-ttu-id="bb721-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bb721-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb721-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb721-111">S_OK</span></span>|<span data-ttu-id="bb721-112">`ICorDebugStackWalk` Объект был успешно создан.</span><span class="sxs-lookup"><span data-stu-id="bb721-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="bb721-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb721-113">E_FAIL</span></span>|<span data-ttu-id="bb721-114">`ICorDebugStackWalk` Объект не был создан.</span><span class="sxs-lookup"><span data-stu-id="bb721-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="bb721-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="bb721-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb721-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb721-116">Remarks</span></span>  
 <span data-ttu-id="bb721-117">Если `CreateStackWalk` метод завершается успешно, возвращенный `ICorDebugStackWalk` контекст объекта имеет значение текущий контекст потока.</span><span class="sxs-lookup"><span data-stu-id="bb721-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb721-118">Требования</span><span class="sxs-lookup"><span data-stu-id="bb721-118">Requirements</span></span>  
 <span data-ttu-id="bb721-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb721-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb721-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb721-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb721-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb721-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb721-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb721-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb721-123">См. также</span><span class="sxs-lookup"><span data-stu-id="bb721-123">See Also</span></span>  
 [<span data-ttu-id="bb721-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bb721-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="bb721-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="bb721-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
