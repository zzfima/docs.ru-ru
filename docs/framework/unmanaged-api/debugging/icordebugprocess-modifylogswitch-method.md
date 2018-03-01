---
title: "Метод ICorDebugProcess::ModifyLogSwitch"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e5fb515229c566ee47bf99fe1a5985389e2a425
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="b2c6e-102">Метод ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="b2c6e-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="b2c6e-103">Задает уровень важности указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="b2c6e-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2c6e-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2c6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2c6e-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="b2c6e-106">[in] Строка, указывающая имя коммутатора журнала указатель.</span><span class="sxs-lookup"><span data-stu-id="b2c6e-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="b2c6e-107">[in] Уровень серьезности, задаваемое для указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="b2c6e-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2c6e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2c6e-108">Remarks</span></span>  
 <span data-ttu-id="b2c6e-109">Этот метод допустим только после [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) произошла обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="b2c6e-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c6e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b2c6e-110">Requirements</span></span>  
 <span data-ttu-id="b2c6e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2c6e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c6e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2c6e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2c6e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2c6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2c6e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c6e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
