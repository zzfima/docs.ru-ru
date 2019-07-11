---
title: Метод ICorDebugManagedCallback::UnloadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 120d00bd329db17b98a439aa2e9c36d2d04968d3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761295"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="5ab14-102">Метод ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="5ab14-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="5ab14-103">Уведомляет отладчик о выгрузке сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5ab14-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ab14-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab14-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ab14-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5ab14-106">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит сборку.</span><span class="sxs-lookup"><span data-stu-id="5ab14-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="5ab14-107">[in] Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="5ab14-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ab14-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ab14-108">Remarks</span></span>  
 <span data-ttu-id="5ab14-109">Сборки не следует после этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5ab14-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab14-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5ab14-110">Requirements</span></span>  
 <span data-ttu-id="5ab14-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ab14-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab14-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ab14-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ab14-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab14-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab14-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab14-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab14-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5ab14-115">See also</span></span>

- [<span data-ttu-id="5ab14-116">Метод LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="5ab14-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="5ab14-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5ab14-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
