---
title: Метод ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e70f7ce9cd943fc3641eef710502ae7f50b369e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748544"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="ddd2d-102">Метод ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ddd2d-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="ddd2d-103">Получает указанное число экземпляров «ICorDebugCode» из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ddd2d-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddd2d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddd2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddd2d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ddd2d-106">[in] Количество `ICorDebugCode` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ddd2d-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ddd2d-107">[out] Массив указателей, каждый из которых указывает `ICorDebugCode` объекта.</span><span class="sxs-lookup"><span data-stu-id="ddd2d-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ddd2d-108">[out] Указатель на число `ICorDebugCode` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ddd2d-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="ddd2d-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="ddd2d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd2d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ddd2d-110">Requirements</span></span>  
 <span data-ttu-id="ddd2d-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd2d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd2d-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd2d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd2d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd2d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd2d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd2d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd2d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ddd2d-115">See also</span></span>
