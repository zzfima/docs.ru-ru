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
ms.openlocfilehash: 5db87cd4ad965654b63a68828cd088b8d2f7d07c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113052"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="de3cd-102">Метод ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="de3cd-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="de3cd-103">Получает указанное число экземпляров «ICorDebugCode» из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="de3cd-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de3cd-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de3cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de3cd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="de3cd-106">[in] Количество `ICorDebugCode` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="de3cd-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="de3cd-107">[out] Массив указателей, каждый из которых указывает `ICorDebugCode` объекта.</span><span class="sxs-lookup"><span data-stu-id="de3cd-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="de3cd-108">[out] Указатель на число `ICorDebugCode` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="de3cd-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="de3cd-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="de3cd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3cd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="de3cd-110">Requirements</span></span>  
 <span data-ttu-id="de3cd-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de3cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de3cd-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de3cd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de3cd-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de3cd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de3cd-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de3cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3cd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="de3cd-115">See also</span></span>
