---
title: Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c9e3aa909c4eb674b166bfd14feb59e35df4cfd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488530"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="3cdfc-102">Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="3cdfc-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="3cdfc-103">Перечисляет указанные области памяти.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdfc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cdfc-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cdfc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cdfc-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="3cdfc-106">[in] Указатель на [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) экземпляра, который вызывается этот метод для каждой области памяти, перечисления в уведомлении отладчика результата.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="3cdfc-107">Перечисление областей памяти продолжится, даже если обратный вызов указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="3cdfc-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="3cdfc-109">[in] Значение [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) перечисление, указывающее области памяти, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cdfc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cdfc-110">Remarks</span></span>  
 <span data-ttu-id="3cdfc-111">Этот метод использует указанный [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) экземпляр для уведомления вызывающей стороны результатов.</span><span class="sxs-lookup"><span data-stu-id="3cdfc-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cdfc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3cdfc-112">Requirements</span></span>  
 <span data-ttu-id="3cdfc-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cdfc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cdfc-114">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3cdfc-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3cdfc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cdfc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cdfc-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cdfc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdfc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3cdfc-117">See also</span></span>
- [<span data-ttu-id="3cdfc-118">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="3cdfc-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
