---
title: "Метод ICoreClrDebugTarget::EnumProcesses"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumProcesses
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8296b4b137032400ee172b6d3670bc1a53dbe60d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="3b667-102">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="3b667-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="3b667-103">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b667-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b667-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b667-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b667-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b667-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="3b667-106">[out] Число процессов, возвращаемых в `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="3b667-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="3b667-107">Это значение может быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="3b667-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="3b667-108">[out] Массив [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) структур, которые представляют процессы, запущенные на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b667-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b667-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b667-109">Return Value</span></span>  
 <span data-ttu-id="3b667-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b667-110">S_OK</span></span>  
 <span data-ttu-id="3b667-111">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="3b667-111">Success.</span></span>  
  
 <span data-ttu-id="3b667-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3b667-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3b667-113">Не удается выделить достаточно памяти для `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="3b667-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="3b667-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="3b667-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3b667-115">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="3b667-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b667-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b667-116">Remarks</span></span>  
 <span data-ttu-id="3b667-117">Чтобы освободить память, выделенную этим методом, вызовите [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3b667-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b667-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3b667-118">Requirements</span></span>  
 <span data-ttu-id="3b667-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b667-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b667-120">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="3b667-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="3b667-121">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="3b667-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="3b667-122">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3b667-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b667-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3b667-123">See Also</span></span>  
 [<span data-ttu-id="3b667-124">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="3b667-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
