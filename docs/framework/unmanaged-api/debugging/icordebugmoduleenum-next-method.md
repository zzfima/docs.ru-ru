---
title: Метод ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027c7b0b9ee7902c81b620549b335cd123d8b277
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491377"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="942e4-102">Метод ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="942e4-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="942e4-103">Возвращает число экземпляров «ICorDebugModule», определяемое `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="942e4-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="942e4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="942e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="942e4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="942e4-106">[in] Количество `ICorDebugModule` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="942e4-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="942e4-107">[out] Массив указателей, каждый из которых указывает `ICorDebugModule` объекта.</span><span class="sxs-lookup"><span data-stu-id="942e4-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="942e4-108">[out] Указатель на число `ICorDebugModule` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="942e4-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="942e4-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="942e4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="942e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="942e4-110">Requirements</span></span>  
 <span data-ttu-id="942e4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="942e4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="942e4-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="942e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="942e4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="942e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="942e4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="942e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942e4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="942e4-115">See also</span></span>

