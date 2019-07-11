---
title: Метод ICoreClrDebugTarget::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 301e6cc153f905bc5c15e1b526e6fb1a492a76d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774438"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="2f979-102">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="2f979-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="2f979-103">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f979-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f979-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f979-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f979-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f979-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="2f979-106">[out] Число процессов, возвращаемых в `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2f979-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="2f979-107">Это значение может быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="2f979-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="2f979-108">[out] Массив [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) структур, представляющих процессы, запущенные на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2f979-108">[out] An array of [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f979-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f979-109">Return Value</span></span>  
 <span data-ttu-id="2f979-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f979-110">S_OK</span></span>  
 <span data-ttu-id="2f979-111">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="2f979-111">Success.</span></span>  
  
 <span data-ttu-id="2f979-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2f979-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2f979-113">Не удается выделить достаточно памяти для `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="2f979-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="2f979-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="2f979-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2f979-115">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="2f979-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f979-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f979-116">Remarks</span></span>  
 <span data-ttu-id="2f979-117">Чтобы освободить память, выделенную этим методом, вызовите [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2f979-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f979-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2f979-118">Requirements</span></span>  
 <span data-ttu-id="2f979-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f979-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f979-120">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="2f979-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2f979-121">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2f979-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2f979-122">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2f979-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f979-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2f979-123">See also</span></span>

- [<span data-ttu-id="2f979-124">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="2f979-124">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
