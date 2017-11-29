---
title: "Метод ICorDebugManagedCallback::CreateProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bef3140717ff977fbfae813d0de89011b89ed062
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="2abbf-102">Метод ICorDebugManagedCallback::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="2abbf-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="2abbf-103">Уведомляет отладчик о присоединенного процесс или работы в первый раз.</span><span class="sxs-lookup"><span data-stu-id="2abbf-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2abbf-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2abbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2abbf-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2abbf-106">[in] Указатель на объект ICorDebugProcess, который представляет процесс, который подключен или запущен.</span><span class="sxs-lookup"><span data-stu-id="2abbf-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2abbf-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2abbf-107">Remarks</span></span>  
 <span data-ttu-id="2abbf-108">Этот метод не вызывается, пока не будет инициализирован общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="2abbf-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="2abbf-109">Большинство [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) методы возвращают CORDBG_E_NOTREADY перед `CreateProcess` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2abbf-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2abbf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2abbf-110">Requirements</span></span>  
 <span data-ttu-id="2abbf-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2abbf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2abbf-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2abbf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2abbf-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2abbf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2abbf-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2abbf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abbf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2abbf-115">See Also</span></span>  
 [<span data-ttu-id="2abbf-116">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2abbf-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
