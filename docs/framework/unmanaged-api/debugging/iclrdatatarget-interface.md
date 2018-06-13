---
title: Интерфейс ICLRDataTarget
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0a5abe8877c8414443fadc00e223df240721132
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410446"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="de2a6-102">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="de2a6-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="de2a6-103">Предоставляет методы для взаимодействия с целевым элементом среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="de2a6-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de2a6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="de2a6-104">Methods</span></span>  
  
|<span data-ttu-id="de2a6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="de2a6-105">Method</span></span>|<span data-ttu-id="de2a6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="de2a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de2a6-107">Метод GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="de2a6-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="de2a6-108">Получает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="de2a6-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="de2a6-109">Метод GetImageBase</span><span class="sxs-lookup"><span data-stu-id="de2a6-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="de2a6-110">Получает базовый адрес памяти для указанного образа.</span><span class="sxs-lookup"><span data-stu-id="de2a6-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="de2a6-111">Метод GetMachineType</span><span class="sxs-lookup"><span data-stu-id="de2a6-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="de2a6-112">Получает идентификатор для типа набора инструкций, целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="de2a6-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="de2a6-113">Метод GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="de2a6-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="de2a6-114">Возвращает размер в байтах, указателя на текущий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="de2a6-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="de2a6-115">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="de2a6-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="de2a6-116">Возвращает указатель на контекст потока с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="de2a6-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="de2a6-117">Метод GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="de2a6-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="de2a6-118">Возвращает значение в локальном хранилище потока (TLS) с указанным индексом для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="de2a6-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="de2a6-119">Метод ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="de2a6-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="de2a6-120">Считывает данные из указанного адреса виртуальной памяти в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="de2a6-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="de2a6-121">Метод Request</span><span class="sxs-lookup"><span data-stu-id="de2a6-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="de2a6-122">Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определяются реализацией.</span><span class="sxs-lookup"><span data-stu-id="de2a6-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="de2a6-123">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="de2a6-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="de2a6-124">Задает текущий контекст заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="de2a6-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="de2a6-125">Метод SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="de2a6-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="de2a6-126">Задает значение в локальном хранилище потока (TLS) заданного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="de2a6-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="de2a6-127">Метод WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="de2a6-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="de2a6-128">Записывает данные из указанного буфера указанного адреса виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="de2a6-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de2a6-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="de2a6-129">Remarks</span></span>  
 <span data-ttu-id="de2a6-130">Клиент API (то есть отладчик) должен реализовывать этот интерфейс, по мере необходимости для определенного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="de2a6-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="de2a6-131">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="de2a6-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2a6-132">Требования</span><span class="sxs-lookup"><span data-stu-id="de2a6-132">Requirements</span></span>  
 <span data-ttu-id="de2a6-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de2a6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2a6-134">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="de2a6-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="de2a6-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2a6-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2a6-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2a6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2a6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="de2a6-137">See Also</span></span>  
 [<span data-ttu-id="de2a6-138">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="de2a6-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="de2a6-139">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="de2a6-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
