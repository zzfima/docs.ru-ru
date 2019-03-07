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
ms.openlocfilehash: 7fdcdf23dfee01e8bad1c95adb4de66f270d5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474973"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="5f8f1-102">Метод ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="5f8f1-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="5f8f1-103">Получает предыдущий цепочки кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="5f8f1-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f8f1-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f8f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f8f1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="5f8f1-106">[out] Указатель на адрес ICorDebugChain объект, представляющий предыдущий цепочки кадров для данного потока.</span><span class="sxs-lookup"><span data-stu-id="5f8f1-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="5f8f1-107">Если эта цепочка является первой, `ppChain` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="5f8f1-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8f1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5f8f1-108">Requirements</span></span>  
 <span data-ttu-id="5f8f1-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f8f1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8f1-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f8f1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f8f1-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8f1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f8f1-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
