---
title: "Метод ICorDebugModule2::ResolveAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e72d2ed69c8d189adb4980c82e07ad71892dc56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="de2a1-102">Метод ICorDebugModule2::ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="de2a1-102">ICorDebugModule2::ResolveAssembly Method</span></span>
<span data-ttu-id="de2a1-103">Разрешает сборку ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="de2a1-103">Resolves the assembly referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de2a1-104">Syntax</span></span>  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de2a1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de2a1-105">Parameters</span></span>  
 `tkAsemblyRef`  
 <span data-ttu-id="de2a1-106">[in] `mdToken` Значение, которое ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="de2a1-106">[in] An `mdToken` value that references the assembly.</span></span>  
  
 `ppAssembly`  
 <span data-ttu-id="de2a1-107">[out] Указатель на адрес объекта ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="de2a1-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de2a1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="de2a1-108">Remarks</span></span>  
 <span data-ttu-id="de2a1-109">Если сборка еще не загружен при `ResolveAssembly` вызывается HRESULT будет возвращено значение CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="de2a1-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2a1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="de2a1-110">Requirements</span></span>  
 <span data-ttu-id="de2a1-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de2a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2a1-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de2a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de2a1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2a1-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
