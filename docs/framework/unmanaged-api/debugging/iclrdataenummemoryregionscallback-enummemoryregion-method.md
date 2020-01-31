---
title: Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: c8313b7c97eb5d94424259dc91459f62e13368fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785592"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="f29de-102">Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="f29de-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="f29de-103">Вызывается методом [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) для передачи в отладчик результата попытки перечисления указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="f29de-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f29de-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f29de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f29de-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f29de-106">окне Начальный адрес области памяти, которая должна быть перечислена.</span><span class="sxs-lookup"><span data-stu-id="f29de-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="f29de-107">окне Размер области памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="f29de-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f29de-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="f29de-108">Remarks</span></span>  
 <span data-ttu-id="f29de-109">Метод `ICLRDataEnumMemoryRegions::EnumMemoryRegions` будет вызывать этот метод обратного вызова после каждой попытки перечисления области памяти.</span><span class="sxs-lookup"><span data-stu-id="f29de-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="f29de-110">Перечисление продолжится, даже если этот метод возвращает значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="f29de-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="f29de-111">Регионы, сообщаемые этим обратным вызовом, могут быть дубликатами или перекрывающимися областями.</span><span class="sxs-lookup"><span data-stu-id="f29de-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29de-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f29de-112">Requirements</span></span>  
 <span data-ttu-id="f29de-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29de-114">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="f29de-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f29de-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f29de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f29de-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29de-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f29de-117">See also</span></span>

- [<span data-ttu-id="f29de-118">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="f29de-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
