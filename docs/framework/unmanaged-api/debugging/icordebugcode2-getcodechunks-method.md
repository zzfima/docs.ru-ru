---
title: Метод ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf8bc747f643819eb82448b4ad6b7fab696c9c91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572504"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="aaedc-102">Метод ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="aaedc-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="aaedc-103">Возвращает фрагменты кода, который представляет собой этого кода объекта.</span><span class="sxs-lookup"><span data-stu-id="aaedc-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaedc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaedc-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaedc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aaedc-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="aaedc-106">[in] Размер `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="aaedc-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="aaedc-107">[out] Число блоков данных, возвращаемых в `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="aaedc-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="aaedc-108">[out] Массив структур «CodeChunkInfo», каждый из которых представляет отдельный блок кода.</span><span class="sxs-lookup"><span data-stu-id="aaedc-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="aaedc-109">Если значение `cbufSize` равно 0, этот параметр может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="aaedc-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaedc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaedc-110">Remarks</span></span>  
 <span data-ttu-id="aaedc-111">Блоки кода никогда не перекрываются, и они будет учитываться порядок, в котором они будут были объединения [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="aaedc-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="aaedc-112">Объект кода промежуточного языка MSIL Microsoft в .NET Framework версии 2.0 будет состоять из одного блока кода.</span><span class="sxs-lookup"><span data-stu-id="aaedc-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaedc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="aaedc-113">Requirements</span></span>  
 <span data-ttu-id="aaedc-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaedc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaedc-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aaedc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aaedc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaedc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaedc-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaedc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaedc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="aaedc-118">See also</span></span>

