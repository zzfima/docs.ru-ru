---
title: Метод ICorDebugChainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4e8b1a76bcc56424e61991d36c94c5f2dfab8aa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745605"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="3cc91-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="3cc91-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="3cc91-103">Получает указанное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="3cc91-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc91-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cc91-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cc91-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cc91-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3cc91-106">[in] Количество `ICorDebugChain` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3cc91-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="3cc91-107">[out] Массив указателей, каждый из которых указывает `ICorDebugChain` , представляющий цепочку.</span><span class="sxs-lookup"><span data-stu-id="3cc91-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3cc91-108">[out] Указатель на число `ICorDebugChain` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3cc91-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="3cc91-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="3cc91-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc91-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3cc91-110">Requirements</span></span>  
 <span data-ttu-id="3cc91-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cc91-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc91-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cc91-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cc91-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cc91-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cc91-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc91-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
