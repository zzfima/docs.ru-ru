---
title: "Метод ICorDebugProcess2::ClearUnmanagedBreakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ca1514eaa916f5e607e49b5a5713763f855d937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="37b0d-102">Метод ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="37b0d-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="37b0d-103">Удаляет установленную ранее точку останова по заданному адресу.</span><span class="sxs-lookup"><span data-stu-id="37b0d-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37b0d-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37b0d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37b0d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="37b0d-106">[in] Объект `CORDB_ADDRESS` значение, которое определяет адрес, по которому была задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="37b0d-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b0d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="37b0d-107">Remarks</span></span>  
 <span data-ttu-id="37b0d-108">Указанный точки останова ранее заданные по предыдущим вызовом [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="37b0d-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="37b0d-109">`ClearUnmanagedBreakpoint` Метод может вызываться во время выполнения отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="37b0d-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="37b0d-110">`ClearUnmanagedBreakpoint` Метод возвращает код ошибки, если присоединен отладчик в режиме только для управляемых или точка останова не существует по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="37b0d-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b0d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="37b0d-111">Requirements</span></span>  
 <span data-ttu-id="37b0d-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b0d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b0d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37b0d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37b0d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37b0d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37b0d-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b0d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
