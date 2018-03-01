---
title: "Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1685b1f739519485e5e68928b29a874587e6f9c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="7b93a-102">Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="7b93a-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="7b93a-103">Перечисляет указанные области памяти.</span><span class="sxs-lookup"><span data-stu-id="7b93a-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b93a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b93a-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b93a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b93a-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="7b93a-106">[in] Указатель на [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) экземпляр, который вызывается этот метод для каждой области памяти, перечисляемые в уведомлении отладчика результата.</span><span class="sxs-lookup"><span data-stu-id="7b93a-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="7b93a-107">Перечисление областей памяти продолжается, даже если обратный вызов указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="7b93a-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="7b93a-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="7b93a-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="7b93a-109">[in] Значение [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) перечисления, которое указывает области памяти для перечисления.</span><span class="sxs-lookup"><span data-stu-id="7b93a-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b93a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b93a-110">Remarks</span></span>  
 <span data-ttu-id="7b93a-111">Этот метод использует указанный [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) экземпляр, чтобы уведомить вызывающий объект результатов.</span><span class="sxs-lookup"><span data-stu-id="7b93a-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b93a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7b93a-112">Requirements</span></span>  
 <span data-ttu-id="7b93a-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b93a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b93a-114">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7b93a-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7b93a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b93a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b93a-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b93a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b93a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7b93a-117">See Also</span></span>  
 [<span data-ttu-id="7b93a-118">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="7b93a-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
