---
title: "Метод ICorDebugThread::GetDebugState"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b9d310cdc088e4b2fc9c6850accc3576a6147ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="520e7-102">Метод ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="520e7-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="520e7-103">Возвращает текущее состояние данного объекта ICorDebugThread отладки.</span><span class="sxs-lookup"><span data-stu-id="520e7-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="520e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="520e7-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="520e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="520e7-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="520e7-106">[out] Указатель на побитовое сочетание значений перечисления CorDebugThreadState, описывающее текущее состояние отладки для данного потока.</span><span class="sxs-lookup"><span data-stu-id="520e7-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="520e7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="520e7-107">Remarks</span></span>  
 <span data-ttu-id="520e7-108">Если в настоящее время остановки процесса, `pState` представляет состояние отладки, который будет существовать для данного потока, будто процесс будет продолжен, а не фактический текущее состояние данного потока.</span><span class="sxs-lookup"><span data-stu-id="520e7-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="520e7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="520e7-109">Requirements</span></span>  
 <span data-ttu-id="520e7-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="520e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="520e7-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="520e7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="520e7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="520e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="520e7-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="520e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
