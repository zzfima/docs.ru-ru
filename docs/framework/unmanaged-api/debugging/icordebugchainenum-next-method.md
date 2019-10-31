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
ms.openlocfilehash: 3c11a0547ad5acc5613324d7e9d7439d44549dbc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125813"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="5a188-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5a188-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="5a188-103">Возвращает указанное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="5a188-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a188-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a188-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a188-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a188-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5a188-106">окне Число извлекаемых экземпляров `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="5a188-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="5a188-107">заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugChain`, представляющий цепочку.</span><span class="sxs-lookup"><span data-stu-id="5a188-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5a188-108">заполняет Указатель на число фактически возвращаемых экземпляров `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="5a188-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="5a188-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="5a188-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a188-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5a188-110">Requirements</span></span>  
 <span data-ttu-id="5a188-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a188-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a188-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a188-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a188-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a188-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a188-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a188-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
