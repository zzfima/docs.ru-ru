---
title: "Метод ICorDebugAssembly2::IsFullyTrusted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly2.IsFullyTrusted
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d155a12a8b281e427f00706cbc6e10a80804c7c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="4de7d-102">Метод ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="4de7d-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="4de7d-103">Возвращает значение, указывающее, является ли сборки было предоставлено полное доверие система безопасности среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4de7d-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4de7d-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4de7d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4de7d-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="4de7d-106">[out] `true` , если сборки был предоставлен полный уровень доверия, система безопасности среды выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="4de7d-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4de7d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4de7d-107">Remarks</span></span>  
 <span data-ttu-id="4de7d-108">Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешены, то есть, если код не в сборке еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="4de7d-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4de7d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4de7d-109">Requirements</span></span>  
 <span data-ttu-id="4de7d-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4de7d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4de7d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4de7d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4de7d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4de7d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4de7d-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4de7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
