---
title: Метод ICorDebugThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b80e0cc026ce80950c14436abb2e84548f9adb64
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499580"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="66838-102">Метод ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="66838-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="66838-103">Возвращает количество экземпляров указанного ICorDebugThread из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="66838-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66838-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66838-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66838-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66838-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="66838-106">[in] Количество `ICorDebugThread` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="66838-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="66838-107">[out] Массив указателей, каждый из которых указывает `ICorDebugThread` , представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="66838-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="66838-108">[out] Указатель на число `ICorDebugThread` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="66838-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="66838-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="66838-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66838-110">Требования</span><span class="sxs-lookup"><span data-stu-id="66838-110">Requirements</span></span>  
 <span data-ttu-id="66838-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66838-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66838-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66838-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66838-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66838-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66838-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66838-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
