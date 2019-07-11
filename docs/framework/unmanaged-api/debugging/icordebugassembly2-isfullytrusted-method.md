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
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744501"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="dcf79-102">Метод ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="dcf79-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="dcf79-103">Получает значение, указывающее ли были предоставлены сборке полное доверие системой безопасности среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dcf79-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcf79-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcf79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcf79-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="dcf79-106">[out] `true` Если были предоставлены сборке полное доверие, система безопасности среды выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="dcf79-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcf79-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcf79-107">Remarks</span></span>  
 <span data-ttu-id="dcf79-108">Этот метод возвращает значение HRESULT CORDBG_E_NOTREADY, если политика безопасности для сборки еще не разрешены, то есть если код не в сборке еще не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="dcf79-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf79-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dcf79-109">Requirements</span></span>  
 <span data-ttu-id="dcf79-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf79-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcf79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf79-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf79-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
