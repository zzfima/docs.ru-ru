---
title: Метод ICLRTask2::EndPreventAsyncAbort
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cacc96d66d5d4eb46c08c93d9c2793282627539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="8d2f6-102">Метод ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="8d2f6-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="8d2f6-103">Позволяет новым или ожидающим запросам прерывания потока в результате поток прерывает выполнение в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d2f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d2f6-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d2f6-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8d2f6-105">Return Value</span></span>  
 <span data-ttu-id="8d2f6-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8d2f6-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d2f6-107">HRESULT</span></span>|<span data-ttu-id="8d2f6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8d2f6-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d2f6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d2f6-109">S_OK</span></span>|<span data-ttu-id="8d2f6-110">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="8d2f6-111">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8d2f6-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8d2f6-112">Метод был вызван для потока, который не является текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d2f6-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d2f6-113">Remarks</span></span>  
 <span data-ttu-id="8d2f6-114">Вызов уменьшает задержки прерываний потока этот метод счетчик для текущего потока на единицу.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="8d2f6-115">Вызовы [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="8d2f6-116">При условии, что значение счетчика больше нуля, задерживаются прерывания потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="8d2f6-117">Функциональные возможности, предоставляемые этой функции используется внутренне для виртуальной машины (VM).</span><span class="sxs-lookup"><span data-stu-id="8d2f6-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="8d2f6-118">Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="8d2f6-119">Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="8d2f6-120">Аналогичным образом внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="8d2f6-121">Если она превышает предельное значение целочисленного, так как увеличивается на узле и ВМ, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d2f6-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8d2f6-122">Requirements</span></span>  
 <span data-ttu-id="8d2f6-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d2f6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d2f6-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d2f6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d2f6-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d2f6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d2f6-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d2f6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2f6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8d2f6-127">See Also</span></span>  
 [<span data-ttu-id="8d2f6-128">Метод BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="8d2f6-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="8d2f6-129">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="8d2f6-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="8d2f6-130">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8d2f6-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8d2f6-131">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="8d2f6-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8d2f6-132">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8d2f6-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="8d2f6-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8d2f6-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
