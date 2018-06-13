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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ed92cbf5a859b9d5b7b8eddefda3ad34a98f27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404054"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="d444d-102">Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="d444d-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="d444d-103">Вызывается методом [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) для сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="d444d-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d444d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d444d-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d444d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d444d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d444d-106">[in] Начальный адрес области памяти, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="d444d-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="d444d-107">[in] Размер в байтах, области памяти.</span><span class="sxs-lookup"><span data-stu-id="d444d-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d444d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d444d-108">Remarks</span></span>  
 <span data-ttu-id="d444d-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions` Метод будет вызывать этот метод обратного вызова после каждой попытки перечисления области памяти.</span><span class="sxs-lookup"><span data-stu-id="d444d-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="d444d-110">Перечисление продолжится, даже если этот метод возвращает значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="d444d-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="d444d-111">Области, о которых сообщает этот обратный вызов может быть повторяющиеся или перекрывающиеся области.</span><span class="sxs-lookup"><span data-stu-id="d444d-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d444d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d444d-112">Requirements</span></span>  
 <span data-ttu-id="d444d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d444d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d444d-114">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d444d-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d444d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d444d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d444d-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d444d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d444d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d444d-117">See Also</span></span>  
 [<span data-ttu-id="d444d-118">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="d444d-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
