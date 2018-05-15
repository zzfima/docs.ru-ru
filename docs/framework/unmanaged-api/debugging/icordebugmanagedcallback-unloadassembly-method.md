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
ms.openlocfilehash: a892012e872dcf44512adbe0d6890812d84ed899
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="4615e-102">Метод ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="4615e-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="4615e-103">Уведомляет отладчик о выгрузке сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4615e-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4615e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4615e-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4615e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4615e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4615e-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержит сборку.</span><span class="sxs-lookup"><span data-stu-id="4615e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="4615e-107">[in] Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="4615e-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4615e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4615e-108">Remarks</span></span>  
 <span data-ttu-id="4615e-109">Не следует использовать сборки после этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4615e-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4615e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4615e-110">Requirements</span></span>  
 <span data-ttu-id="4615e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4615e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4615e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4615e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4615e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4615e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4615e-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4615e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4615e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4615e-115">See Also</span></span>  
 [<span data-ttu-id="4615e-116">Метод LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="4615e-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="4615e-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4615e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
