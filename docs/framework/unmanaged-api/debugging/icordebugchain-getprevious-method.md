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
ms.openlocfilehash: c7598a9d93631ca93187886fd8929ba10726dad7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124737"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="5c5ce-102">Метод ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="5c5ce-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="5c5ce-103">Возвращает предыдущую цепочку кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="5c5ce-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c5ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c5ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c5ce-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="5c5ce-106">заполняет Указатель на адрес объекта ICorDebugChain, представляющий предыдущую цепочку кадров для данного потока.</span><span class="sxs-lookup"><span data-stu-id="5c5ce-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="5c5ce-107">Если цепочка является первой, `ppChain` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="5c5ce-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5ce-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5c5ce-108">Requirements</span></span>  
 <span data-ttu-id="5c5ce-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5ce-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5ce-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c5ce-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c5ce-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c5ce-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c5ce-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5ce-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
