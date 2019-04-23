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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225434"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="038af-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="038af-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="038af-103">Предоставляет метод обратного вызова для [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) для сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="038af-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="038af-104">Методы</span><span class="sxs-lookup"><span data-stu-id="038af-104">Methods</span></span>  
  
|<span data-ttu-id="038af-105">Метод</span><span class="sxs-lookup"><span data-stu-id="038af-105">Method</span></span>|<span data-ttu-id="038af-106">Описание</span><span class="sxs-lookup"><span data-stu-id="038af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="038af-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="038af-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="038af-108">Вызывается средой `ICLRDataEnumMemoryRegions::EnumMemoryRegions` для сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="038af-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="038af-109">Требования</span><span class="sxs-lookup"><span data-stu-id="038af-109">Requirements</span></span>  
 <span data-ttu-id="038af-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="038af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="038af-111">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="038af-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="038af-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="038af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="038af-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="038af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038af-114">См. также</span><span class="sxs-lookup"><span data-stu-id="038af-114">See also</span></span>

- [<span data-ttu-id="038af-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="038af-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
