---
title: Метод ICorDebugManagedCallback2::FunctionRemapComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515d434e8d8f1c99cf5052ef9a2f1e098f6021b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915282"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="5f8e2-102">Метод ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="5f8e2-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="5f8e2-103">Уведомляет отладчик, что выполнение кода переключил до новой версии редактируемой функции.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f8e2-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f8e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f8e2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5f8e2-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий измененный функцию.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5f8e2-107">[in] Указатель на объект ICorDebugThread, представляющий поток, на котором была обнаружена точка останова преобразования цветов.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="5f8e2-108">[in] Указатель на объект ICorDebugFunction, представляющий версию функции, в настоящее время выполняется в потоке.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f8e2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f8e2-109">Remarks</span></span>  
 <span data-ttu-id="5f8e2-110">Этот обратный вызов дает отладчику возможность создать любое средство организации пошагового режима, существовавшие ранее.</span><span class="sxs-lookup"><span data-stu-id="5f8e2-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8e2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5f8e2-111">Requirements</span></span>  
 <span data-ttu-id="5f8e2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f8e2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8e2-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f8e2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f8e2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f8e2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8e2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5f8e2-116">See also</span></span>

- [<span data-ttu-id="5f8e2-117">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="5f8e2-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5f8e2-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5f8e2-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
