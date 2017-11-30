---
title: "Метод ICorDebugManagedCallback2::FunctionRemapComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cee712c2ff8acf56049ca9e288fad21e4608da3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="d4516-102">Метод ICorDebugManagedCallback2::FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="d4516-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="d4516-103">Уведомляет отладчик о том, что выполнение кода переключил до новой версии редактируемой функции.</span><span class="sxs-lookup"><span data-stu-id="d4516-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4516-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4516-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4516-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4516-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d4516-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий измененную функцию.</span><span class="sxs-lookup"><span data-stu-id="d4516-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d4516-107">[in] Указатель на объект ICorDebugThread, представляющий поток, на котором была обнаружена точка останова преобразования.</span><span class="sxs-lookup"><span data-stu-id="d4516-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="d4516-108">[in] Указатель на объект ICorDebugFunction, представляющий версию функции, в настоящее время выполняется в потоке.</span><span class="sxs-lookup"><span data-stu-id="d4516-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4516-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4516-109">Remarks</span></span>  
 <span data-ttu-id="d4516-110">Этот обратный вызов дает отладчику возможность создать любое средство организации пошагового режима, существовавшие ранее.</span><span class="sxs-lookup"><span data-stu-id="d4516-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4516-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d4516-111">Requirements</span></span>  
 <span data-ttu-id="d4516-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4516-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4516-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4516-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4516-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4516-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4516-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4516-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4516-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d4516-116">See Also</span></span>  
 [<span data-ttu-id="d4516-117">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4516-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="d4516-118">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d4516-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
