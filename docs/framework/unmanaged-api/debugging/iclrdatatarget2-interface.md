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
ms.openlocfilehash: bdc8378a129dd5bb1d9fdcb080c7b5cd53d34091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789073"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="17068-102">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="17068-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="17068-103">Подкласс [ICLRDataTarget](iclrdatatarget-interface.md) , используемый уровнем служб доступа к данным для управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="17068-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17068-104">Методы</span><span class="sxs-lookup"><span data-stu-id="17068-104">Methods</span></span>  
  
|<span data-ttu-id="17068-105">Метод</span><span class="sxs-lookup"><span data-stu-id="17068-105">Method</span></span>|<span data-ttu-id="17068-106">Описание</span><span class="sxs-lookup"><span data-stu-id="17068-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17068-107">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="17068-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="17068-108">Выделяет память в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="17068-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="17068-109">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="17068-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="17068-110">Освобождает память, которая была ранее выделена в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="17068-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17068-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="17068-111">Remarks</span></span>  
 <span data-ttu-id="17068-112">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="17068-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="17068-113">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="17068-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="17068-114">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="17068-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17068-115">Требования</span><span class="sxs-lookup"><span data-stu-id="17068-115">Requirements</span></span>  
 <span data-ttu-id="17068-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17068-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17068-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="17068-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="17068-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17068-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17068-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17068-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17068-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="17068-120">See also</span></span>

- [<span data-ttu-id="17068-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="17068-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="17068-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="17068-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
