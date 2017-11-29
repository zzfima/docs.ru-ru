---
title: "Метод ICorRuntimeHost::Stop"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.Stop
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f6bf66065293107efae7f401a584b7342f29125
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="3480f-102">Метод ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="3480f-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3480f-103">Останавливает выполнение кода в среде выполнения для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="3480f-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3480f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3480f-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3480f-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3480f-105">Return Value</span></span>  
  
|<span data-ttu-id="3480f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3480f-106">HRESULT</span></span>|<span data-ttu-id="3480f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3480f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3480f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3480f-108">S_OK</span></span>|<span data-ttu-id="3480f-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="3480f-109">The operation was successful.</span></span>|  
|<span data-ttu-id="3480f-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3480f-110">S_FALSE</span></span>|<span data-ttu-id="3480f-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="3480f-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3480f-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3480f-112">E_FAIL</span></span>|<span data-ttu-id="3480f-113">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3480f-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3480f-114">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3480f-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3480f-115">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3480f-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3480f-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3480f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3480f-117">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3480f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3480f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="3480f-118">Remarks</span></span>  
 <span data-ttu-id="3480f-119">Обычно необязателен для вызова `Stop` метод, поскольку код прекращает выполнение при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="3480f-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3480f-120">После вызова `Stop`, среда CLR нельзя инициализировать повторно в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="3480f-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3480f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3480f-121">Requirements</span></span>  
 <span data-ttu-id="3480f-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3480f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3480f-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3480f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3480f-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3480f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3480f-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3480f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3480f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3480f-126">See Also</span></span>  
 [<span data-ttu-id="3480f-127">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3480f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
