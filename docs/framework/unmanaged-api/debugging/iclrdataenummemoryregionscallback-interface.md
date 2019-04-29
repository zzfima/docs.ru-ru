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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698191"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="d84f6-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="d84f6-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="d84f6-103">Предоставляет метод обратного вызова для [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) для сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="d84f6-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d84f6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d84f6-104">Methods</span></span>  
  
|<span data-ttu-id="d84f6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d84f6-105">Method</span></span>|<span data-ttu-id="d84f6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d84f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d84f6-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="d84f6-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="d84f6-108">Вызывается средой `ICLRDataEnumMemoryRegions::EnumMemoryRegions` для сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="d84f6-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d84f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d84f6-109">Requirements</span></span>  
 <span data-ttu-id="d84f6-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d84f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d84f6-111">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d84f6-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d84f6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d84f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d84f6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d84f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84f6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d84f6-114">See also</span></span>

- [<span data-ttu-id="d84f6-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d84f6-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
