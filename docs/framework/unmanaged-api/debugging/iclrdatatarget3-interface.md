---
title: Интерфейс ICLRDataTarget3
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: a6591f7d7b632bcdbdabb1633f7431d79da7ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111815"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="1b7cd-102">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="1b7cd-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="1b7cd-103">Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , предоставляющий доступ к сведениям об исключениях.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b7cd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1b7cd-104">Methods</span></span>  
  
|<span data-ttu-id="1b7cd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1b7cd-105">Method</span></span>|<span data-ttu-id="1b7cd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1b7cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b7cd-107">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="1b7cd-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="1b7cd-108">Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="1b7cd-109">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="1b7cd-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="1b7cd-110">Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="1b7cd-111">Метод GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="1b7cd-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="1b7cd-112">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b7cd-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="1b7cd-113">Remarks</span></span>  
 <span data-ttu-id="1b7cd-114">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="1b7cd-115">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="1b7cd-116">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="1b7cd-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7cd-117">Требования</span><span class="sxs-lookup"><span data-stu-id="1b7cd-117">Requirements</span></span>  
 <span data-ttu-id="1b7cd-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b7cd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b7cd-119">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="1b7cd-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1b7cd-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b7cd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b7cd-121">**Версии платформы .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1b7cd-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7cd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1b7cd-122">See also</span></span>

- [<span data-ttu-id="1b7cd-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="1b7cd-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="1b7cd-124">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="1b7cd-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="1b7cd-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b7cd-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
