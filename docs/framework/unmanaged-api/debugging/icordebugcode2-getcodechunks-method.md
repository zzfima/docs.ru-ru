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
ms.openlocfilehash: 4bbc7ac7d87c6a5d36dc3432c603bb7d16d62c00
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747425"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="b4d7d-102">Метод ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="b4d7d-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="b4d7d-103">Возвращает фрагменты кода, который представляет собой этого кода объекта.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4d7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4d7d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4d7d-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="b4d7d-106">[in] Размер `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="b4d7d-107">[out] Число блоков данных, возвращаемых в `chunks` массива.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="b4d7d-108">[out] Массив структур «CodeChunkInfo», каждый из которых представляет отдельный блок кода.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="b4d7d-109">Если значение `cbufSize` равно 0, этот параметр может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4d7d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4d7d-110">Remarks</span></span>  
 <span data-ttu-id="b4d7d-111">Блоки кода никогда не перекрываются, и они будет учитываться порядок, в котором они будут были объединения [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="b4d7d-112">Объект кода промежуточного языка MSIL Microsoft в .NET Framework версии 2.0 будет состоять из одного блока кода.</span><span class="sxs-lookup"><span data-stu-id="b4d7d-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d7d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b4d7d-113">Requirements</span></span>  
 <span data-ttu-id="b4d7d-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d7d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d7d-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4d7d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4d7d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4d7d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4d7d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d7d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d7d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b4d7d-118">See also</span></span>
