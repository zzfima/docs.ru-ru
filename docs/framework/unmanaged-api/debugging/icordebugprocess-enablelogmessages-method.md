---
title: Метод ICorDebugProcess::EnableLogMessages
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe237ca01d409636f184930d26ca970d58e90437
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472956"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="3cf3a-102">Метод ICorDebugProcess::EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="3cf3a-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="3cf3a-103">Включает и отключает передачу сообщений журнала в отладчик.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cf3a-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cf3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cf3a-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="3cf3a-106">[in] `true` позволяет передавать сообщения журнала; `false` отключает передачу.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cf3a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cf3a-107">Remarks</span></span>  
 <span data-ttu-id="3cf3a-108">Этот метод допустим только после [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) происходит обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cf3a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3cf3a-109">Requirements</span></span>  
 <span data-ttu-id="3cf3a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf3a-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cf3a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cf3a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cf3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cf3a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cf3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
