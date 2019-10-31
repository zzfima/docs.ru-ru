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
ms.openlocfilehash: 4134062be93a2fc5e76949d465a7b5822556b408
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128895"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="8582f-102">Метод ICorDebugProcess::EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="8582f-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="8582f-103">Включает и отключает передачу сообщений журнала отладчику.</span><span class="sxs-lookup"><span data-stu-id="8582f-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8582f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8582f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8582f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8582f-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="8582f-106">[in] `true` включает передачу сообщений журнала; `false` отключает передачу.</span><span class="sxs-lookup"><span data-stu-id="8582f-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8582f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="8582f-107">Remarks</span></span>  
 <span data-ttu-id="8582f-108">Этот метод допустим только после возникновения обратного вызова [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8582f-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8582f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8582f-109">Requirements</span></span>  
 <span data-ttu-id="8582f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8582f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8582f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8582f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8582f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8582f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8582f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8582f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
