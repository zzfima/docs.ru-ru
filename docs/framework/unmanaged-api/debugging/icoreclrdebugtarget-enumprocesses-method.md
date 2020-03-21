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
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178441"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a><span data-ttu-id="a4d9a-102">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="a4d9a-102">ICoreClrDebugTarget::EnumProcesses Method</span></span>
<span data-ttu-id="a4d9a-103">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-103">Enumerates the processes that are running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4d9a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4d9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4d9a-105">Parameters</span></span>  
 `pcProcs`  
 <span data-ttu-id="a4d9a-106">[out] Число процессов, возвращаемых в `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-106">[out] The number of processes returned in `ppProcs`.</span></span> <span data-ttu-id="a4d9a-107">Это значение может быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="a4d9a-107">This value can be 0 (zero).</span></span>  
  
 `ppProcs`  
 <span data-ttu-id="a4d9a-108">(ваут) Массив структур [CoreClrDebugProcInfo,](coreclrdebugprocinfo-structure.md) представляющих процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-108">[out] An array of [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) structures that represent the processes running on the remote computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4d9a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a4d9a-109">Return Value</span></span>  
 <span data-ttu-id="a4d9a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4d9a-110">S_OK</span></span>  
 <span data-ttu-id="a4d9a-111">Успешно.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-111">Success.</span></span>  
  
 <span data-ttu-id="a4d9a-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a4d9a-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="a4d9a-113">Не удается выделить достаточно памяти для `ppProcs`.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-113">Unable to allocate enough memory for `ppProcs`.</span></span>  
  
 <span data-ttu-id="a4d9a-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="a4d9a-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a4d9a-115">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="a4d9a-115">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4d9a-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4d9a-116">Remarks</span></span>  
 <span data-ttu-id="a4d9a-117">Чтобы освободить память, которая была выделена этим методом, позвоните методу [ICoreClrDebugTarget::FreeMemory.](icoreclrdebugtarget-freememory-method.md)</span><span class="sxs-lookup"><span data-stu-id="a4d9a-117">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d9a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a4d9a-118">Requirements</span></span>  
 <span data-ttu-id="a4d9a-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d9a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d9a-120">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="a4d9a-120">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a4d9a-121">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="a4d9a-121">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a4d9a-122">**Рамочные версии .NET:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a4d9a-122">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d9a-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4d9a-123">See also</span></span>

- [<span data-ttu-id="a4d9a-124">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="a4d9a-124">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
