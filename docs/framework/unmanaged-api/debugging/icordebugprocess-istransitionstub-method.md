---
title: "Метод ICorDebugProcess::IsTransitionStub"
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
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="9640e-102">Метод ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="9640e-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="9640e-103">Получает значение, указывающее, является ли адрес в заглушке, что вызовет переход к управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="9640e-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9640e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9640e-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9640e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9640e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9640e-106">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес в вопросе.</span><span class="sxs-lookup"><span data-stu-id="9640e-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="9640e-107">[out] Указатель на значение типа Boolean, `true` Если указанный адрес находится в пределах заглушки, которая вызовет переход к управляемому коду; в противном случае \*`pbTransitionStub` — `false`.</span><span class="sxs-lookup"><span data-stu-id="9640e-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9640e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9640e-108">Remarks</span></span>  
 <span data-ttu-id="9640e-109">`IsTransitionStub` Метод может использоваться в неуправляемом коде пошагового выполнения для определения момента возвращения управления пошаговым выполнением в управляемый шаг.</span><span class="sxs-lookup"><span data-stu-id="9640e-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="9640e-110">Вы также можете заглушки перехода удостоверений, просмотрев информацию в переносимом исполняемом (PE) файле.</span><span class="sxs-lookup"><span data-stu-id="9640e-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9640e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9640e-111">Requirements</span></span>  
 <span data-ttu-id="9640e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9640e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9640e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9640e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9640e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9640e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9640e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9640e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
