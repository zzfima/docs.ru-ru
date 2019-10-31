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
ms.openlocfilehash: ca5db8c8570cedd9b0412b71058d453112a1831c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140130"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="a0a77-102">Метод ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="a0a77-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="a0a77-103">Создает объект [икордебугстакквалк](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="a0a77-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0a77-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0a77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0a77-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="a0a77-106">заполняет Указатель на адрес объекта [икордебугстакквалк](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="a0a77-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0a77-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0a77-107">Return Value</span></span>  
 <span data-ttu-id="a0a77-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="a0a77-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a0a77-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0a77-109">HRESULT</span></span>|<span data-ttu-id="a0a77-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a0a77-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0a77-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0a77-111">S_OK</span></span>|<span data-ttu-id="a0a77-112">Объект `ICorDebugStackWalk` был успешно создан.</span><span class="sxs-lookup"><span data-stu-id="a0a77-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="a0a77-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0a77-113">E_FAIL</span></span>|<span data-ttu-id="a0a77-114">Объект `ICorDebugStackWalk` не был создан.</span><span class="sxs-lookup"><span data-stu-id="a0a77-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a0a77-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="a0a77-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a77-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="a0a77-116">Remarks</span></span>  
 <span data-ttu-id="a0a77-117">Если метод `CreateStackWalk` выполнен, возвращаемый контекст объекта `ICorDebugStackWalk` задается в текущем контексте потока.</span><span class="sxs-lookup"><span data-stu-id="a0a77-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a77-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a0a77-118">Requirements</span></span>  
 <span data-ttu-id="a0a77-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0a77-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a77-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0a77-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0a77-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0a77-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0a77-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a77-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a77-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a0a77-123">See also</span></span>

- [<span data-ttu-id="a0a77-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a0a77-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0a77-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="a0a77-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
