---
title: Метод ICorDebugThread3::CreateStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b21bf047acf306fb41a7e6a8f8e73c698ea5b619
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765200"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="0e6c0-102">Метод ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="0e6c0-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="0e6c0-103">Создает [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объект потока, стек которого вы хотите развернуть.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e6c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e6c0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e6c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e6c0-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="0e6c0-106">[out] Указатель на адрес [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объект потока, стек которого вы хотите развернуть.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e6c0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e6c0-107">Return Value</span></span>  
 <span data-ttu-id="0e6c0-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0e6c0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e6c0-109">HRESULT</span></span>|<span data-ttu-id="0e6c0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0e6c0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e6c0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e6c0-111">S_OK</span></span>|<span data-ttu-id="0e6c0-112">`ICorDebugStackWalk` Объект был успешно создан.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="0e6c0-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e6c0-113">E_FAIL</span></span>|<span data-ttu-id="0e6c0-114">`ICorDebugStackWalk` Объект не был создан.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0e6c0-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="0e6c0-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e6c0-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e6c0-116">Remarks</span></span>  
 <span data-ttu-id="0e6c0-117">Если `CreateStackWalk` метод завершается успешно, возвращенный `ICorDebugStackWalk` контекст объекта присваивается текущий контекст потока.</span><span class="sxs-lookup"><span data-stu-id="0e6c0-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e6c0-118">Требования</span><span class="sxs-lookup"><span data-stu-id="0e6c0-118">Requirements</span></span>  
 <span data-ttu-id="0e6c0-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e6c0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e6c0-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e6c0-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e6c0-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e6c0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e6c0-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e6c0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6c0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0e6c0-123">See also</span></span>

- [<span data-ttu-id="0e6c0-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0e6c0-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0e6c0-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="0e6c0-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
