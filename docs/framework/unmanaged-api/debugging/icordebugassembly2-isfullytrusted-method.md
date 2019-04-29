---
title: Метод ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645569"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="4203f-102">Метод ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="4203f-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="4203f-103">Получает значение, указывающее ли были предоставлены сборке полное доверие системой безопасности среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4203f-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4203f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4203f-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4203f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4203f-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="4203f-106">[out] `true` Если были предоставлены сборке полное доверие, система безопасности среды выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="4203f-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4203f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4203f-107">Remarks</span></span>  
 <span data-ttu-id="4203f-108">Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешены, то есть если код не в сборке еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="4203f-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4203f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4203f-109">Requirements</span></span>  
 <span data-ttu-id="4203f-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4203f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4203f-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4203f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4203f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4203f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4203f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4203f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
