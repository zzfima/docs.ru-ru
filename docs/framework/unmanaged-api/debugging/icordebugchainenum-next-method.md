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
ms.openlocfilehash: cd4f27b958aa4b25c2662d8a5e9da6bcdc73d5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404460"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="362e4-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="362e4-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="362e4-103">Получает заданное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="362e4-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="362e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="362e4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="362e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="362e4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="362e4-106">[in] Количество `ICorDebugChain` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="362e4-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="362e4-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugChain` , представляющий цепочки.</span><span class="sxs-lookup"><span data-stu-id="362e4-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="362e4-108">[out] Указатель на число `ICorDebugChain` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="362e4-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="362e4-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="362e4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="362e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="362e4-110">Requirements</span></span>  
 <span data-ttu-id="362e4-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="362e4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="362e4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="362e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="362e4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="362e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="362e4-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="362e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
