---
title: Метод ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 70aaf32b9da751b49571ab98a95e432b7f84caa9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130641"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="5e45e-102">Метод ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="5e45e-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="5e45e-103">Уведомляет отладчик о выгрузке модуля общеязыковой среды выполнения (DLL).</span><span class="sxs-lookup"><span data-stu-id="5e45e-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e45e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e45e-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e45e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e45e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5e45e-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором содержится модуль.</span><span class="sxs-lookup"><span data-stu-id="5e45e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="5e45e-107">окне Указатель на объект ICorDebugModule, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="5e45e-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e45e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5e45e-108">Remarks</span></span>  
 <span data-ttu-id="5e45e-109">Модуль не должен использоваться после этого вызова.</span><span class="sxs-lookup"><span data-stu-id="5e45e-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e45e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5e45e-110">Requirements</span></span>  
 <span data-ttu-id="5e45e-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e45e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e45e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e45e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e45e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e45e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e45e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e45e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e45e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5e45e-115">See also</span></span>

- [<span data-ttu-id="5e45e-116">Метод LoadModule</span><span class="sxs-lookup"><span data-stu-id="5e45e-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="5e45e-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5e45e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
