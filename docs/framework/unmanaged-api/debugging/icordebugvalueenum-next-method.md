---
title: Метод ICorDebugValueEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae09b4f1cd069edf81be583c7c4226717736094
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764273"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="a4152-102">Метод ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a4152-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="a4152-103">Получает указанное число экземпляров «ICorDebugValue» из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a4152-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4152-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4152-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4152-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4152-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a4152-106">[in] Количество `ICorDebugValue` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a4152-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a4152-107">[out] Массив указателей, каждый из которых указывает `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="a4152-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a4152-108">[out] Указатель на число `ICorDebugValue` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a4152-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="a4152-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="a4152-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4152-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a4152-110">Requirements</span></span>  
 <span data-ttu-id="a4152-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4152-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4152-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4152-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4152-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4152-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4152-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4152-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4152-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a4152-115">See also</span></span>
