---
title: Метод ICorDebugChain::GetPrevious
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c795c2fbbfdc45b6e1aac6684f730f55fc106a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746414"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="43186-102">Метод ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="43186-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="43186-103">Получает предыдущий цепочки кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="43186-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43186-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43186-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43186-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43186-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="43186-106">[out] Указатель на адрес ICorDebugChain объект, представляющий предыдущий цепочки кадров для данного потока.</span><span class="sxs-lookup"><span data-stu-id="43186-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="43186-107">Если эта цепочка является первой, `ppChain` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="43186-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43186-108">Требования</span><span class="sxs-lookup"><span data-stu-id="43186-108">Requirements</span></span>  
 <span data-ttu-id="43186-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43186-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43186-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43186-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43186-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43186-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43186-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43186-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
