---
title: Метод ICorDebugProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c298107983f4835569cfee7503537537ad11a165
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493587"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="4ca23-102">Метод ICorDebugProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4ca23-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="4ca23-103">Получает указанное число экземпляров ICorDebugProcess из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4ca23-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ca23-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ca23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ca23-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4ca23-106">[in] Количество `ICorDebugProcess` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4ca23-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processess`  
 <span data-ttu-id="4ca23-107">[out] Массив указателей, каждый из которых указывает `ICorDebugProcess` объект, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="4ca23-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4ca23-108">[out] Указатель на число `ICorDebugProcess` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4ca23-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="4ca23-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="4ca23-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca23-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4ca23-110">Requirements</span></span>  
 <span data-ttu-id="4ca23-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca23-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ca23-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ca23-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ca23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca23-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
