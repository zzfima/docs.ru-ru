---
title: Метод ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a6596807b98e6c8b8624b5df18f78dbf8d0711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="5a045-102">Метод ICorDebugModule2::ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="5a045-102">ICorDebugModule2::ResolveAssembly Method</span></span>
<span data-ttu-id="5a045-103">Разрешает сборку ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="5a045-103">Resolves the assembly referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a045-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a045-104">Syntax</span></span>  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a045-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a045-105">Parameters</span></span>  
 `tkAsemblyRef`  
 <span data-ttu-id="5a045-106">[in] `mdToken` Значение, которое ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="5a045-106">[in] An `mdToken` value that references the assembly.</span></span>  
  
 `ppAssembly`  
 <span data-ttu-id="5a045-107">[out] Указатель на адрес объекта ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="5a045-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a045-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a045-108">Remarks</span></span>  
 <span data-ttu-id="5a045-109">Если сборка еще не загружен при `ResolveAssembly` вызывается HRESULT будет возвращено значение CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="5a045-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a045-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5a045-110">Requirements</span></span>  
 <span data-ttu-id="5a045-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a045-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a045-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a045-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a045-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a045-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a045-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a045-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
