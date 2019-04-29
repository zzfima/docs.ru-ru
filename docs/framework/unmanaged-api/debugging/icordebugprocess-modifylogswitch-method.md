---
title: Метод ICorDebugProcess::ModifyLogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1c85499e5269027da2c2a01ab67aab2c5da626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775554"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="96df3-102">Метод ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="96df3-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="96df3-103">Задает уровень серьезности, указанный журнал коммутатора.</span><span class="sxs-lookup"><span data-stu-id="96df3-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96df3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96df3-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96df3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96df3-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="96df3-106">[in] Указатель на строку, которая указывает имя переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="96df3-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="96df3-107">[in] Уровень серьезности, который нужно задать для параметра указанного журнала.</span><span class="sxs-lookup"><span data-stu-id="96df3-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96df3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="96df3-108">Remarks</span></span>  
 <span data-ttu-id="96df3-109">Этот метод допустим только после [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) произошла обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="96df3-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96df3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="96df3-110">Requirements</span></span>  
 <span data-ttu-id="96df3-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96df3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96df3-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96df3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96df3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96df3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96df3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96df3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
