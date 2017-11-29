---
title: "Метод ICorDebugCode2::GetCodeChunks"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCodeChunks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 950fd5c19e8827a63dcf075c42d3e0c18ff91261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="6a1d2-102">Метод ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="6a1d2-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="6a1d2-103">Возвращает фрагменты кода, состоящий из этого объекта кода.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a1d2-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a1d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a1d2-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="6a1d2-106">[in] Размер `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="6a1d2-107">[out] Число блоков, возвращаемых в `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="6a1d2-108">[out] Массив структур «CodeChunkInfo», каждая из которых представляет одинарный блок кода.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="6a1d2-109">Если значение `cbufSize` равно 0, этот параметр может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1d2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a1d2-110">Remarks</span></span>  
 <span data-ttu-id="6a1d2-111">Блоки кода никогда не перекрываются, и располагаются в порядке, в котором они будут были объединения [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="6a1d2-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="6a1d2-112">Объект кода промежуточного языка MSIL Microsoft в .NET Framework версии 2.0 содержит из одного блока кода.</span><span class="sxs-lookup"><span data-stu-id="6a1d2-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a1d2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6a1d2-113">Requirements</span></span>  
 <span data-ttu-id="6a1d2-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a1d2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a1d2-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a1d2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a1d2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a1d2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a1d2-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a1d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1d2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6a1d2-118">See Also</span></span>  
 
