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
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133950"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="fb279-102">Метод ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="fb279-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="fb279-103">Возвращает значение, указывающее, предоставлено ли сборке полное доверие системой безопасности среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb279-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb279-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb279-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb279-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb279-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="fb279-106">[out] `true`, если сборке было предоставлено полное доверие системой безопасности среды выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fb279-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb279-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="fb279-107">Remarks</span></span>  
 <span data-ttu-id="fb279-108">Этот метод возвращает значение HRESULT объекта CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешена, то есть если в сборке еще не выполнялся код.</span><span class="sxs-lookup"><span data-stu-id="fb279-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb279-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fb279-109">Requirements</span></span>  
 <span data-ttu-id="fb279-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb279-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb279-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb279-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb279-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb279-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb279-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb279-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
