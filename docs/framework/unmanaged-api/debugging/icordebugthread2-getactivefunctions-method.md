---
title: Метод ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed13f78d5a1f6d54b12c86613715f4878a521bfa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489934"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="a1043-102">Метод ICorDebugThread2::GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="a1043-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="a1043-103">Получает сведения о активной функции в каждом из кадров этот поток.</span><span class="sxs-lookup"><span data-stu-id="a1043-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1043-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1043-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1043-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1043-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="a1043-106">[in] Размер массива `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="a1043-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="a1043-107">[out] Указатель на число объектов, возвращаемых в `pFunctions` массива.</span><span class="sxs-lookup"><span data-stu-id="a1043-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="a1043-108">Количество возвращенных объектов будет равно числу управляемые фреймы в стеке.</span><span class="sxs-lookup"><span data-stu-id="a1043-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="a1043-109">[in, out] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения об активных функциях в рамках этого потока.</span><span class="sxs-lookup"><span data-stu-id="a1043-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="a1043-110">Первый элемент будет использоваться для фрейме конечного узла и т. д. обратно в корень стека.</span><span class="sxs-lookup"><span data-stu-id="a1043-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1043-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1043-111">Remarks</span></span>  
 <span data-ttu-id="a1043-112">Если `pFunctions` имеет значение null, если во входных данных, `GetActiveFunctions` возвращает количество функций, которые находятся в стеке.</span><span class="sxs-lookup"><span data-stu-id="a1043-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="a1043-113">То есть если `pFunctions` имеет значение null, если во входных данных, `GetActiveFunctions` возвращает значение только в `pcFunctions`.</span><span class="sxs-lookup"><span data-stu-id="a1043-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="a1043-114">`GetActiveFunctions` Метод предназначен для оптимизации за получение те же сведения из кадров в трассировке стека и включает в себя только кадры, которые бы объект ICorDebugILFrame для них в полную трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="a1043-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1043-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a1043-115">Requirements</span></span>  
 <span data-ttu-id="a1043-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1043-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1043-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1043-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1043-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1043-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1043-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1043-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
