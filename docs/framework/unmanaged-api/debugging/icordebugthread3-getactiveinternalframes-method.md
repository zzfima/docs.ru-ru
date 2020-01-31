---
title: Метод ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 25cd3e05bc80dd39d2ca558bb4dd5fb77d255f5a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791399"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="5d21d-102">Метод ICorDebugThread3::GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="5d21d-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="5d21d-103">Возвращает массив внутренних кадров (объектов[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) в стеке.</span><span class="sxs-lookup"><span data-stu-id="5d21d-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d21d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d21d-104">Syntax</span></span>  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d21d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d21d-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="5d21d-106">окне Число внутренних кадров, ожидаемых в `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="5d21d-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="5d21d-107">заполняет Указатель на `ULONG32`, содержащий количество внутренних кадров в стеке.</span><span class="sxs-lookup"><span data-stu-id="5d21d-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="5d21d-108">[вход, выход] Указатель на адрес массива внутренних кадров в стеке.</span><span class="sxs-lookup"><span data-stu-id="5d21d-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d21d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d21d-109">Return Value</span></span>  
 <span data-ttu-id="5d21d-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5d21d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5d21d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d21d-111">HRESULT</span></span>|<span data-ttu-id="5d21d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5d21d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d21d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d21d-113">S_OK</span></span>|<span data-ttu-id="5d21d-114">Объект [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) успешно создан.</span><span class="sxs-lookup"><span data-stu-id="5d21d-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="5d21d-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5d21d-115">E_INVALIDARG</span></span>|<span data-ttu-id="5d21d-116">`cInternalFrames` не равен нулю, `ppInternalFrames` `null`, либо `pcInternalFrames` является `null`.</span><span class="sxs-lookup"><span data-stu-id="5d21d-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="5d21d-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="5d21d-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="5d21d-118">`ppInternalFrames` меньше, чем число внутренних кадров.</span><span class="sxs-lookup"><span data-stu-id="5d21d-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="5d21d-119">Исключения</span><span class="sxs-lookup"><span data-stu-id="5d21d-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d21d-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="5d21d-120">Remarks</span></span>  
 <span data-ttu-id="5d21d-121">Внутренние кадры — это структуры данных, помещаемые в стек средой выполнения для хранения временных данных.</span><span class="sxs-lookup"><span data-stu-id="5d21d-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="5d21d-122">При первом вызове `GetActiveInternalFrames`следует присвоить параметру `cInternalFrames` значение 0 (ноль), а параметру `ppInternalFrames` — значение null.</span><span class="sxs-lookup"><span data-stu-id="5d21d-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="5d21d-123">При первом возвращении `GetActiveInternalFrames` `pcInternalFrames` содержит количество внутренних кадров в стеке.</span><span class="sxs-lookup"><span data-stu-id="5d21d-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="5d21d-124">затем `GetActiveInternalFrames` следует вызвать второй раз.</span><span class="sxs-lookup"><span data-stu-id="5d21d-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="5d21d-125">Необходимо передать правильное число (`pcInternalFrames`) в параметре `cInternalFrames` и указать указатель на массив подходящего размера в `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="5d21d-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="5d21d-126">Используйте метод [икордебугстакквалк:: noframes](icordebugthread3-getactiveinternalframes-method.md) для возврата фактических кадров стека.</span><span class="sxs-lookup"><span data-stu-id="5d21d-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d21d-127">Требования</span><span class="sxs-lookup"><span data-stu-id="5d21d-127">Requirements</span></span>  
 <span data-ttu-id="5d21d-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d21d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d21d-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d21d-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d21d-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d21d-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d21d-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d21d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d21d-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d21d-132">See also</span></span>

- [<span data-ttu-id="5d21d-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5d21d-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5d21d-134">Отладка</span><span class="sxs-lookup"><span data-stu-id="5d21d-134">Debugging</span></span>](index.md)
