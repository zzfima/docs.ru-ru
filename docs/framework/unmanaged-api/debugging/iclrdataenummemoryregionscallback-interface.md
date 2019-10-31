---
title: Интерфейс ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: cf46133095d1345ffbe0356d3ab486c11ae6dbd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122917"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="239b7-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="239b7-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="239b7-103">Предоставляет метод обратного вызова для [иклрдатаенуммеморирегионс:: енуммеморирегионс](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) , сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="239b7-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="239b7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="239b7-104">Methods</span></span>  
  
|<span data-ttu-id="239b7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="239b7-105">Method</span></span>|<span data-ttu-id="239b7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="239b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="239b7-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="239b7-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="239b7-108">Вызывается с помощью `ICLRDataEnumMemoryRegions::EnumMemoryRegions` для передачи в отладчик результата попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="239b7-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="239b7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="239b7-109">Requirements</span></span>  
 <span data-ttu-id="239b7-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="239b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="239b7-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="239b7-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="239b7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="239b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="239b7-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="239b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="239b7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="239b7-114">See also</span></span>

- [<span data-ttu-id="239b7-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="239b7-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
