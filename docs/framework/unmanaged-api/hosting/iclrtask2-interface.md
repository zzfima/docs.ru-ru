---
title: "Интерфейс ICLRTask2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="c26f2-102">Интерфейс ICLRTask2</span><span class="sxs-lookup"><span data-stu-id="c26f2-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="c26f2-103">Предоставляет все функциональные возможности [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейс; Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="c26f2-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c26f2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c26f2-104">Methods</span></span>  
  
|<span data-ttu-id="c26f2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c26f2-105">Method</span></span>|<span data-ttu-id="c26f2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c26f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c26f2-107">BeginPreventAsyncAbort-метод</span><span class="sxs-lookup"><span data-stu-id="c26f2-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="c26f2-108">Задержки новые запросы прерывания потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="c26f2-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="c26f2-109">EndPreventAsyncAbort-метод</span><span class="sxs-lookup"><span data-stu-id="c26f2-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="c26f2-110">Позволяет новым или ожидающим запросам прерывания потока в результате поток прерывает выполнение в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="c26f2-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c26f2-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c26f2-111">Remarks</span></span>  
 <span data-ttu-id="c26f2-112">`ICLRTask2` Интерфейс наследует `ICLRTask` интерфейс и добавляет методы, позволяющие основному приложению откладывать прерывания потока для защиты области кода, которая должна работать без сбоев.</span><span class="sxs-lookup"><span data-stu-id="c26f2-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="c26f2-113">Вызов `BeginPreventAsyncAbort` увеличивает на единицу счетчик задержки прерывания для текущего потока, а вызов метода `EndPreventAsyncAbort` уменьшает его.</span><span class="sxs-lookup"><span data-stu-id="c26f2-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="c26f2-114">Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="c26f2-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="c26f2-115">При условии, что значение счетчика больше нуля, задерживаются прерывания потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="c26f2-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="c26f2-116">Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` , не связан, ее можно достичь состояния, в какой поток прерываний не доставляться к текущему потоку.</span><span class="sxs-lookup"><span data-stu-id="c26f2-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="c26f2-117">Задержка для потока, который прерывает сам не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c26f2-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="c26f2-118">Функциональные возможности, предоставляемые этой функции используется внутренне для виртуальной машины (VM).</span><span class="sxs-lookup"><span data-stu-id="c26f2-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="c26f2-119">Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине.</span><span class="sxs-lookup"><span data-stu-id="c26f2-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="c26f2-120">Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его.</span><span class="sxs-lookup"><span data-stu-id="c26f2-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="c26f2-121">Аналогичным образом внутренний счетчик не проверяется на переполнение.</span><span class="sxs-lookup"><span data-stu-id="c26f2-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="c26f2-122">Если она превышает предельное значение целочисленного, так как увеличивается на узле и ВМ, результирующее поведение не определено.</span><span class="sxs-lookup"><span data-stu-id="c26f2-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="c26f2-123">Для сведения о членах наследуется от `ICLRTask` и о других вариантах использования этого интерфейса, в разделе [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c26f2-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c26f2-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c26f2-124">Requirements</span></span>  
 <span data-ttu-id="c26f2-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c26f2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c26f2-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c26f2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c26f2-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c26f2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c26f2-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c26f2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26f2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c26f2-129">See Also</span></span>  
 [<span data-ttu-id="c26f2-130">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c26f2-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c26f2-131">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c26f2-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c26f2-132">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c26f2-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c26f2-133">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c26f2-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="c26f2-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c26f2-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
