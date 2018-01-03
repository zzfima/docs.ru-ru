---
title: "Метод ICorDebugChain::GetPrevious"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetPrevious
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5f98395ff8e77aa52a470f893ea5db02d73fdf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="3f194-102">Метод ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="3f194-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="3f194-103">Возвращает предыдущую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="3f194-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f194-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f194-104">Syntax</span></span>  
  
```  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f194-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f194-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="3f194-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет предыдущую цепь кадров для данного потока.</span><span class="sxs-lookup"><span data-stu-id="3f194-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="3f194-107">Если эта цепь является первой, `ppChain` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="3f194-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f194-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3f194-108">Requirements</span></span>  
 <span data-ttu-id="3f194-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f194-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f194-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f194-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f194-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f194-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f194-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f194-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
