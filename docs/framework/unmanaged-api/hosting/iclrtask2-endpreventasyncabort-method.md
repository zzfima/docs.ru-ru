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
ms.openlocfilehash: 8fd48fbdc48672da4e2dfff83ddd11231877f519
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519714"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="08bfb-102">Метод ICLRTask2::EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="08bfb-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="08bfb-103">Позволяет новым или ожидающих запросов прерывания потока с последующим получением поток прерывает выполнение в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="08bfb-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08bfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08bfb-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="08bfb-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08bfb-105">Return Value</span></span>  
 <span data-ttu-id="08bfb-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="08bfb-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="08bfb-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08bfb-107">HRESULT</span></span>|<span data-ttu-id="08bfb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="08bfb-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08bfb-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="08bfb-109">S_OK</span></span>|<span data-ttu-id="08bfb-110">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="08bfb-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="08bfb-111">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="08bfb-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="08bfb-112">Метод был вызван для потока, который не является текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="08bfb-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08bfb-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="08bfb-113">Remarks</span></span>  
 <span data-ttu-id="08bfb-114">Вызвав этот счетчик уменьшается задержка прерываний потока метод для текущего потока на единицу.</span><span class="sxs-lookup"><span data-stu-id="08bfb-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="08bfb-115">Вызовы [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="08bfb-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="08bfb-116">До тех пор, пока счетчик не равно нулю, являются отложенными прерывания потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="08bfb-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="08bfb-117">Функциональные возможности, предоставляемые этой функции используется внутри виртуальной машины (VM).</span><span class="sxs-lookup"><span data-stu-id="08bfb-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="08bfb-118">Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине.</span><span class="sxs-lookup"><span data-stu-id="08bfb-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="08bfb-119">Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его.</span><span class="sxs-lookup"><span data-stu-id="08bfb-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="08bfb-120">Аналогичным образом внутренний счетчик не проверяются на переполнение.</span><span class="sxs-lookup"><span data-stu-id="08bfb-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="08bfb-121">Если оно превышает превышено, так как увеличивается на узле и виртуальной Машины, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="08bfb-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08bfb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="08bfb-122">Requirements</span></span>  
 <span data-ttu-id="08bfb-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08bfb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08bfb-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08bfb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08bfb-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08bfb-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08bfb-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08bfb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bfb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="08bfb-127">See also</span></span>
- [<span data-ttu-id="08bfb-128">Метод BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="08bfb-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="08bfb-129">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="08bfb-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="08bfb-130">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="08bfb-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="08bfb-131">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="08bfb-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="08bfb-132">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="08bfb-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="08bfb-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="08bfb-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
