---
title: Метод ICorDebugCode::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178995"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="10a09-102">Метод ICorDebugCode::GetCode</span><span class="sxs-lookup"><span data-stu-id="10a09-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="10a09-103">Получает весь код для указанной функции, отформатированный для разборки.</span><span class="sxs-lookup"><span data-stu-id="10a09-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="10a09-104">Этот метод был унесена в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="10a09-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="10a09-105">Вместо этого используйте [ICorDebugCode2::GetCodeChunks.](icordebugcode2-getcodechunks-method.md)</span><span class="sxs-lookup"><span data-stu-id="10a09-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a09-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10a09-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a09-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="10a09-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="10a09-108">(в) Смещение начала функции.</span><span class="sxs-lookup"><span data-stu-id="10a09-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="10a09-109">(в) Смещение конца функции.</span><span class="sxs-lookup"><span data-stu-id="10a09-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="10a09-110">(в) Размер массива, `buffer` в который будет возвращен код.</span><span class="sxs-lookup"><span data-stu-id="10a09-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="10a09-111">(ваут) Массив, в который код будет возвращен.</span><span class="sxs-lookup"><span data-stu-id="10a09-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="10a09-112">(ваут) Число байтов вернулось.</span><span class="sxs-lookup"><span data-stu-id="10a09-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10a09-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="10a09-113">Remarks</span></span>  
 <span data-ttu-id="10a09-114">Если код функции был разделен на несколько фрагментов, они скатированы в порядке увеличения родной смещения.</span><span class="sxs-lookup"><span data-stu-id="10a09-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="10a09-115">Границы инструкций не проверяются.</span><span class="sxs-lookup"><span data-stu-id="10a09-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a09-116">Требования</span><span class="sxs-lookup"><span data-stu-id="10a09-116">Requirements</span></span>  
 <span data-ttu-id="10a09-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a09-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a09-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10a09-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10a09-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10a09-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10a09-120">**Рамочные версии .NET:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="10a09-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a09-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10a09-121">See also</span></span>

- [<span data-ttu-id="10a09-122">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="10a09-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
