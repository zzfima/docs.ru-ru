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
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793718"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="10e2a-102">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="10e2a-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="10e2a-103">Предоставляет методы для взаимодействия с целевым элементом общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="10e2a-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10e2a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="10e2a-104">Methods</span></span>  
  
|<span data-ttu-id="10e2a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="10e2a-105">Method</span></span>|<span data-ttu-id="10e2a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="10e2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10e2a-107">Метод GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="10e2a-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="10e2a-108">Возвращает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="10e2a-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="10e2a-109">Метод GetImageBase</span><span class="sxs-lookup"><span data-stu-id="10e2a-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="10e2a-110">Возвращает адрес базовой памяти для указанного образа.</span><span class="sxs-lookup"><span data-stu-id="10e2a-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="10e2a-111">Метод GetMachineType</span><span class="sxs-lookup"><span data-stu-id="10e2a-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="10e2a-112">Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="10e2a-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="10e2a-113">Метод GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="10e2a-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="10e2a-114">Возвращает размер (в байтах) указателя на текущий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="10e2a-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="10e2a-115">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="10e2a-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="10e2a-116">Возвращает указатель на контекст потока с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="10e2a-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="10e2a-117">Метод GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="10e2a-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="10e2a-118">Возвращает значение в локальном хранилище потока (TLS) по указанному индексу для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="10e2a-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="10e2a-119">Метод ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="10e2a-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="10e2a-120">Считывает данные из указанного адреса виртуальной памяти в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="10e2a-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="10e2a-121">Метод Request</span><span class="sxs-lookup"><span data-stu-id="10e2a-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="10e2a-122">Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.</span><span class="sxs-lookup"><span data-stu-id="10e2a-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="10e2a-123">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="10e2a-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="10e2a-124">Задает текущий контекст указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="10e2a-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="10e2a-125">Метод SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="10e2a-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="10e2a-126">Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="10e2a-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="10e2a-127">Метод WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="10e2a-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="10e2a-128">Записывает данные из указанного буфера в указанный адрес виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="10e2a-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e2a-129">Заметки</span><span class="sxs-lookup"><span data-stu-id="10e2a-129">Remarks</span></span>  
 <span data-ttu-id="10e2a-130">Клиент API (то есть отладчик) должен реализовать этот интерфейс в соответствии с конкретным целевым элементом.</span><span class="sxs-lookup"><span data-stu-id="10e2a-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="10e2a-131">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="10e2a-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e2a-132">Требования</span><span class="sxs-lookup"><span data-stu-id="10e2a-132">Requirements</span></span>  
 <span data-ttu-id="10e2a-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e2a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e2a-134">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="10e2a-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="10e2a-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e2a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e2a-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e2a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e2a-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="10e2a-137">See also</span></span>

- [<span data-ttu-id="10e2a-138">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="10e2a-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="10e2a-139">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="10e2a-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
