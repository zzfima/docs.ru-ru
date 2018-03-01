---
title: "Метод ICLRTask2::EndPreventAsyncAbort"
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
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b18f6b8f6768c0a2980489cf8b84e16a9dd31350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="6c19d-102">Метод ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6c19d-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="6c19d-103">Позволяет новым или ожидающим запросам прерывания потока в результате поток прерывает выполнение в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="6c19d-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c19d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c19d-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6c19d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6c19d-105">Return Value</span></span>  
 <span data-ttu-id="6c19d-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="6c19d-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6c19d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c19d-107">HRESULT</span></span>|<span data-ttu-id="6c19d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="6c19d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c19d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c19d-109">S_OK</span></span>|<span data-ttu-id="6c19d-110">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6c19d-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="6c19d-111">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="6c19d-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="6c19d-112">Метод был вызван для потока, который не является текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="6c19d-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c19d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c19d-113">Remarks</span></span>  
 <span data-ttu-id="6c19d-114">Вызов уменьшает задержки прерываний потока этот метод счетчик для текущего потока на единицу.</span><span class="sxs-lookup"><span data-stu-id="6c19d-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="6c19d-115">Вызовы [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="6c19d-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="6c19d-116">При условии, что значение счетчика больше нуля, задерживаются прерывания потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="6c19d-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="6c19d-117">Функциональные возможности, предоставляемые этой функции используется внутренне для виртуальной машины (VM).</span><span class="sxs-lookup"><span data-stu-id="6c19d-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="6c19d-118">Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине.</span><span class="sxs-lookup"><span data-stu-id="6c19d-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="6c19d-119">Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его.</span><span class="sxs-lookup"><span data-stu-id="6c19d-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="6c19d-120">Аналогичным образом внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="6c19d-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="6c19d-121">Если она превышает предельное значение целочисленного, так как увеличивается на узле и ВМ, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="6c19d-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c19d-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6c19d-122">Requirements</span></span>  
 <span data-ttu-id="6c19d-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c19d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c19d-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c19d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c19d-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c19d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c19d-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c19d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c19d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6c19d-127">See Also</span></span>  
 [<span data-ttu-id="6c19d-128">Метод BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="6c19d-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="6c19d-129">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="6c19d-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="6c19d-130">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="6c19d-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6c19d-131">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="6c19d-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6c19d-132">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6c19d-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="6c19d-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6c19d-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
