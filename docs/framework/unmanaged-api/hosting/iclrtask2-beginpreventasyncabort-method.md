---
title: Метод ICLRTask2::BeginPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 67841bbcd796e41b3b81f922020fe6c3677730c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124568"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="ab6d9-102">Метод ICLRTask2::BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="ab6d9-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="ab6d9-103">Откладывает запросы на прерывание нового потока от результирующего прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab6d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab6d9-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ab6d9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab6d9-105">Return Value</span></span>  
 <span data-ttu-id="ab6d9-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab6d9-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab6d9-107">HRESULT</span></span>|<span data-ttu-id="ab6d9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ab6d9-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab6d9-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab6d9-109">S_OK</span></span>|<span data-ttu-id="ab6d9-110">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="ab6d9-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ab6d9-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ab6d9-112">Метод был вызван в потоке, который не является текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab6d9-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="ab6d9-113">Remarks</span></span>  
 <span data-ttu-id="ab6d9-114">При вызове этого метода значение счетчика "задержка — прерывание потока" для текущего потока увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="ab6d9-115">Вызовы `BeginPreventAsyncAbort` и [ICLRTask2:: EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="ab6d9-116">Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="ab6d9-117">Если этот вызов не связан с вызовом метода `EndPreventAsyncAbort`, можно достичь состояния, в котором прерывания потока не могут быть доставлены в текущий поток.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="ab6d9-118">Задержка не учитывается для потока, который прерывает работу.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="ab6d9-119">Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ).</span><span class="sxs-lookup"><span data-stu-id="ab6d9-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="ab6d9-120">Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="ab6d9-121">Например, вызов `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` может установить нулевое значение счетчика, если виртуальная машина ранее увеличила ее.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="ab6d9-122">Аналогично, внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="ab6d9-123">Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab6d9-124">Требования</span><span class="sxs-lookup"><span data-stu-id="ab6d9-124">Requirements</span></span>  
 <span data-ttu-id="ab6d9-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab6d9-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab6d9-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ab6d9-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab6d9-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab6d9-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab6d9-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab6d9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab6d9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ab6d9-129">See also</span></span>

- [<span data-ttu-id="ab6d9-130">Метод EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="ab6d9-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="ab6d9-131">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="ab6d9-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="ab6d9-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ab6d9-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ab6d9-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ab6d9-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ab6d9-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ab6d9-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ab6d9-135">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ab6d9-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
