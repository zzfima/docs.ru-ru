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
ms.openlocfilehash: 19058308876f80afdbaec73583242aa8ad3c33cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="72a7e-102">Метод ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="72a7e-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="72a7e-103">Возвращает значение, указывающее, является ли сборки было предоставлено полное доверие система безопасности среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="72a7e-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72a7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72a7e-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72a7e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72a7e-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="72a7e-106">[out] `true` , если сборки был предоставлен полный уровень доверия, система безопасности среды выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="72a7e-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72a7e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="72a7e-107">Remarks</span></span>  
 <span data-ttu-id="72a7e-108">Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешены, то есть, если код не в сборке еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="72a7e-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72a7e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="72a7e-109">Requirements</span></span>  
 <span data-ttu-id="72a7e-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72a7e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72a7e-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72a7e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72a7e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72a7e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72a7e-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72a7e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
