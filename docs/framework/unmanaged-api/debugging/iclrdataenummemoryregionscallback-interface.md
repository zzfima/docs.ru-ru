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
ms.openlocfilehash: 4e3891996af5945ed95c8c37dddfee5c446db248
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789108"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="f7438-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="f7438-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="f7438-103">Предоставляет метод обратного вызова для [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) , сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="f7438-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7438-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f7438-104">Methods</span></span>  
  
|<span data-ttu-id="f7438-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f7438-105">Method</span></span>|<span data-ttu-id="f7438-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f7438-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7438-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="f7438-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="f7438-108">Вызывается с помощью `ICLRDataEnumMemoryRegions::EnumMemoryRegions` для передачи в отладчик результата попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="f7438-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7438-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f7438-109">Requirements</span></span>  
 <span data-ttu-id="f7438-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7438-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7438-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="f7438-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f7438-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7438-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7438-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7438-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7438-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7438-114">See also</span></span>

- [<span data-ttu-id="f7438-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f7438-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
