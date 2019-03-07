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
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489830"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="ac1b9-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ac1b9-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="ac1b9-103">Получает указанное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ac1b9-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac1b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac1b9-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac1b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac1b9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ac1b9-106">[in] Количество `ICorDebugChain` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ac1b9-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="ac1b9-107">[out] Массив указателей, каждый из которых указывает `ICorDebugChain` , представляющий цепочку.</span><span class="sxs-lookup"><span data-stu-id="ac1b9-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ac1b9-108">[out] Указатель на число `ICorDebugChain` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ac1b9-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="ac1b9-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="ac1b9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac1b9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ac1b9-110">Requirements</span></span>  
 <span data-ttu-id="ac1b9-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac1b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac1b9-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac1b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac1b9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac1b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac1b9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac1b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
