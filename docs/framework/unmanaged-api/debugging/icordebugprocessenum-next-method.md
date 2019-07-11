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
ms.openlocfilehash: 59efdb76c000a78007ec0321202793ed0dd50cfb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768275"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="4fe5d-102">Метод ICorDebugProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4fe5d-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="4fe5d-103">Получает указанное число экземпляров ICorDebugProcess из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4fe5d-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe5d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fe5d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fe5d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fe5d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4fe5d-106">[in] Количество `ICorDebugProcess` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4fe5d-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="4fe5d-107">[out] Массив указателей, каждый из которых указывает `ICorDebugProcess` объект, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="4fe5d-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4fe5d-108">[out] Указатель на число `ICorDebugProcess` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4fe5d-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="4fe5d-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="4fe5d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fe5d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4fe5d-110">Requirements</span></span>  
 <span data-ttu-id="4fe5d-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fe5d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe5d-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fe5d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fe5d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fe5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fe5d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
