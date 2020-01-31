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
ms.openlocfilehash: 14a72e4622aac09840e43f8bcdcf8a8c8d6e6892
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777916"
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="e254b-102">Метод ICorDebugCode::GetCode</span><span class="sxs-lookup"><span data-stu-id="e254b-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="e254b-103">Возвращает весь код для указанной функции, отформатированный для дизассемблирования.</span><span class="sxs-lookup"><span data-stu-id="e254b-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="e254b-104">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e254b-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e254b-105">Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e254b-105">Use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e254b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e254b-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e254b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e254b-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="e254b-108">окне Смещение начала функции.</span><span class="sxs-lookup"><span data-stu-id="e254b-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="e254b-109">окне Смещение конца функции.</span><span class="sxs-lookup"><span data-stu-id="e254b-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="e254b-110">окне Размер массива `buffer`, в который будет возвращен код.</span><span class="sxs-lookup"><span data-stu-id="e254b-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e254b-111">заполняет Массив, в который будет возвращен код.</span><span class="sxs-lookup"><span data-stu-id="e254b-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="e254b-112">заполняет Число возвращаемых байтов.</span><span class="sxs-lookup"><span data-stu-id="e254b-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e254b-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="e254b-113">Remarks</span></span>  
 <span data-ttu-id="e254b-114">Если код функции делится на несколько блоков, они объединяются в порядке возрастания смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="e254b-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="e254b-115">Границы инструкций не проверяются.</span><span class="sxs-lookup"><span data-stu-id="e254b-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e254b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e254b-116">Requirements</span></span>  
 <span data-ttu-id="e254b-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e254b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e254b-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e254b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e254b-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e254b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e254b-120">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e254b-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e254b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e254b-121">See also</span></span>

- [<span data-ttu-id="e254b-122">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="e254b-122">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
