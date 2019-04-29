---
title: Интерфейс ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697944"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="30a77-102">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="30a77-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="30a77-103">Подкласс [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , используемый уровнем служб доступа к данным для управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="30a77-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30a77-104">Методы</span><span class="sxs-lookup"><span data-stu-id="30a77-104">Methods</span></span>  
  
|<span data-ttu-id="30a77-105">Метод</span><span class="sxs-lookup"><span data-stu-id="30a77-105">Method</span></span>|<span data-ttu-id="30a77-106">Описание</span><span class="sxs-lookup"><span data-stu-id="30a77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30a77-107">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="30a77-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="30a77-108">Выделяет память в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="30a77-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="30a77-109">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="30a77-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="30a77-110">Освобождает память, выделенную ранее в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="30a77-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30a77-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="30a77-111">Remarks</span></span>  
 <span data-ttu-id="30a77-112">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="30a77-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="30a77-113">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="30a77-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="30a77-114">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="30a77-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a77-115">Требования</span><span class="sxs-lookup"><span data-stu-id="30a77-115">Requirements</span></span>  
 <span data-ttu-id="30a77-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a77-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a77-117">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="30a77-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="30a77-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a77-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a77-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a77-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a77-120">См. также</span><span class="sxs-lookup"><span data-stu-id="30a77-120">See also</span></span>

- [<span data-ttu-id="30a77-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="30a77-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="30a77-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="30a77-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
