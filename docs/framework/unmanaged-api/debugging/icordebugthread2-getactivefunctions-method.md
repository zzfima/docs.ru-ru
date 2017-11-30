---
title: "Метод ICorDebugThread2::GetActiveFunctions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetActiveFunctions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f7f416a5441b788394e93a98d274d02fa2ec2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="0ec76-102">Метод ICorDebugThread2::GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="0ec76-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="0ec76-103">Получает сведения о активной функции, в каждой из рамок этот поток.</span><span class="sxs-lookup"><span data-stu-id="0ec76-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ec76-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ec76-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ec76-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="0ec76-106">[in] Размер массива `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="0ec76-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="0ec76-107">[out] Указатель на число объектов, возвращаемых `pFunctions` массива.</span><span class="sxs-lookup"><span data-stu-id="0ec76-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="0ec76-108">Число возвращенных объектов будет равно числу управляемые фреймы в стеке.</span><span class="sxs-lookup"><span data-stu-id="0ec76-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="0ec76-109">[in, out] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения о функциях активные в рамках данного потока.</span><span class="sxs-lookup"><span data-stu-id="0ec76-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="0ec76-110">Первый элемент будет использоваться для конечного кадра и т. д. обратно в корень стека.</span><span class="sxs-lookup"><span data-stu-id="0ec76-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ec76-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ec76-111">Remarks</span></span>  
 <span data-ttu-id="0ec76-112">Если `pFunctions` имеет значение null, если на входе `GetActiveFunctions` возвращает количество функций, которые находятся в стеке.</span><span class="sxs-lookup"><span data-stu-id="0ec76-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="0ec76-113">То есть если `pFunctions` имеет значение null, если на входе `GetActiveFunctions` возвращает значение только в `pcFunctions`.</span><span class="sxs-lookup"><span data-stu-id="0ec76-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="0ec76-114">`GetActiveFunctions` Метод предназначен для оптимизации за получение те же сведения из кадров в трассировке стека и содержит только кадры, которые бы объект ICorDebugILFrame для них в полную трассировку стека.</span><span class="sxs-lookup"><span data-stu-id="0ec76-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec76-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0ec76-115">Requirements</span></span>  
 <span data-ttu-id="0ec76-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec76-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec76-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ec76-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ec76-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ec76-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ec76-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec76-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
