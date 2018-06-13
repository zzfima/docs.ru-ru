---
title: Метод ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1d05914004d3c1fcc5ff109e854d01661367835
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413123"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="ed133-102">Метод ICorDebugManagedCallback::LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="ed133-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="ed133-103">Уведомляет отладчик о успешно загруженных сборки CLR среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ed133-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed133-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed133-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed133-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed133-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ed133-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в который была загружена сборка.</span><span class="sxs-lookup"><span data-stu-id="ed133-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="ed133-107">[in] Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="ed133-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed133-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ed133-108">Requirements</span></span>  
 <span data-ttu-id="ed133-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed133-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed133-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed133-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed133-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed133-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed133-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed133-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed133-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ed133-113">See Also</span></span>  
 [<span data-ttu-id="ed133-114">Метод UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="ed133-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)  
 [<span data-ttu-id="ed133-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ed133-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
