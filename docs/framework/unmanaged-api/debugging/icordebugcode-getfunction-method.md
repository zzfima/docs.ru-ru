---
title: "Метод ICorDebugCode::GetFunction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0304eaadec5805b1ded9a4cbfe79959c3e18a344
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="df68d-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="df68d-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="df68d-103">Возвращает связанный с «ICorDebugCode» «ICorDebugFunction».</span><span class="sxs-lookup"><span data-stu-id="df68d-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df68d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df68d-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df68d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df68d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="df68d-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="df68d-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df68d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="df68d-107">Remarks</span></span>  
 <span data-ttu-id="df68d-108">`ICorDebugCode`и `ICorDebugFunction` Ведение отношение.</span><span class="sxs-lookup"><span data-stu-id="df68d-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df68d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="df68d-109">Requirements</span></span>  
 <span data-ttu-id="df68d-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df68d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df68d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df68d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df68d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df68d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df68d-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df68d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df68d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="df68d-114">See Also</span></span>  
 
