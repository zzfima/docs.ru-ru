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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b69970d50652da203ecf1ae6fe8d604ccee06cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483579"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="63c59-102">Метод ICorDebugCode::GetCode</span><span class="sxs-lookup"><span data-stu-id="63c59-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="63c59-103">Получает весь код для указанной функции, отформатированных для Дизассемблированный код.</span><span class="sxs-lookup"><span data-stu-id="63c59-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="63c59-104">Этот метод был объявлен устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="63c59-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="63c59-105">Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="63c59-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63c59-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63c59-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63c59-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="63c59-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="63c59-108">[in] Смещение начала функции.</span><span class="sxs-lookup"><span data-stu-id="63c59-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="63c59-109">[in] Смещение конца функции.</span><span class="sxs-lookup"><span data-stu-id="63c59-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="63c59-110">[in] Размер `buffer` массива, в который будет возвращаться код.</span><span class="sxs-lookup"><span data-stu-id="63c59-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="63c59-111">[out] Массив, в которую будет возвращаться код.</span><span class="sxs-lookup"><span data-stu-id="63c59-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="63c59-112">[out] Число возвращаемых байтов.</span><span class="sxs-lookup"><span data-stu-id="63c59-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63c59-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="63c59-113">Remarks</span></span>  
 <span data-ttu-id="63c59-114">Если код функции поделен на несколько блоков, они объединяются в порядке возрастания смещения машинного кода.</span><span class="sxs-lookup"><span data-stu-id="63c59-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="63c59-115">Границы инструкций не проверяются.</span><span class="sxs-lookup"><span data-stu-id="63c59-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63c59-116">Требования</span><span class="sxs-lookup"><span data-stu-id="63c59-116">Requirements</span></span>  
 <span data-ttu-id="63c59-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63c59-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63c59-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63c59-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63c59-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63c59-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63c59-120">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="63c59-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c59-121">См. также</span><span class="sxs-lookup"><span data-stu-id="63c59-121">See also</span></span>
- [<span data-ttu-id="63c59-122">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="63c59-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)

